# Creating a user, _bob_ on terminal 1.

### Add user _bob_ on terminal 1.

We'll add a user, _bob_ to Terminal 1 with the `adduser` command.

**Click on the code snippet below to execute it on Terminal Host 1.**

`adduser bob`{{execute T1}}

**Click in the Terminal Host 1 window to the right.**

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

Your user, _bob_ has been created on Terminal 1.

### Add privilege elevation to _bob's_ account

Add _bob_ to the sudo group so he can elevate privileges when needed with `usermod`.

`usermod -aG sudo bob`{{execute T1}}

### Change from _root_ to _bob_

Change from running as _root_ to run as _bob_ using the substitute user identity `su` command.

`su - bob`{{execute T1}}

In the next step, we'll create _bob's_ public/private key pair with `ssh-keygen`.
