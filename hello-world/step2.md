Run ssh-keygen for bob.

## Task

Running ssh-keygen will do several things for us. It will add a hidden directory to bob's home called .ssh, it will generate a public/private key pair and put them in the .ssh folder, and it will set proper permissions (700 for the directory, and 600 for the files) on those resources.

`ssh-keygen`{{execute T1}}

You'll see the following output:
