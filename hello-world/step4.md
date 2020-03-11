# Run ssh-keygen for bob on Terminal 2.

## Public/Private Key Pair Generation and Folder Setup

Running *ssh-keygen* will do several things for us. It will add a hidden directory to bob's home called *.ssh*, it will generate a public/private key pair and put them in the *.ssh* folder, and it will set proper permissions (700 for the directory, and 600 for the files) on those resources.

`ssh-keygen`{{execute T2}}

You'll see the following output:

>bob@host02:~$ ssh-keygen  
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

Now, we want to copy the content of *id_rsa.pub* on Terminal 1 to the *authorized_keys* file in the *.ssh* folder on this system.

On Terminal 1, select the text that was output when the cat command was run. It will look something like this: 

>ssh-rsa >AAAAB3NzaC1yc2EAAAADAQABAAABAQCostLDIrveyujCUMuJkO42ifDEG7FMhAPEKJmX8dXIUavZiccLUgnf1X9syMR7YYzWdpz9GXI62Va/z5zW8ITRaOWHsJ18h+MpDfk+9qBEeiBydLFo0rzSSJDmZTpbLVOpkQ2LYgSy0eouPtNTFRvaRLXjaQb01WCMneXMmun33w1CvNgOEWQb/d4iUO2ylKz20CvacfwctKgjROG3ZDtgv9D0S6+xCsx7gEOMVcuVxaA58NH5b9p55qNue9DNT3l4oNRPJQ5MY+HyQp3YZoTb3eesyhz+/WALyR7XQ29QhGNTu9RMkpQl/IB6YrTNHX7jpp2humRfzTzx0m1JDjgt bob@host01

Be sure to select everything from `ssh-rsa...` to `...bob@host01` inclusive.

Hit `ctrl-c` to copy your selection to your operating system's clipboard.

Type `echo '<paste key here by typing ctrl-v>' >> /home/bob/.ssh/authorized_keys` on **Terminal 2**.

In our example, it will look like this:

`echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCostLDIrveyujCUMuJkO42ifDEG7FMhAPEKJmX8dXIUavZiccLUgnf1X9syMR7YYzWdpz9GXI62Va/z5zW8ITRaOWHsJ18h+MpDfk+9qBEeiBydLFo0rzSSJDmZTpbLVOpkQ2LYgSy0eouPtNTFRvaRLXjaQb01WCMneXMmun33w1CvNgOEWQb/d4iUO2ylKz20CvacfwctKgjROG3ZDtgv9D0S6+xCsx7gEOMVcuVxaA58NH5b9p55qNue9DNT3l4oNRPJQ5MY+HyQp3YZoTb3eesyhz+/WALyR7XQ29QhGNTu9RMkpQl/IB6YrTNHX7jpp2humRfzTzx0m1JDjgt bob@host01' >> /home/bob/.ssh/authorized_keys`

Be sure to have single quotes around the key. Do not type the less than and greater than signs between the single quotes. The only thing inside the signle quotes should be the exact content of the key generated on Terminal 1.

This will create an *authorized_keys* file if it does not already exist and add the key from Terminal 1 to it, or append it to existing content if the file already exists.

Now, change directory to your *.ssh* folder then change the permissions on the *authorized_keys* file to `600`.

`cd /home/bob/.ssh`{{execute T2}}

`chmod 600 authorized_keys`{{execute T2}}

Next, we'll make sure key-based authentication is working for *bob* from Terminal 1 to Terminal 2.
