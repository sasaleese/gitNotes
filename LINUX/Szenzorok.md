# CPU sebesség

`watch -n.1 "grep \"^[c]pu MHz\" /proc/cpuinfo"`

# Hőmérsékletek

```
sudo apt install lm-sensors
sudo sensors-detect
```

```
echo drivetemp | sudo tee -a /etc/modules
```

# GUI

- Extensions
- Extension Manager
  - Freon
