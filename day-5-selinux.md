### Configuring SELinux


For CentOS/RHEL/Fedora:


```
sudo yum install -y policycoreutils-python-utils # (or selinux-policy, or libselinux-utils if needed)

# A simple yum/dnf command is usually sufficient to ensure dependencies are met.
```
For Debian/Ubuntu:

```
sudo apt-get update
sudo apt-get install -y selinux-utils # If SELinux is not already installed
```

<b> Disable SELinux </b>

`sudo vi /etc/selinux/config`

```# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
```
