# Create a user, *bob* on terminal 2.

### Add user *bob* on terminal 2.

We'll add a user, *bob* to Terminal 2 with the `adduser` command.

`adduser bob`{{execute T2}}

You'll see the following:

>Adding user 'bob' ...  
>Adding new group 'bob' (1001) ...  
>Adding new user 'bob' (1001) with group 'bob' ...  
>Creating home directory '/home/bob' ...  
>Copying files from '/etc/skel' ...  
>Enter new UNIX password: **enter your password**  
>Retype new UNIX password: **repeat your password**  
>passwd: password updated successfully  
>Changing the user information for bob  
>Enter the new value, or press ENTER for the default  
>        Full Name []: **press Enter**  
>        Room Number []: **press Enter**  
>        Work Phone []: **press Enter**  
>        Home Phone []: **press Enter**  
>        Other []: **press Enter**  
>Is the information correct? [Y/n] **press Enter**  

Your user, *bob* has been created on Terminal 2.

### Add privilege elevation to _bob's_ account

Add *bob* to the sudo group so he can elevate privileges when needed with `usermod`.

`usermod -aG sudo bob`{{execute T2}}

### Change from *root* to *bob*

Change from running as *root* to run as *bob* using the substitute user identity `su` command.

`su - bob`{{execute T2}}

In the next step, we'll create *bob's* public/private key pair and set up his directory and file permissions on System 2 with `ssh-keygen`.
