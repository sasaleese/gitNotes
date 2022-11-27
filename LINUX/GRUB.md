- /etc/default/grub

```
GRUB_CMDLINE_LINUX_DEFAULT

acpi_osi=!Darwin	# Apple ACPI

usb-storage.quirks=152d:9561:u  # AXAGON EE25-A6C UAS driver kikapcsolása

consoleblank=420	# framebuffer módban 7 perc után elsötétít - legyen hosszabb, mint a teljes boot idő, különben részlegesen visszakapcsolja a boot folyamat a képernyőt

video=VGA-1:1280x1024@60 drm.edid_firmware=VGA-1:edid/1280x1024.bin	# grafikus felület van, de 10 mp-enként spam log és képernyőn is spam
nomodeset		# N54L + Benq - nincs spam loggolás de nincs grafikus felület sem
radeon.modeset=0	# ua.

libata.force=noncq	# akkor kell, ha SSD fagyás lenne MacBookban (nincs)

GRUB_TIMEOUT=1
GRUB_RECORDFAIL_TIMEOUT=5
```

- update-grub!
