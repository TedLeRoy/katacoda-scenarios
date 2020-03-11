# Eliminate Password Authentication for SSH.

## Edit */etc/ssh/sshd_config* to only allow key-based authentication.

Now we'll make a copy of the original *sshd_config* file, then edit the original to disallow password authentication.

Copy the */etc/ssh/sshd_config* file to a backup file so you'll have it if you need to restore it:

`sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.0`{{execute T2}}

If prompted for a password, enter *bob's* Terminal 2 password to confirm that you have sudo privileges.

Edit the original */etc/ssh/sshd_config* file with vim:

`sudo vim /etc/ssh/sshd_config`{{execute T2}}

When the file opens, look for the following lines:

`PermitRootLogin prohibit-password
...
ChallengeResponseAuthentication no
...
PasswordAuthentication yes`

Hit "i" to enter insert mode in vim.

Edit `PermitRootLogin prohibit-password` to read `PermitRootLogin no`.

Ensure `ChallengeResponseAuthentication no` is set. If not, change whatever follows to `no`.

Change `PasswordAuthentication yes` to `PasswordAuthentication no`.

**If any of the lines you're editing have a pound sign (#) in front of them remove it to uncomment the line.**

Save your changes by hitting the Escape key, then typing colon followed by w then q. `:wq`.

Reload the SSH service:

`sudo service ssh reload`{{execute T2}}

In the next step, we'll make sure password authentication no longer works.
