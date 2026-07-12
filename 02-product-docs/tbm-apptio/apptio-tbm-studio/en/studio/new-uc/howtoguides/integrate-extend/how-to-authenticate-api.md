---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To: Authenticate with the API"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
source_path: "studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To: Authenticate with the API

**Objective:** Obtain an authentication token to make authorized API requests

**Time estimate:** 15-30 minutes (first-time setup)

**When to use:** Before any upload or download operation. Tokens are required for all
API calls.

**Prerequisites**

- A user account in Enhanced Access Administration with API access
- API keys generated and granted access to your target environment
- Network access to frontdoor.apptio.com

## Required Permissions

**For upload operations,** your account needs:

- AccessDev
- UploadData

**For download operations,** your account needs:

- AccessProd, AccessStg
- AllDataView, DrillDown
- ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewTransparencyReports,
  ViewUnitReports
- ViewReportsSavedForEveryone

Tip: Some View permissions may not be required depending on the products installed
and data types being downloaded. When in doubt, test your configuration.

## Method 1: Authenticate Using API Keys (Recommended)

API keys are the preferred authentication method for security reasons. They allow
fine-grained access control and can be revoked without changing user passwords.

**Step 1: Generate API keys in Enhanced Access Administration**

1. Log in to Enhanced Access Administration
2. Navigate to your user account settings
3. Generate a new API key pair (public and secret)
4. Click Grant Access next to the key name to authorize environment access
5. Store the secret key securely—it cannot be retrieved after creation

**Step 2: Request an authentication token**

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
 -H "Content-Type: application/json" \
 -H "Accept: application/json" \
 -d '{"keyAccess":"YOUR_PUBLIC_KEY","keySecret":"YOUR_SECRET_KEY"}'
```

**Python:**

```
import requests
import json
 
def get_auth_token(public_key, secret_key):
 """Authenticate with TBM Studio API using API keys."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 headers = {
 "Content-Type": "application/json",
 "Accept": "application/json"
 }
 payload = {
 "keyAccess": public_key,
 "keySecret": secret_key
 }
 
 response = requests.post(url, headers=headers, json=payload)
 response.raise_for_status()
 
 # Token is returned in cookies
 token = response.cookies.get('apptio-opentoken')
 return token
 
# Usage
token = get_auth_token("your_public_key", "your_secret_key")
```

**Step 3: Get your Environment ID**

The environment ID is required for subsequent API calls. It remains constant unless your
Enhanced Access Administration configuration changes.

```
curl -X GET "https://frontdoor.apptio.com/api/environment/yourdomain.com/main" \
 -H "Content-Type: application/json" \
 -H "apptio-opentoken: YOUR_TOKEN"
```

**Python:**

```
def get_environment_id(token, domain, frontdoor_env="main"):
 """Get the environment ID for API calls."""
 url = f"https://frontdoor.apptio.com/api/environment/{domain}/{frontdoor_env}"
 headers = {
 "Content-Type": "application/json",
 "apptio-opentoken": token
 }
 
 response = requests.get(url, headers=headers)
 response.raise_for_status()
 
 return response.json()["id"]
 
# Usage
env_id = get_environment_id(token, "yourdomain.com")
```

## Method 2: Authenticate Using Username/Password

Warning: Username/password authentication is supported but not recommended for
production systems. Use API keys when possible for better security.

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"userId":"user@domain.com","password":"your_password"}'
```

**Python:**

```
def get_auth_token_password(user_id, password):
    """Authenticate using username and password."""
    url = "https://frontdoor.apptio.com/service/apikeylogin"
    headers = {
        "Content-Type": "application/json",
        "Accept": "application/json"
    }
    payload = {
        "userId": user_id,
        "password": password
    }
    
    response = requests.post(url, headers=headers, json=payload)
    response.raise_for_status()
    
    return response.cookies.get('apptio-opentoken')
```

## Expected Results

- Successful authentication returns an apptio-opentoken in the response cookies
- The environment ID endpoint returns a JSON response containing the numeric environment
  ID
- Both values are required for all subsequent API operations

## Common Pitfalls

- **Key not granted environment access:** After creating an API key, you must
  explicitly grant it access to environments via the Grant Access link.
- **Missing permissions:** Ensure the UploadData permission is assigned.
- **Token expiration:** Authentication tokens expire. Implement token refresh logic in
  long-running processes.

**Parent topic:** [API Integration](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
