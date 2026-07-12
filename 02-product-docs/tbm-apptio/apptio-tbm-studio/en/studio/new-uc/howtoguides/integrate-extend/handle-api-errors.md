---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To: Handle API Errors"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
source_path: "studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To: Handle API Errors

**Objective:** Implement robust error handling and retry logic for production API
integrations

**Time estimate:** 30-45 minutes to implement

**When to use:** Building production integrations that must handle network issues,
authentication expiration, and service interruptions gracefully.

## API Return Codes

|  |  |  |
| --- | --- | --- |
| **Code** | **Description** | **Action** |
| 200 | Success (GET) | Process response data |
| 201 | Creation successful | Resource created successfully |
| 202 | Update successful | Resource updated successfully |
| 400 | Incorrect API string / Bad request | Check URL format, parameters, and request body |
| 401 | Unauthorized | Re-authenticate and retry |
| 403 | Forbidden | Check user permissions |
| 404 | Not found | Verify resource exists (project, table, time period) |
| 500 | Internal server error | Retry with exponential backoff; contact support if persistent |

## Understanding Error Responses

Error responses return JSON with a message field describing the issue:

```
{
 "message": "Poorly formatted date string: 'SOMEDATE:2010'. Ought to be of the form 'granularity':'year'."
}
```

## Common error messages:

|  |  |  |
| --- | --- | --- |
| **Message Pattern** | **Cause** | **Solution** |
| Poorly formatted date string | Invalid time period format | Use format Month:Year (e.g., January:2024) |
| user X does not exist | Invalid username in request | Verify username format and account exists |
| Access denied | Insufficient permissions | Verify account has required permission sets |
| Table not found | Target table does not exist | Check table name spelling and project |

## Implementing Retry Logic

Production integrations should implement exponential backoff for transient
failures:

```
import requests
import time
import logging
 
class TBMStudioAPIClient:
 """Production-ready TBM Studio API client with retry logic."""
 
 def __init__(self, customer_id, domain, max_retries=3, base_delay=1.0):
 self.customer_id = customer_id
 self.domain = domain
 self.max_retries = max_retries
 self.base_delay = base_delay
 self.token = None
 self.env_id = None
 self.logger = logging.getLogger(__name__)
 
 def authenticate(self, public_key, secret_key):
 """Authenticate and store token."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 response = self._make_request(
 "POST", url,
 json={"keyAccess": public_key, "keySecret": secret_key},
 headers={"Content-Type": "application/json"}
 )
 self.token = response.cookies.get('apptio-opentoken')
 
 # Get environment ID
 env_url = f"https://frontdoor.apptio.com/api/environment/{self.domain}/main"
 env_response = self._make_request("GET", env_url)
 self.env_id = env_response.json()["id"]
 
 def _make_request(self, method, url, **kwargs):
 """Make HTTP request with retry logic."""
 last_exception = None
 
 for attempt in range(self.max_retries):
 try:
 # Add auth headers if authenticated
 if self.token and 'headers' not in kwargs:
 kwargs['headers'] = {}
 if self.token:
 kwargs['headers'].update({
 "apptio-opentoken": self.token,
 "apptio-current-environment": str(self.env_id) if self.env_id else "",
 "app-type": "Flagship",
 "app-version": "NA"
 })
 
 response = requests.request(method, url, **kwargs)
 
 # Check for retryable status codes
 if response.status_code == 401:
 self.logger.warning("Token expired, re-authentication required")
 raise AuthenticationError("Token expired")
 
 if response.status_code >= 500:
 response.raise_for_status() # Will be caught and retried
 
 response.raise_for_status()
 return response
 
 except requests.exceptions.RequestException as e:
 last_exception = e
 
 if attempt < self.max_retries - 1:
 delay = self.base_delay * (2 ** attempt) # Exponential backoff
 self.logger.warning(
 f"Request failed (attempt {attempt + 1}/{self.max_retries}), "
 f"retrying in {delay}s: {e}"
 )
 time.sleep(delay)
 
 raise last_exception
 
 def upload(self, project, table, time_period, file_path, action="overwrite"):
 """Upload data with error handling."""
 import urllib.parse
 
 project_enc = urllib.parse.quote(project)
 table_enc = urllib.parse.quote(table)
 
 url = (f"https://{self.customer_id}.apptio.com/biit/api/v1/"
 f"{self.domain}/{project_enc}/{table_enc}/{time_period}/{action}")
 
 with open(file_path, 'rb') as f:
 response = self._make_request("POST", url, files={'myfile': f})
 
 return response.json()
 
 
class AuthenticationError(Exception):
 """Raised when authentication fails or token expires."""
 pass
 
 
# Usage with error handling
def main():
 logging.basicConfig(level=logging.INFO)
 
 client = TBMStudioAPIClient("acme", "acme.com")
 
 try:
 client.authenticate("public_key", "secret_key")
 result = client.upload(
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="data.csv"
 )
 print(f"Upload successful: {result}")
 
 except AuthenticationError:
 print("Authentication failed. Check API credentials.")
 except requests.exceptions.HTTPError as e:
 print(f"API error: {e.response.status_code} - {e.response.text}")
 except Exception as e:
 print(f"Unexpected error: {e}")
```

## Token Refresh Strategy

For long-running processes, implement proactive token refresh:

```
import time
from datetime import datetime, timedelta
 
class TokenManager:
 """Manage API token lifecycle."""
 
 def __init__(self, client, refresh_margin_minutes=5):
 self.client = client
 self.refresh_margin = timedelta(minutes=refresh_margin_minutes)
 self.token_expiry = None
 self.token_lifetime = timedelta(hours=1) # Adjust based on actual expiry
 
 def get_valid_token(self, public_key, secret_key):
 """Get a valid token, refreshing if necessary."""
 now = datetime.now()
 
 if (self.token_expiry is None or 
 now >= self.token_expiry - self.refresh_margin):
 self.client.authenticate(public_key, secret_key)
 self.token_expiry = now + self.token_lifetime
 
 return self.client.token
```

## Logging Best Practices

- **Log all API calls:** Include timestamp, endpoint, HTTP method, and response
  status
- **Log response times:** Monitor for performance degradation
- **Never log credentials:** Redact tokens, API keys, and passwords from logs
- **Log error responses:** Capture full error messages for troubleshooting
- **Use structured logging:** Format logs as JSON for easier parsing and analysis

Warning: Avoid logging sensitive data such as API keys, tokens, or PII. Use
placeholders or hashing for identifiable information in logs.

## Common Pitfalls

- **No retry on 500 errors:** Server errors are often transient. Always implement retry
  with backoff.
- **Ignoring rate limits:** While not explicitly documented, avoid sending requests in
  rapid succession. Add delays between batch operations.
- **Not handling token expiration:** Always handle 401 responses by re-authenticating and
  retrying.
- **Missing error parsing:** Always parse and log the message field from error responses
  for meaningful diagnostics.

**Parent topic:** [API Integration](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
