- /etc/default/grub

```
GRUB_CMDLINE_LINUX_DEFAULT
acpi_osi=!Darwin    # Apple ACPI
consoleblank=60     # framebuffer módban 1 perc után elsötétít
libata.force=noncq  # akkor kell, ha SSD fagyás lenne

GRUB_TIMEOUT=1
GRUB_RECORDFAIL_TIMEOUT=5
```
