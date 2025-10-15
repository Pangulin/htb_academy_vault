to test for SSRF we can use this: 

api=http://127.0.0.1/index.php and see if it reflects the index page 



Exploitation: 

sometimes we can do a file read exploitation: 

api=file:///etc/passwd