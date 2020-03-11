# Troubleshooting and Logs.

## Learn typical hurdles and what logs to check.

We've checked and tested and everything works, but how do you troubleshoot when something doesn't?

My experience indicates it's usually an issue with one of two things:

1. The permissions aren't correct on the _.ssh_ folder or the files it contains. Check the permissions on the system you're SSH'ing **from**.

Permissions on the _.ssh_ folder should be 700. Check this by running `stat -c "%a %n" /home/bob/.ssh`{{execute T1}}

Permissions on the _id_rsa_ and authorized_keys files should be 600. Check by running `stat -c "%a %n" /home/bob/.ssh/id_rsa`{{execute T1}} and `stat -c "%a %n" /home/bob/.ssh/authorized_keys`{{execute T2}}

The _authorized_keys_ file will be on the target system, Terminal 2 in our case.

Permissions on the _id_rsa.pub_ file should be 600. Check by running `stat -c "%a %n" /home/bob/.ssh/id_rsa.pub`{{execute T1}}

If any permissions are incorrect, fix them by running `chmod`. Type `chmod 700 .ssh` to set the permissions on the .ssh folder to 700 for example.

2. The next thing to check is the content of the _authorized_keys_ file. It must be an exact copy of what is in the _id_rsa.pub_ file on system 1. If you suspect something's amiss, it is best to delete the file, assuming you don't have other keys in there, and try again.

Be sure to use the echo command as shown. Using a text editor can introduce unwanted, sometimes invisible characters.

If both of those things are set up correctly, check the entries in `/var/log/auth.log`.

You may want to grep for entries containing fail or the username you're trying to log in with.

You've configured and tested key based authentication on Ubuntu. Great work!
