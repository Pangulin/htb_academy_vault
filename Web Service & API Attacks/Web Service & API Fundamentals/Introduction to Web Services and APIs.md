Web services enable applications to communicate with each other. The applications can be entirely different. Consider the following scenario:

- One application written in Java is running on a Linux host and is using an Oracle database
- Another application written in C++ is running on a Windows host and is using an SQL Server database


## Web Service vs. API

---

The terms `web service` and `application programming interface (API)` should not be used interchangeably in every case.

- Web services are a type of application programming interface (API). The opposite is not always true!
- Web services need a network to achieve their objective. APIs can achieve their goal even offline.
- Web services rarely allow external developer access, and there are a lot of APIs that welcome external developer tinkering.
- Web services usually utilize SOAP for security reasons. APIs can be found using different designs, such as XML-RPC, JSON-RPC, SOAP, and REST.
- Web services usually utilize the XML format for data encoding. APIs can be found using different formats to store data, with the most popular being JavaScript Object Notation (JSON).

## Web Service Approaches/Technologies

---

There are multiple approaches/technologies for providing and consuming web services:

- `XML-RPC`
    
    - [XML-RPC](http://xmlrpc.com/spec.md) uses XML for encoding/decoding the remote procedure call (RPC) and the respective parameter(s). HTTP is usually the transport of choice.
    - Code: http
        
        ```
        http
          --> POST /RPC2 HTTP/1.0
          User-Agent: Frontier/5.1.2 (WinNT)
          Host: betty.userland.com
          Content-Type: text/xml
          Content-length: 181
        
          <?xml version="1.0"?>
          <methodCall>
            <methodName>examples.getStateName</methodName>
            <params>
               <param>
         		     <value><i4>41</i4></value>
         		     </param>
        		  </params>
            </methodCall>
        
          <-- HTTP/1.1 200 OK
          Connection: close
          Content-Length: 158
          Content-Type: text/xml
          Date: Fri, 17 Jul 1998 19:55:08 GMT
          Server: UserLand Frontier/5.1.2-WinNT
        
          <?xml version="1.0"?>
          <methodResponse>
             <params>
                <param>
        		      <value><string>South Dakota</string></value>
        		      </param>
          	    </params>
           </methodResponse>
        ```

