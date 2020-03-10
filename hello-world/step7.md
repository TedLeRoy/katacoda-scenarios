# Make sure only key-based authentication will work.

## Change permissions on your authorized_keys file to break key-based auth then try to log in.

We know key based authentication works, but what if the key is broken or the user doesn't have it? How can we see that the user will not simply be promted for a password?

We'll move the `authorized_keys` file up one directory, then try to login to see.

`sudo mv /home/bob/.ssh/authorized_keys ../`{{execute T2}}

Now, if you were connected from Terminal 1 to Terminal 2 over SSH, close that connection by typing `exit`.

If you made the change directly on Terminal 2, go to Terminal 1 and try to connect over SSH.

`ssh bob@[[HOST2_IP]]`{{execute}}

You should receive an error saying `Permission denied (publickey).`

That means a user without a key will not be able to try and enter a password, so this is working as we hoped it would.

Change permissions back to the correct setting:

`sudo mv /home/bob/authorized_keys /home/bob/.ssh/`{{execute T2}}

Make sure SSH is working again.

`ssh bob@[[HOST2_IP]]`{{execute}}

In the next lesson, we'll see common things to check if you're having any problems.
