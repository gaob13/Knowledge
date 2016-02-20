#public key
The first thing you’ll need to do is make sure you’ve run the keygen command to generate the keys:
```
    ssh-keygen -t rsa
```  
Then use this command to push the key to the remote server, modifying it to match your server name.
```
    cat ~/.ssh/id_rsa.pub | ssh user@hostname 'cat >> .ssh/authorized_keys'
```
#Config
```
Host *
  Compression yes
  ServerAliveInterval 60
  ServerAliveCountMax 5
  ControlMaster auto
  ControlPath /tmp/sockets/%r@%h-%p
  ControlPersist 4h
```
