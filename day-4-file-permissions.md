### linux file permissons

Linux file permissions are a fundamental security mechanism controlling access to files and directories. They are based on three permission types and three user categories: 
1. Permission Types:
Read (r):
Files: Allows viewing the contents of a file.
Directories: Allows listing the contents of a directory.
Write (w):
Files: Allows modifying or deleting the file.
Directories: Allows creating, deleting, or renaming files within the directory (requires execute permission as well).
Execute (x):
Files: Allows running a file as a program or script.
Directories: Allows traversing into the directory (e.g., using cd) and accessing metadata about its contents.
2. User Categories:
Owner (u): The user who owns the file or directory.
Group (g): The group associated with the file or directory.
Others (o): All other users on the system not in the owner or group categories.
3. Representation:
Permissions can be represented in two main ways:
Symbolic: Uses letters (r, w, x) for each permission and user category (e.g., rwxr-xr-x).
Octal (Numeric): Assigns a numerical value to each permission (read=4, write=2, execute=1) and sums them for each user category (e.g., 755 for rwxr-xr-x).
4. Commands:
chmod: Used to change file and directory permissions.
chown: Used to change the owner of a file or directory.
chgrp: Used to change the group owner of a file or directory.
umask: Determines the default permissions for newly created files and directories.
5. Special Permissions:
SetUID (SUID): When set on an executable file, it allows users to run the file with the permissions of the file owner.
SetGID (SGID): When set on an executable file, it allows users to run the file with the permissions of the file's group. When set on a directory, new files and subdirectories created within it inherit the group ownership of the parent directory.
Sticky Bit: When set on a directory, it prevents users from deleting or renaming files within that directory unless they own the file or the directory.