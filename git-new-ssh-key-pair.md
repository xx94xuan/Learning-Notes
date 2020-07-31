1. Generate the new ssh key.   
  `$ ssh-keygen -t rsa -b 4096 -C "example.com"`
2. Adding ssh key to ssh-agent.   
  `$ eval "$(ssh-agent -s)"`
3. Modify `~/.ssh/config` to auto load keys into ssh-agent and store passphrases in keychain.    
  `$ touch ~/.ssh/config`
```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```
4. Add ssh private key to ssh-agent.   
 `$ ssh-add -K ~/.ssh/id_rsa`
5. Add ssh key to your github account.   
 copy the key: `$ pbcopy < ~/.ssh/id_rsa.pub`
6. github webpage -> settings -> ssh and GPG keys -> add ssh key -> YES!That's IT!    
7. `git clone xxxxxx`   
