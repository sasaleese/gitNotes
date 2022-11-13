`egrep -v "^$|^[[:space:]]*#" /etc/samba/smb.conf`

# OpenWRT
- Force synchronous I/O - On lower-end devices may increase speeds, by forceing synchronous I/O instead of the default asynchronous.
- Enable macOS compatible shares - Enables Apple's AAPL extension globally and adds macOS compatibility options to all shares.
- Disable Netbios

```
[global]
	fruit:model = AirPort
	netbios name = HOSTNAME
	interfaces = br-lan 
	server string = Samba on OpenWRT
	unix charset = UTF-8
	workgroup = WORKGROUP
	bind interfaces only = yes
	deadtime = 15
	enable core files = no
	security = user
	invalid users = root
	map to guest = Bad User
	null passwords = yes
	passdb backend = smbpasswd
	socket options = IPTOS_LOWDELAY TCP_NODELAY
	load printers = No
	printcap name = /dev/null
	disable spoolss = yes
	printing = bsd
	mdns name = mdns
	veto files = /Thumbs.db/.DS_Store/._.DS_Store/.apdisk/
	delete veto files = yes
	disable netbios = yes
	smb ports = 445
	aio read size = 0
	aio write size = 0

[SHARE]
	path = /SHARE
	create mask = 0666
	directory mask = 0777
	read only = no
	guest ok = yes
	fruit:encoding = native
	fruit:metadata = stream
	fruit:veto_appledouble = no
	vfs objects = catia fruit streams_xattr 
```
