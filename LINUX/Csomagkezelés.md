# Felhasználó által telepített csomagok

Ubuntu

```
comm -23 <(apt-mark showmanual | sort -u) <(gzip -dc /var/log/installer/initial-status.gz | sed -n 's/^Package: //p' | sort -u)
```

OpenWRT


```
ls /overlay/upper/usr/lib/opkg/info/*.list | sed -e 's/.*\///' | sed -e 's/\.list//'
```
