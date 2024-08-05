To search exploit from a service and a version:
searchsploit "Samba 3.0.20"
Then search for an exploit in msfconsole:
search < service >
use < position >
Then we list the params:
show options
We check what params are required and we set them with:
set < params name >
Finally we lanch the exploit:
run

Get a nicer shell when being in a reverse shell with nc for instance:
```
python -c 'import pty; pty.spawn("bash")'
```

## Resources

[Get a reverse shell](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)

[List of exploit linux and windows ports and other](https://github.com/rapid7/metasploit-framework/blob/master//modules/exploits/unix/ftp/vsftpd_234_backdoor.rb)

[Help on every HTB machine if stuck](https://0xdf.gitlab.io/2020/04/07/htb-lame.html#beyond-root---vsftpd)