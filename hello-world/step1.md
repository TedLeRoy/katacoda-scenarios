Adding a user to Terminal 1.

## Task

We'll add a user, _bob_ to Terminal 1 with the **adduser** command.

`adduser bob`{{execute T1}}

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

Change from running as _root_ to run as _bob_ using the substitute user identity _su_ command.

`su - bob`{{execute T1}}
