GRUB_CMDLINE_LINUX_DEFAULT

```
consoleblank=60     # framebuffer módban 1 perc után elsötétít
```

- /etc/systemd/logind.conf

```
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
```

- Extensions
- Extension Manager
  - Allow Locked Remote Desktop

```
systemctl set-default multi-user.target
```
