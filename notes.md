# helpful command line commands and notes
+ home and root dirs
```bash
~/ # user home dir
/ # filesystem root dir
```

# terminal settings (rc)
+ Cat it:
```bash
cat ~/.zshrc
```
+ May add aliases
```bash
alias ll="ls -la"        # now typing 'll' runs 'ls -la'
alias gs="git status"    # 'gs' becomes a shortcut for 'git status'
```
+ Or declare more complicated function compositions:
```bash
mkcd() { mkdir -p "$1" && cd "$1"; }   # make a folder and immediately go into it
```
+ May update PATH variable
```bash
export PATH="$PATH:/my/tools"
```

# ssh
+ Generate an ssh key
```bash
ssh-keygen -t ed25519 -f ~/.ssh/my_key
```
+ Ordinary ssh command:
```bash
ssh alice@192.168.1.100 -p 2222 -i ~/.ssh/my_key
```
+ There are two ssh config files:
    + ~/.ssh/config
    + /etc/ssh/ssh_config
+ Config files contain host blocks, e.g.:
```bash
Host myserver
    HostName 192.168.1.100
    User alice
    Port 2222
    IdentityFile ~/.ssh/my_key
```
+ Host blocks permit aliasing of the ssh command via:
```bash
ssh myserver
```