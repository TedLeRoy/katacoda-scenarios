# Test key-based authentication.

## Connect from Terminal 1 to Terminal 2 with SSH using keys.

Now that we've configured the keys, let's make sure they work.

`ssh bob@[[HOST2_IP]]`{{execute T1}}

If this is the first time you've connected to the remote system, you'll be prompted to accept its fingerprint. Just type yes and press Enter.

You'll then be prompted to enter the password you used to protect your key.

Enter that password.

You should be authenticated.

The process should look similar to the following:

`bob@host01:~$ ssh bob@172.17.0.21
The authenticity of host '172.17.0.21 (172.17.0.21)' can't be established.
ECDSA key fingerprint is SHA256:SK3U6gPvlomtsq58aKe9c+9I+Lro0A8IyEdbF6rDJ7c.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '172.17.0.21' (ECDSA) to the list of known hosts.
Enter passphrase for key '/home/bob/.ssh/id_rsa': **Enter the password you put on your key**

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.`

In the next step, we'll configure the sshd_config file so the system will no longer accept password authentication.
