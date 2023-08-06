# bash_hints
collection of bash commands which may be useful
<br>
<br>
<br>
<br>
Sort a file (which has content per line) and then output as single line

```sort file | tr '\n' ' '```

Words seperated by spaces in a file - convert to per line and sorted

```cat /tmp/ubuntu_pkgs |  tr " " "\n" | sort```

Copy ACL

```getfacl source-folder | setfacl --set-file=- target-folder```

Replace with sed recursively (from current directory)

```find . -type f -exec sed -i 's/old/new/g' {} +```
