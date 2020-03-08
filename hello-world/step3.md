# Creating a user, _bob_ on terminal 2.

### Add user _bob_ on terminal 2.

We'll add a user, _bob_ to Terminal 2 with the `adduser` command.

**Click on the code snippet below to execute it on Terminal Host 2.**

`adduser bob`{{execute T2}}

**Click in the Terminal Host 2 window to the right.**

**Provide the requested input where you see double asterisks in the output as below.**

You'll see the following:

`Adding user 'bob' ...
Adding new group 'bob' (1001) ...
Adding new user 'bob' (1001) with group 'bob' ...
Creating home directory '/home/bob' ...
Copying files from '/etc/skel' ...
Enter new UNIX password: **enter your password**
Retype new UNIX password: **repeat your password**
passwd: password updated successfully
Changing the user information for bob
Enter the new value, or press ENTER for the default
        Full Name []: **press Enter**
        Room Number []: **press Enter**
        Work Phone []: **press Enter**
        Home Phone []: **press Enter**
        Other []: **press Enter**
Is the information correct? [Y/n] **press Enter**`

Your user, _bob_ has been created on Terminal 2.

### Add privilege elevation to _bob's_ account

Add _bob_ to the sudo group so he can elevate privileges when needed with `usermod`.

`usermod -aG sudo bob`{{execute T2}}

### Change from _root_ to _bob_

Change from running as _root_ to run as _bob_ using the substitute user identity `su` command.

`su - bob`{{execute T2}}

In the next step, we'll create _bob's_ public/private key pair and set up his directory and file permissions on T2 with `ssh-keygen`.
