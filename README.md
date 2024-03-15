# bash_hints
collection of bash commands which may be useful
<br>
<br>
<br>
<br>
Assign date to variable, useful for scripts

``DATE_OF_RUN=$(date +%F_%H_%M)``

Date X days ago

``date +%Y-%m-%d -d '1 day ago'``

Find files using newer modification time than X days ago.

``find /directory -newermt $(date +%Y-%m-%d -d 'X day ago') -type f``


Sort a file (which has content per line) and then output as single line

```sort file | tr '\n' ' '```

Words seperated by spaces in a file - convert to per line and sorted

```cat /tmp/ubuntu_pkgs |  tr " " "\n" | sort```

Copy ACL

```getfacl source-folder | setfacl --set-file=- target-folder```

Replace with sed recursively (from current directory)

```find . -type f -exec sed -i 's/old/new/g' {} +```

Find and count files in directories... using a CWD, which ONLY contains directories (note the ls -1 used to feed from CWD).

```ls -1 | while read -r dir; do printf "%s:\t" "$dir"; find "$dir" -type f | wc -l; done```

Add first colume of numbers in file without using bc, but awk

```awk '{s+=$1} END {print s}' some_filename```

...an alternative to the last command, numbers printed for each line and final total.

```awk '{ sum+=$1;print $1} END {print "Sum";print sum}' some_filename```


ps - Show top10 CPU utilisation, all processes, apply formatting

``ps -Ao user:50,uid,comm,pid,pcpu,tty --sort=-pcpu | head ``

iostat

``iostat -kxh``

clear page cache (sudo/root)

``sync; echo 1 > /proc/sys/vm/drop_caches``
