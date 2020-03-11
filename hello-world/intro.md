# SSH key-based authentication

## Welcome to the SSH key-based authentication for Ubuntu Server scenario!

### Problem

SSH is a secure, encrypted protocol for managing remote devices such as Linux and BSD servers and network devices like those made by Cisco and Juniper from a command line terminal emulator.

In a default installation on Linux, it uses username and password for authentication.

Usernames and passwords can be gleaned in many ways including brute force if the system is not set up proplerly or through password re-use if your credentials are compromised elsewhere. Username and password authentication is a very insecure way to manage remote authentication and a better option is available to us with just a few steps.

### Solution

Key-based authentication uses a public key and a private key. Only the public key is exposed and it is useless for authentication without the corresponding private key.

Key-based authentication is much more secure in that the keys generated are nearly impossible to guess, and without them, once you're set up, an attacker won't be able to log in.

If you've never configured key-based authentication for SSH it can be a little confusing.

We'll walk through the process, step-by-step, together here.

### Discussion

The steps to configure key-based authentication are highlighted below and we'll do each in this scenario:

1. Create a non-root user on system one
    1. Creatre user _bob_ with `adduser` 
    2. Add the _bob_ to the _sudo_ group with `usermod`
    3. Switch from root to the new user with `su`
2. Generate a key pair _bob_ on system one
    1. Create key with `ssh-keygen`
    2. List key contents with `cat`
3. Create a non-root user on system two 
    1. Create user _bob_ `adduser`
    2. Add the _bob_ to the _sudo_ group with `usermod`
    3. Switch from root to the new user with `su`
4. Set up directories for keys with `ssh-keygen`
    1. Copy the key on system 1 to the _authorized_keys_ file on system 2 with `echo`
    2. Set permissions on the _authorized_keys_ file to 600 using `chmod`
5. Test key-based authentication from system one to system two with `ssh`
6. Set system two so it will only accept key-based authentication 
    1. Make a backup copy of /etc/ssh/sshd_cofnig_ with cp
    2. Edit _/etc/ssh/sshd_config_ with `vim`
    3. Save changes
    4. Reload ssh with `service`
    5. Be sure ssh still works
7. Make sure password authentication no longer works by disabling your key and trying to log in.
8. Understand common problems and what logs to check for any issues along the way.

This sounds like a lot but we'll get through it pretty quickly!

This scenario can be found here: https://www.katacoda.com/theo1.
