```
sudo passwd root
sudo visudo
```

/etc/sudoers
```
Defaults	rootpw
james   ALL=(ALL:ALL) NOPASSWD: /usr/sbin/poweroff
```

/etc/polkit-1/localauthority.conf.d/51-ubuntu-admin.conf
```
AdminIdentities=unix-user:root
```
