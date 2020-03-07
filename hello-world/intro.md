<h1>SSH key-based authentication</h1>

<h2>Welcome to the SSH key-based authentication for Ubuntu 18.04 Server scenario!</h2>

SSH is a secure, encrypted protocol for managing remote devices such as Linux and BSD servers and network devices like those made by Cisco and Juniper.

In a default installation on Linux, it uses username and password for authentication.

This is a very insecure way to manage remote authentication and a better option is available to us with just a few steps.

Key-based authentication uses a public key and a private key. Only the public key is exposed and it is useless for authentication without the corresponding private key.

Key-based authentication is much more secure in that the keys generated are nearly impossible to guess, and without them, once you're set up, an attacker won't be able to log in.

If you've never configured key-based authentication for SSH it can be a little confusing.

We'll walk through the process, step-by-step, together here.

<h3>The process is as follows:</h3>

1. Create a non-root user on system one with `adduser`.
2. Add the new user to the _sudo_ group with `usermod`.
3. Switch from root to the new user with `su`.
4. Generate a key pair for the new user with `ssh-keygen`.
5. Print the key to the terminal or standard output with `cat`.
6. Create a non-root user on the second system with the same username with `adduser`.
7. Add the new user on system two to the _sudo_ group with `usermod`.
6. Switch from root to the new user with `su`.
7. Set up directories for keys with `ssh-keygen`.
8. Copy the key on system 1 to the _authorized_keys_ file on system 2 with `echo`.
9. Set permissions on the _authorized_keys_ file to 600 using `chmod`.
10. Test key-based authentication from system one to system two with `ip` and `ssh`.
11. Set system two so it will only accept key-based authentication by editing _/etc/ssh/sshd_config_ with `vim`.
12. Reload the ssh service with `service`.
13. Make sure key-based authentication from system one to system two still works with `ssh`.
14. Make sure privilege elevation still works with `sudo`.
15. Make sure password authentication no longer works by disabling your key and trying to log in.
16. Understand what logs to check for any issues along the way.

This sounds like a lot but we'll get through it pretty quickly!
