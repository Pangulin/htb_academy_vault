
we can use linux variables and take certain strings out of it to get a character we want

echo ${PATH}
/home/htb-ac-1022206/.pyenv/shims:/home/htb-ac-1022206/.pyenv/bin:/home/htb-ac-1022206/.local/bin:/snap/bin:/usr/sandbox/:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/usr/share/games:/usr/local/sbin:/usr/sbin:/sbin:/usr/share:/usr/share/john:/opt/mssql-tools/bin:/snap/bin:/usr/local/sbin:/usr/sbin:/sbin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/opt/xplico/bin:/opt/xplico/bin

example for getting a / :
echo ${PATH:0:1}
/


example for ; : 
```shell-session
echo ${LS_COLORS:10:1}

;
```

