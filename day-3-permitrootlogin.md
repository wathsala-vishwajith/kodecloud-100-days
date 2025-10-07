### Restrict Root Login on SSH

Edit `/etc/ssh/sshd_config` to `PermitRootLogin no` 

Restart sshd
`sudo systemctl restart sshd` or `sudo service sshd restart`.
