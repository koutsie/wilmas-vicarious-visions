# Communicating with wilma:

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

#### Unsuccessfull:

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

#### Succesfull:

```
Login=account.namel&SESSIONID=*sessionid*&format=json&ApiKey=sha1%*an hash of the api key[?]&CompleteJson=&Password=*your password lmao* HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Server: Wilma
Date: Thu, 12 Sep 2019 16:40:59 GMT
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
Set-Cookie: Wilma2LoginID=; Path=/; HttpOnly; Secure; Max-Age=0
Set-Cookie: Wilma2SID=*no clue, maybe SignInID?? TODO*; Path=/; HttpOnly; Secure
Content-Length: 33970

{"LoginResult":"Ok","WilmaId":"*TODO*","ApiVersion":9,"FormKey":"student:*","ConnectIds":[],"Name":"Eemeli Examplestudent","Type":2,"PrimusId":*Four letter PrimusID* ,"School":"Cool Exampleschool!" ,"Messages":[{"Id":*Six letter msg-id*,"Subject":"EXAMPLE","TimeStamp":"2019-00-00 00:00","Folder":"inbox","SenderId":*senderid*,"SenderType":1,"Sender":"Teachers Name (ABR)","Status":1},} *< -- + a lot of other data, TODO*
user-agent: Wilma/2.0.android
Connection: keep-alive
Keep-Alive: 60
Content-Type: application/x-www-form-urlencoded
Content-Length: 258
Host: wilmaurl.example.fi
Cookie: Wilma2LangID=3; Wilma2SID=*TODO*
```
