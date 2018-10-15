# setup bash (quick'n'dirty)

```sh
# disable freeze / ctrl + s
echo "stty -ixon" >> .bashrc

# alias
echo "alias ll='ls -l'" >> .bashrc
echo "alias la='ls -A'" >> .bashrc
echo "alias l='ls -CF'" >> .bashrc

# alias clear
echo "alias c='clear'" >> .bashrc
```

also use this

    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\] : \[\033[01;34m\]\w\[\033[00m\]\n\$ '

    # for root
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\] : \[\033[01;34m\]\w\[\033[00m\]\n\$ '