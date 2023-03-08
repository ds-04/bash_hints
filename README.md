# bash_hints
collection of bash commands which may be useful
<br>
<br>
<br>
<br>
Sort a file (which has content per line) and then output as single line

```sort file | tr '\n' ' '```

Copy ACL

```getfacl source-folder | setfacl --set-file=- target-folder```
