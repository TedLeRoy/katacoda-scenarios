# Eliminate Password Authentication for SSH.

## Edit /etc/ssh/sshd_config to only allow key-based authentication.

Now we'll make a copy of the original `sshd_config` file, then edit the original to disallow password authentication.

If you still have an SSH session open from Terminal 1 to Terminal 2, you can use that by running the commands on Terminal 1. If not, just start the SSH session back up:

`ssh bob@[[HOST2_IP]]`{{execute T1}}

Copy the `/etc/ssh/sshd_config` file to a backup file so you'll have it if you need to restore it:

`sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.0`

If prompted for a password, enter bob's Terminal 1 password to confirm that you have sudo privileges.

Edit the original /etc/ssh/sshd_config file with vim:

`sudo vim /etc/ssh/sshd_config`{{execute T1}}

When the file opens, look for the following lines:

