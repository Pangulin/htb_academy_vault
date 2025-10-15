## What are Injections

|Injection|Description|
|---|---|
|OS Command Injection|Occurs when user input is directly used as part of an OS command.|
|Code Injection|Occurs when user input is directly within a function that evaluates code.|
|SQL Injections|Occurs when user input is directly used as part of an SQL query.|
|Cross-Site Scripting/HTML Injection|Occurs when exact user input is displayed on a web page.|
## OS Command Injections

#### PHP Example

For example, a web application written in `PHP` may use the `exec`, `system`, `shell_exec`, `passthru`, or `popen` functions to execute commands directly on the back-end server, each having a slightly different use case. The following code is an example of PHP code that is vulnerable to command injections:

Code: php

```php
<?php
if (isset($_GET['filename'])) {
    system("touch /tmp/" . $_GET['filename'] . ".pdf");
}
?>
```

Perhaps a particular web application has a functionality that allows users to create a new `.pdf` document that gets created in the `/tmp` directory with a file name supplied by the user and may then be used by the web application for document processing purposes. However, as the user input from the `filename` parameter in the `GET` request is used directly with the `touch` command (without being sanitized or escaped first), the web application becomes vulnerable to OS command injection. This flaw can be exploited to execute arbitrary system commands on the back-end server.
#### NodeJS Example

This is not unique to `PHP` only, but can occur in any web development framework or language. For example, if a web application is developed in `NodeJS`, a developer may use `child_process.exec` or `child_process.spawn` for the same purpose. The following example performs a similar functionality to what we discussed above:

Code: javascript

```javascript
app.get("/createfile", function(req, res){
    child_process.exec(`touch /tmp/${req.query.filename}.txt`);
})
```

The above code is also vulnerable to a command injection vulnerability, as it uses the `filename` parameter from the `GET` request as part of the command without sanitizing it first. Both `PHP` and `NodeJS` web applications can be exploited using the same command injection methods.

