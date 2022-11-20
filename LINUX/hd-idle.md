```
wget http://adelolmo.github.io/andoni.delolmo@gmail.com.gpg.key -O /etc/apt/trusted.gpg.d/hd-idle.asc
echo "deb http://adelolmo.github.io/$(lsb_release -cs) $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/adelolmo.github.io.list
sudo apt update
sudo apt install hd-idle
```

/etc/default/hd-idle

```
START_HD_IDLE=true
HD_IDLE_OPTS="-c ata -i 0 -a /dev/disk/by-label/LABEL -i 540 -l /var/log/hd-idle.log"
```

Sharkoon Rapid-Case 3.5 eSATA
- hd-idle-vel biztosan működik

Axagon EE25-XA3 (ASM1153)
- hd-idle (-c ata)
- ne pont 10 perc legyen, mert 10 percnél nem működik (a ház is akkor altatná be és race condition lesz pont??)
- (Gnome Disk APM 1, spindown 9 minutes??
- vagy crontab -e -> @reboot /usr/sbin/hdparm -B1 -S108 /dev/disk/by-label/LABEL??)
