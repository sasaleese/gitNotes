# smb.conf szűrése

`egrep -v "^$|^[[:space:]]*#" /etc/samba/smb.conf`

# user management

```
smbpasswd -a samba_user		- user hozzáadása
smbpasswd samba_user		- user password változtatása
smbpasswd -x samba_user		- user eltávolítása
pdbedit -L -v					- userek listázása
```

---

# Ubuntu

```
[global]
	fruit:model = MacBookAir6,1 / MacPro

	fruit:encoding = native
	fruit:metadata = stream
	fruit:veto_appledouble = no
	vfs objects = catia fruit streams_xattr io_uring
   
	netbios name = HOSTNAME
	; wsdd2 hostname parameter

	interfaces = enx0017890116f1 / enp2s0
	bind interfaces only = yes
	deadtime = 15	
	enable core files = no
	security = user
	invalid users = root
	null passwords = yes
	socket options = IPTOS_LOWDELAY TCP_NODELAY SO_KEEPALIVE
	load printers = No
	printcap name = /dev/null
	disable spoolss = yes
	printing = bsd
	mdns name = mdns
	veto files = /Thumbs.db/.DS_Store/._.DS_Store/.apdisk/
	delete veto files = yes
	use sendfile = Yes
	disable netbios = Yes
	smb ports = 445
	unix password sync = no
   
   workgroup = WORKGROUP
   ; wsdd2 workgroup parameter
   server string = %h server (Samba, Ubuntu)
;   interfaces = 127.0.0.0/8 eth0
;   bind interfaces only = yes
   log file = /var/log/samba/log.%m
   max log size = 1000
   logging = file
   panic action = /usr/share/samba/panic-action %d
   server role = standalone server
   obey pam restrictions = yes
   
;   unix password sync = yes
   
   passwd program = /usr/bin/passwd %u
   passwd chat = *Enter\snew\s*\spassword:* %n\n *Retype\snew\s*\spassword:* %n\n *password\supdated\ssuccessfully* .
   pam password change = yes
   map to guest = bad user
;   logon path = \\%N\profiles\%U
;   logon drive = H:
;   logon script = logon.cmd
; add user script = /usr/sbin/adduser --quiet --disabled-password --gecos "" %u
; add machine script  = /usr/sbin/useradd -g machines -c "%u machine account" -d /var/lib/samba -s /bin/false %u
; add group script = /usr/sbin/addgroup --force-badname %g
;   include = /home/samba/etc/smb.conf.%m
;   idmap config * :              backend = tdb
;   idmap config * :              range   = 3000-7999
;   idmap config YOURDOMAINHERE : backend = tdb
;   idmap config YOURDOMAINHERE : range   = 100000-999999
;   template shell = /bin/bash
   usershare allow guests = yes
;[homes]
;   comment = Home Directories
;   browseable = no
;   read only = yes
;   create mask = 0700
;   directory mask = 0700
;   valid users = %S
;[netlogon]
;   comment = Network Logon Service
;   path = /home/samba/netlogon
;   guest ok = yes
;   read only = yes
;[profiles]
;   comment = Users profiles
;   path = /home/samba/profiles
;   guest ok = no
;   browseable = no
;   create mask = 0600
;   directory mask = 0700
;[printers]
;   comment = All Printers
;   browseable = no
;   path = /var/spool/samba
;   printable = yes
;   guest ok = no
;   read only = yes
;   create mask = 0700
;[print$]
;   comment = Printer Drivers
;   path = /var/lib/samba/printers
;   browseable = yes
;   read only = yes
;   guest ok = no
;   write list = root, @lpadmin

[SHARE]
	path = /SHARE
	create mask = 0664
	directory mask = 2775
	read only = no
	guest ok = yes
	inherit owner = yes
	
[TEMP]
	path = /TEMP
	create mask = 0666
	directory mask = 0777
	read only = no
	guest ok = yes
	inherit owner = yes
```

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
