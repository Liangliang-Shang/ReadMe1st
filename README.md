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
