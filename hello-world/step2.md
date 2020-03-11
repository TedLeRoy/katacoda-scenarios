# Run ssh-keygen for bob.

## Public/Private Key Pair Generation

Running ssh-keygen will do several things for us. It will add a hidden directory to bob's home called .ssh, it will generate a public/private key pair and put them in the .ssh folder, and it will set proper permissions (700 for the directory, and 600 for the files) on those resources.

`ssh-keygen`{{execute T1}}

You'll see the following output:

>bob@host01:~$ ssh-keygen  
>Generating public/private rsa key pair.  
>Enter file in which to save the key (/home/bob/.ssh/id_rsa): **Press Enter**  
>Created directory '/home/bob/.ssh'.  
>Enter passphrase (empty for no passphrase): **Enter passphrase**  
>Enter same passphrase again: **Enter passphrase**  
>Your identification has been saved in /home/bob/.ssh/id_rsa.  
>Your public key has been saved in /home/bob/.ssh/id_rsa.pub.  
>The key fingerprint is:  
>SHA256:f1XXAXgGA5rXwjSDCyI7Fye8cf9cTv3dzBnPFrj9ioM bob@host01  
>The key's randomart image is:  
>+---[RSA 2048]----+  
>|  .     .=.oo... |  
>| . * + .= +..o  o|  
>|  o O oo.+ .+ . +|  
>| o o   o. .o o +.|  
>|  o     S +   =+B|  
>|         + . o +O|  
>|          ...  ..|  
>|          E...  .|  
>|            .... |  
>+----[SHA256]-----+  

Now, we want to see the content of the id_rsa.pub file so we can select and copy it to system two in a later step:

`cat /home/bob/.ssh/id_rsa.pub`{{execute T1}}
