# Bash
# Flags
_Modifiers that will change how a Bash command operates._
Flags will typically be placed after a command and will start with a dash.  
- `-`: single dashes are used for single character flags.
- `--`: double dashes are used for descriptive flags.
- **Combination**: some operations allow single character flag combos  `ls -l -a` -> `ls -la`.
- The order of the flags matters in how it changes the operation.

---
# History Commands
_Commands and shortcuts that will interact with previous terminal inputs._
The **History List** is a list of text in the terminal.  
- `!n`: runs the nth command in the history list.
- `!-n`: Runs the command from n commands ago.
- `!<command>`: Runs the most recent command that starts with `<command>`.
- `^old^new`: Re-runs the last command, but replaces `old` with `new`.

---
# Navigation Operations
_Operations involved in navigating through directories and files._
## pwd 
_Outputs the current working directory._
## export
_Outputs all environment variables._
``` BASH
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R
```

---
## whatis _keyword_
_Outputs manual information on `keyword`._
> - `(1)`: User commands
> - `(3)`: Library calls
> - `(3x)`: Extended library calls
``` BASH
$ whatis echo
...wait(1), where(1), which(1), while(1) - shell built-in commands
echo(1)                  - write arguments to the standard output
```

## whereis _keyword_
_Outputs the file path of `keyword`._
``` BASH
$ whereis flutter
flutter: /Users/willschmitz/development/flutter/bin/flutter
```

---
## which _executable_
_Outputs the full path location of `executable`._
> Can use `command` to find its location.
``` BASH
$ which php
/c/xampp/php/php
```

---
## clear
_Removes all text displayed on terminal._
``` BASH
$ clear

```

---
## grep _search_term_, _file_
_Outputs lines that match a specified pattern._

> `flags`:  
> - `-i` case insensitive
> - `-r` Recursively search directories.
> - `-n` Show line numbers with output lines
> - `-c` Count the number of matching lines
> - `-v` Invert the match; show non-matching lines
> - `-E` Interpret pattern as an extended regular expression
``` BASH
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
