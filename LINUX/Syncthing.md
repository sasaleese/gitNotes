```
echo "deb https://apt.syncthing.net/ syncthing stable" | sudo tee /etc/apt/sources.list.d/syncthing.list
curl -s https://syncthing.net/release-key.txt | sudo tee /etc/apt/trusted.gpg.d/syncthing.asc
```

```
/lib/systemd/system/syncthing@.service

ExecStartPre=/usr/bin/sleep 60
```
