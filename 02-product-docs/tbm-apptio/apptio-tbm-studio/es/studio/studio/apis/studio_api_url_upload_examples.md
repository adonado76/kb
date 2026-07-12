---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "API URL ejemplos de carga"
breadcrumb: []
source_path: "studio/studio/apis/studio_api_url_upload_examples.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL ejemplos de carga

**Se aplica a** : v11.x, v12.0, v12.1, v12.2+

## cURL ejemplo

```
curl -k -F myfile@filename.csv -u‘datalinkuser@customer.com:password’
‘https://customer.apptio.com/biit/api/v1/customer.com/
Project%20Name/Data+set+name/current/overwrite’
```

## Ejemplo Java 1

```
import org.apache.commons.httpclient.HttpClient;
import org.apache.commons.httpclient.MultiThreadedHttpConnectionManager;
import org.apache.commons.httpclient.UsernamePasswordCredentials;
import org.apache.commons.httpclient.auth.AuthScope;
import org.apache.commons.httpclient.methods.PostMethod;
import org.apache.commons.httpclient.methods.multipart.FilePart;
import org.apache.commons.httpclient.methods.multipart.MultipartRequestEntity;
import org.apache.commons.httpclient.params.HttpConnectionManagerParams;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.UnsupportedEncodingException;
import java.net.URLEncoder;
public class ApiExample {
protected static final HttpClient client = new HttpClient( new
MultiThreadedHttpConnectionManager() );
static { HttpConnectionManagerParams params = new HttpConnectionManagerParams();
params.setDefaultMaxConnectionsPerHost( 20 ); params.setMaxTotalConnections( 20 );
client.getHttpConnectionManager().setParams( params ); System.setProperty(
"org.apache.commons.logging.Log", "org.apache.commons.logging.impl.SimpleLog" ); System.setProperty(
"org.apache.commons.logging.simplelog.showdatetime", "true" ); System.setProperty(
"org.apache.commons.logging.simplelog.log.httpclient.wire", "debug" ); System.setProperty(
"org.apache.commons.logging.simplelog.log.org.apache.commons.httpclient", "debug" ); } public static
void main( String args[] ) throws UnsupportedEncodingException, FileNotFoundException { String
username = args[ 0 ]; String password = args[ 1 ]; String clientid = args[ 2 ]; String domain =
args[ 3 ]; String project = args[ 4 ]; String table = args[ 5 ]; String date = args[ 6 ]; String
action = args[ 7 ]; String filename = args[ 8 ]; project = URLEncoder.encode( project, "UTF-8" );
table = URLEncoder.encode( table, "UTF-8" ); PostMethod postMethod = new PostMethod( "https://" +
clientid + ".apptio.com/biit/api/v1/" + domain + "/" + project + "/" + table + "/" + date + "/" +
action );
client.getState().setCredentials( new AuthScope( clientid + ".apptio.com", 443, "Apptio REST API"
), new UsernamePasswordCredentials( username, password ) );
FilePart filePart = new FilePart( filename, new File( filename ) ); postMethod.setRequestEntity(
new MultipartRequestEntity( new FilePart[] { filePart }, postMethod.getParams() ) ); int statusCode
= 0; try { statusCode = client.executeMethod( postMethod ); } catch ( IOException e ) {
System.out.println( e.getMessage() ); e.printStackTrace(); }
return; } }
```

## Ejemplo Java 2

```
import com.apptio.automation.common.data.datadriven.util.TestDataHolder;
import com.apptio.automation.common.utilities.datalink.DataLinkTestAPIV1;
import com.apptio.automation.common.utilities.datalink.Status;
import org.testng.annotations.AfterTest;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;
import java.io.IOException;
import java.util.HashMap;
import static org.testng.Assert.assertEquals;
import static org.testng.Assert.assertTrue;
public class Sample_DataLinkTestAPIV1 {
private TestDataHolder testDataHolder;
public Sample_DataLinkTestAPIV1() {
testDataHolder = new TestDataHolder();
try {
testDataHolder.addDataFromTextFile("dataLink.csv", '|');
} catch(IOException e) {
assertTrue(false);
}
}
@DataProvider(name = "dataLinkDataProvider", parallel = true)
public Object[][] getTestData() {
return testDataHolder.getAllDataRows();
}
@Test(enabled = true, dataProvider = "dataLinkDataProvider")
public void testMultipleUpload(HashMap<String,
String> parameterValues) throws IOException, InterruptedException {
String username = parameterValues.get("username");
String password = parameterValues.get("password");
String serverName = parameterValues.get("serverName");
int serverPort = Integer.valueOf(parameterValues.get("serverPort"));
String domain = parameterValues.get("targetDomain");
String project = parameterValues.get("targetProject");
String table = parameterValues.get("targetTable");
String date = parameterValues.get("targetDate");
String action = parameterValues.get("action");
String filename = parameterValues.get("filename");
int expectedCode = Integer.valueOf(parameterValues.get("expectedCode"));
String expectedMessage = parameterValues.get("expectedMessage");
DataLinkTestAPIV1 dataLink = new DataLinkTestAPIV1(serverName, serverPort, username, password);
Status status = dataLink.upload(domain, project, table, date, action, filename);
assertEquals(status.getCode(), expectedCode);
assertEquals(status.getMessage(), expectedMessage);
dataLink.storeToLocal(filename);
assertEquals(dataLink.verify(domain, project, table, date), expectedMessage);
}
}
```

## Ejemplo en C

```
using System;
using System.Net;
using System.Threading;
using System.Security.Cryptography.X509Certificates;
using System.Net.Security;
namespace API-Demo
{
class MainClass
{
public static bool TrustAllCertificatesCallback(object sender, X509Certificate cert, X509Chain
chain, SslPolicyErrors errors)
{
return true;
}
public static string baseUrl = "https://customer.apptio.com/biit/api";
public static void Main(string[] args)
{
ServicePointManager.ServerCertificateValidationCallback = TrustAllCertificatesCallback;
string username = args.Length > 0 ? args[0] : "api@customer.com";
string password = args.Length > 1 ? args[1] : "Password!1";
string domain = args.Length > 0 ? args[2] : "customer.com";
string project = args.Length > 0 ? args[3] : "someproject";
string date = args.Length > 0 ? args[4] : "January:2000";
string tableName = args.Length > 0 ? args[5] : "tableName";
string action = args.Length > 0 ? args[6] : "overwrite";
string file = args.Length > 0 ? args[7] : "C\\:data.csv";
Boolean retry = true;
do
{
WebClient client = new WebClient();
client.Credentials = new NetworkCredential(username, password);
try {\\
client.UploadFile(baseUrl + "/v1/" + domain + "/" + project + "/" + tableName + "/" + date + "/"
+ action, file);
retry = false;
}
catch (WebException e)
{
Console.WriteLine("This program is expected to throw WebException on successful run." +
"\n\nException Message :" + e.GetBaseException().Message);
if (e.Status == WebExceptionStatus.ProtocolError)
{
Console.WriteLine("Status Code :{0}", ((HttpWebResponse)e.Response).StatusCode);
Console.WriteLine("Status Description :{0}",
((HttpWebResponse)e.Response).StatusDescription);
}
}
catch (Exception e)
{
Console.WriteLine(e);
}
Thread.Sleep(5000);
} while (retry);
}
}
}
```

## Python ejemplo

```
#! /usr/bin/env python
# -*- coding: iso-8859-1 -*-
# vi:ts=4:et
import os, sys
import pycurl
# Class which holds a file reference and the read callback
class FileReader:
def __init__(self, fp):
self.fp = fp
def read_callback(self, size):
return self.fp.read(size)
password = sys.argv[1];
domain = sys.argv[2];
project = sys.argv[3];
date = sys.argv[4];
tableName = sys.argv[5];
action = sys.argv[6];
file = sys.argv[7];
baseUrl = "https://customer.apptio.com/biit/api";
url = baseUrl + "/v1/" + domain + "/" + project + "/" + tableName + "/" + date + "/" +
action;
if not os.path.exists(file):
print "Error: the file '%s' does not exist" % file
raise SystemExit
# Initialize pycurl
c = pycurl.Curl()
c.setopt(pycurl.URL, url)
c.setopt(pycurl.UPLOAD, 1)
# Two versions with the same semantics here, but the filereader version
# is useful when you have to process the data which is read before returning
if 1:
c.setopt(pycurl.READFUNCTION, FileReader(open(file, 'rb')).read_callback)
else:
c.setopt(pycurl.READFUNCTION, open(filename, 'rb').read)
# Set size of file to be uploaded.
filesize = os.path.getsize(filename)
c.setopt(pycurl.INFILESIZE, filesize)
# Start transfer
print 'Uploading file %s to url %s' % (filename, url)
c.perform()
c.close()
```
