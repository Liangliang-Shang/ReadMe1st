# ReadMe1st
The Beginning of Everything

## ssh

1. on the client, gen rsa keys

   ```bash
   $ ssh-keygen
   Generating public/private rsa key pair.
   ...

   # key pair generated in ~/.ssh
   -rw-------  1 imsha imsha 2.6K Sep 17 08:21 id_rsa     # private-key as a key
   -rw-r--r--  1 imsha imsha  568 Sep 17 08:21 id_rsa.pub # public-key as a lock
   ```

2. on the server, append id_rsa.pub on the client to <user@>server:~user/.ssh/authorized_keys

   ```bash
   $ cat <<EOF >> authorized_keys
   > ssh-rsa ... imsha@lianglis
   > EOF
   ```

3. on the client, log in

   ```bash
   $ ssh <user@>server
   ```

## interactive shell - bash
```bash
$ export TERM=xterm

$ export PS1='\[\033[1;31m\]$(date +%Y.%m.%d) \t\[\033[00m\] | \[\033[32;40m\]\u@\h:$(pwd)\[\033[00m\]\n$ ' || \
> export PS1='\[\033[1;38;5;196;48;5;234m\]\D{%Y.%m.%d} \t\[\033[0m\] | \[\033[1;38;5;28;48;5;234m\]\u@\h:$(pwd)\[\033[0m\]\n$ '
```
