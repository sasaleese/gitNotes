```
echo "deb https://downloads.plex.tv/repo/deb public main" | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
curl https://downloads.plex.tv/plex-keys/PlexSign.key  | sudo tee /etc/apt/trusted.gpg.d/plex.asc

sudo apt update
sudo apt install plexmediaserver
```
