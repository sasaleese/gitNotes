```
wget http://adelolmo.github.io/andoni.delolmo@gmail.com.gpg.key -O /etc/apt/trusted.gpg.d/hd-idle.asc
echo "deb http://adelolmo.github.io/$(lsb_release -cs) $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/adelolmo.github.io.list
sudo apt update
sudo apt install hd-idle
```

/etc/default/hd-idle

```
START_HD_IDLE=true
HD_IDLE_OPTS="-i 0 -a /dev/disk/by-label/LABEL -i 600 -l /var/log/hd-idle.log"
```
