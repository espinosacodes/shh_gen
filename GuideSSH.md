# SSH key 
Generating an SSH Key Pair 

This command creates an SSH key pair using the ed25519 algorithm, which is a modern and secure option.
-t ed25519: Specifies the key type as ed25519.
-f ~/.ssh/id_ed25519: Sets the filename for the private key to id_ed25519 in your ~/.ssh directory (the hidden SSH configuration directory in your home directory).
Upon running this command:

```
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519

```
You'll be prompted to enter a secure passphrase for your private key. This passphrase is like a password that protects your key. Choose a strong and unique passphrase that you can remember.
You'll see a progress bar as the key is generated.
Two files will be created in your ~/.ssh directory:
id_ed25519 (private key): Keep this file secure! Never share it with anyone.
id_ed25519.pub (public key): This is the key you'll add to GitHub.

Starting the SSH Agent

This command starts the SSH agent, a program that temporarily stores your private key in memory so you can avoid entering your passphrase repeatedly for SSH connections during your current session.
eval is used to execute the output of the ssh-agent -s command, which sets environment variables for the agent.
```
eval "$(ssh-agent -s)" 
```
Verifying the Key Addition 

The SSH agent is a program that runs in the background and securely manages your private key during your current terminal session.
```
ssh-add ~/.ssh/id_ed25519
```
Copying the Public Key 

```
cat ~/.ssh/id_ed25519.pub
```

Adding the Public Key to GitHub:

Go to your GitHub account settings.
Navigate to the "SSH and GPG keys" section.
Click "New SSH key" and paste the copied public key into the "Key" field.
Provide a descriptive title for your key (e.g., "My Personal Machine").
Click "Add SSH key".
Now, when you connect to a GitHub repository using SSH, you'll be able to authenticate securely without entering your password, as long as the SSH agent is running and has your private key loaded.
