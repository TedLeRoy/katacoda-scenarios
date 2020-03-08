# Test key-based authentication.

## Connect from Terminal 1 to Terminal 2 with SSH using keys.

Now that we've configured the keys, let's make sure they work.

`ssh bob@[[HOST2_IP]]`{{execute T1}}

You'll be prompted to enter the password you used to protect your key.

Enter that password.

You should be authenticated.

In the next step, we'll configure the sshd_config file so the system will no longer accept password authentication.
