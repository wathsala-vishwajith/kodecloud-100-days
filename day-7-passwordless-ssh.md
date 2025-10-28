1. On the Jump Host (as user)
Log in to the jump host as the user.

Step 1: Generate an SSH Key Pair

`ssh-keygen -t rsa`

2. On Each Application Server (App Server 1, 2, 3, etc.)
For each application server, you must copy thor's public key to the corresponding sudo user's authorized_keys file.

Example for App Server 1 (Sudo User: user2)

The most common and easiest way is to use the ssh-copy-id command from the jump host.

Step 1: Use ssh-copy-id
Run this command from the jump host as the thor user, replacing <AppServer1_IP> with the actual IP address or hostname of App Server 1.


`ssh-copy-id user2@<AppServer1_IP>`

When prompted, you will need to enter the password for user2 on App Server 1 the first time only. This command automatically does the following:

* Connects to the remote user.

* Creates the ~/.ssh directory if it doesn't exist.

* Sets the correct permissions on ~/.ssh. (chmod 700)

* Appends the content of thor's public key (~/.ssh/id_rsa.pub) to user2's ~/.ssh/authorized_keys file.

3. Test the Setup (from Jump Host as thor)

`ssh user2@<AppServer1_IP>`

If the connection is successful without a password prompt, the password-less authentication is correctly configured, and your automation scripts can now run seamlessly.