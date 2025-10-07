### SSH to the host

`$ ssh user@ip`

### Create the user as nologin

`$  sudo useradd -s /sbin/nologin username`

Check the user is created,

`$ cat /etc/passwd` user should have `/sbin/login`