# Pool
- root:root
- rwxrwxr-x

# subdirectories
- james:users
- directories 2775
- files 664

# csak fájlok
- find . -type f -print0 | xargs -0 chmod 664
