```
{
    "alt-speed-down": 50,
    "alt-speed-enabled": false,
    "alt-speed-time-begin": 540,
    "alt-speed-time-day": 127,
    "alt-speed-time-enabled": false,
    "alt-speed-time-end": 1020,
    "alt-speed-up": 50,
    "bind-address-ipv4": "0.0.0.0",
    "bind-address-ipv6": "::",

    "blocklist-enabled": true,
    "blocklist-url": "https://github.com/Naunter/BT_BlockLists/raw/master/bt_blocklists.gz",

    "cache-size-mb": 4,

    "dht-enabled": false,					# priv

    "download-dir": "/Download",

    "download-limit": 100,
    "download-limit-enabled": 0,
    "download-queue-enabled": true,
    "download-queue-size": 5,

    "encryption": 2,						# require encryption

    "idle-seeding-limit": 30,
    "idle-seeding-limit-enabled": false,
    "incomplete-dir": "/var/lib/transmission-daemon/Downloads",
    "incomplete-dir-enabled": false,
    "lpd-enabled": no,						# csak ha több kliens fut a LAN-on
    "max-peers-global": 200,
    "message-level": 1,						# Error
    "peer-congestion-algorithm": "",				# https://www.irif.fr/~jch//software/bittorrent/tcp-congestion-control.html
    "peer-id-ttl-hours": 6,
    "peer-limit-global": 200,
    "peer-limit-per-torrent": 50,

    "peer-port": 15951,

    "peer-port-random-high": 65535,
    "peer-port-random-low": 49152,
    "peer-port-random-on-start": false,
    "peer-socket-tos": "default",				# lowcost?

    "pex-enabled": false,					# peer felderítés lassabb/gyorsabb

    "port-forwarding-enabled": false,				# uPNP?
    "preallocation": 1,						# 1 - gyors, 2 -teljes (kevesebb töredezettség)
    "prefetch-enabled": true,					# router - false; x86 = true
    "queue-stalled-enabled": true,
    "queue-stalled-minutes": 30,

    "ratio-limit": 1.1,
    "ratio-limit-enabled": true,

    "rename-partial-files": true,

    "rpc-authentication-required": false,

    "rpc-bind-address": "0.0.0.0",
    "rpc-enabled": true,
    "rpc-host-whitelist": "",

    "rpc-host-whitelist-enabled": false,

    "rpc-password": "",

    "rpc-port": 9091,
    "rpc-url": "/transmission/",
    "rpc-username": "transmission",

    "rpc-whitelist": "",
    "rpc-whitelist-enabled": false,

    "scrape-paused-torrents-enabled": false,

    "script-torrent-done-enabled": false,
    "script-torrent-done-filename": "",
    "seed-queue-enabled": false,
    "seed-queue-size": 10,
    "speed-limit-down": 100,
    "speed-limit-down-enabled": false,

    "speed-limit-up": 3,
    "speed-limit-up-enabled": true,

    "start-added-torrents": true,
    "trash-original-torrent-files": false,

    "umask": 0,							# json-ban 10-es a számrendszer - umask octális "022" = 18

    "upload-limit": 100,
    "upload-limit-enabled": 0,
    "upload-slots-per-torrent": 14,
    "utp-enabled": true						# Micro Transport Protocol látencia és congestio javítására
}
```
