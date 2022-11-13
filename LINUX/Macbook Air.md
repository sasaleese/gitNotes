## Energiagazdálkodás

- /etc/default/grub
```
GRUB_CMDLINE_LINUX_DEFAULT="
acpi_osi=!Darwin    # Apple ACPI
consoleblank=60     # framebuffer módban 1 perc után elsötétíteni
libata.force=noncq  # akkor kell, ha SSD fagyás lenne

GRUB_TIMEOUT=1
GRUB_RECORDFAIL_TIMEOUT=1
```

- SSD energiamegtakarító mód spindown nélkül
  - Gnome Disks appban 128-ra állítjuk az APM-et

```
crontab -e
@reboot	echo "ondemand" | tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor >/dev/null 2>&1
```

- /etc/sysctl.d/disable_watchdog.conf

```
kernel.nmi_watchdog = 0
```

- szenzorok
```
sudo apt install lm-sensors
sudo echo drivetemp >> /etc/modules
```

- ventillátor profil állítása
```
sudo apt install mbpfan
sudo nano /etc/mbpfan.conf
```


## Headless mód
- /etc/systemd/logind.conf
```
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
```

- Extensions
- Extension Manager
  - Allow Locked Remote Desktop
  - Freon

```
systemctl set-default multi-user.target
```
