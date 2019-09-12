# Heres a request example:

```
GET /index_json?langid=3 HTTP/1.1
user-agent: Wilma/2.0.android
Connection: keep-alive
Keep-Alive: 60
Host: wilmaurl.example.fi
```


##### We'll use the `Wilma/2.0.android` to appear as the wilma app.

### The response looks something like this:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Server: Wilma
Date: Thu, 12 Sep 2019 00:00:00 GMT
Connection: keep-alive
Accept-Ranges: none
Access-Control-Allow-Origin: *
X-XSS-Protection: 1; mode=block
Cache-Control: private, no-cache, no-store, must-revalidate, max-age=0
Pragma: no-cache
Vary: *
Allow: GET, POST
Referrer-Policy: same-origin
Strict-Transport-Security: max-age=31536000; includeSubDomains
Content-Security-Policy: upgrade-insecure-requests
X-Frame-Options: sameorigin
X-Content-Type-Options: nosniff
Set-Cookie: Wilma2LangID=3; Path=/; HttpOnly; Secure
Set-Cookie: Wilma2LoginID=*your 12 character wilmaloginID*; Path=/; HttpOnly; Secure
Content-Length: 79
```

### Data within that login may vary:

```
{"LoginResult":"Failed","SessionID":"*this seems to be the same 12 char wilmaloginID*","ApiVersion":9,"Workers":[]}POST /login HTTP/1.1
user-agent: Wilma/2.0.android
Connection: keep-alive
Keep-Alive: 60
Content-Type: application/x-www-form-urlencoded
Content-Length: 143
Host: wilmaurl.example.fi
Cookie: Wilma2LangID=3; Wilma2LoginID=*your 12 character wilmaloginID*
```
