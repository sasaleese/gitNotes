- dropbear helyett openssh-server és openssh-client

- helyi gépen
```
ssh-keygen -b 4096
ssh-copy-id user@server.ip

cat ~/.ssh/id_rsa.pub | ssh user@server.ip "mkdir ~/.ssh; cat >> ~/.ssh/authorized_keys"
```
