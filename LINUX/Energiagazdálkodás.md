# Energiagazdálkodás

# Macbook Air 6,1 (mid-2013)

- watchdog kikapcsolása

- Intel energiagazdálkodás kikapcsolható - nem érzékeli a szenzorokat vmiért

- mbpfan

- 15-ös Intel Energy Performance Bias?

- Gnome - Power Saver?

- Gnome Disks - APM=128

# HP N54L

- watchdog kikapcsolása

- Intel energiagazdálkodás kikapcsolható - AMD CPU

- javasolt scaling governor - ondemand?


---

### Watchdog kikapcsolása
/etc/sysctl.d/disable_watchdog.conf
`kernel.nmi_watchdog = 0`

### Intel energiagazdálkodás kikapcsolása
`sudo systemctl disable thermald.service`

### Scaling governor beállítása

- schedutil - default
- powersave - kevésbé agresszív energiamegtakarítás
- ondemand - legnagyobb energiamegtakarítás, de okozhat bugokat - [`https://wiki.archlinux.org/title/CPU_frequency_scaling#Troubleshooting`](https://wiki.archlinux.org/title/CPU_frequency_scaling#Troubleshooting)

1. cpupower-gui - governor, minimum és maximum CPU sebesség állítása

2. crontab

`@reboot	echo "ondemand" | tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor >/dev/null 2>&1`

### Intel Energy Performace Balance
- crontab

`@reboot echo "15" | tee /sys/devices/system/cpu/cpu*/power/energy_perf_bias`

```
 0 - performance
 4 - balance-performance
 6 - normal (default)
 8 - balance-power
15 - power
```

### MBPfan
```
sudo apt install mbpfan
```

/etc/mbpfan.conf

```
min_fan1_speed = 1200	# put the *lowest* value of "cat /sys/devices/platform/applesmc.768/fan*_min"
max_fan1_speed = 6500	# put the *highest* value of "cat /sys/devices/platform/applesmc.768/fan*_max"
low_temp = 55			# try ranges 55-63, default is 63
high_temp = 58			# try ranges 58-66, default is 66
max_temp = 86			# take highest number returned by "cat /sys/devices/platform/coretemp.*/hwmon/hwmon*/temp*_max", divide by 1000
polling_interval = 5	# default is 1 seconds
```

# Státusz lekérdezések

### aktív scaling driverek?
`cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_driver`

### aktív scaling governor?
`cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor`

### lehetséges governorok?
`cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors`

### aktív Intel Energy Performance Bias?
`cat /sys/devices/system/cpu/cpu*/power/energy_perf_bias`

# Hasznos

- powertop
- [`https://wiki.archlinux.org/title/CPU_frequency_scaling`](https://wiki.archlinux.org/title/CPU_frequency_scaling)
- [`https://forum.proxmox.com/threads/c-states-not-working.72630/
`](https://forum.proxmox.com/threads/c-states-not-working.72630/)
