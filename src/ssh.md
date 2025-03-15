# SSH

# Table of Contents
- [Generating SSH keys](#generating-ssh-keys)
- [Using SSH](#using-ssh)

---

## Generating SSH keys

To generate an SSH key pair, run 
```
ssh-keygen -t ed25519 -C "your_email@example.com"  
```
You can simply press Enter when prompted to accept the default location and filename.  
By default, this will create a `.ssh` folder in your home directory, which contains 2 files. 
- `id_ed25519`: this is your **private** key
- `id_ed25519.pub`: this is your **public** key 

If you see these have been created, then you have succesfully generated an SSH key pair.

Note: on Linux, you must use `ls -a` instead of `ls` in order to see the `.ssh` folder. You can always navigate to it with `cd ~/.ssh`


## Using SSH

**Important:** YOU SHOULD NEVER SHARE YOUR PRIVATE KEY! That's why it's called the *private* key.

When authenticating using SSH, you will need to provide your public key to whichever service you are authenticating with (remote server, GitHub, etc...). "Providing" the key usually consists in copy-pasting it from your .pub file. Once your public key has been stored, your matching private key will effectively be your password.

