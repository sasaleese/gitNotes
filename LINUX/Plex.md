```
curl https://downloads.plex.tv/plex-keys/PlexSign.key  | sudo tee /etc/apt/trusted.gpg.d/plex.asc
echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
sudo apt install plexmediaserver
```
