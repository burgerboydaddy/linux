## Command that updates all expired keys in ubuntu:

```
sudo apt-key list | \
 grep "expired: " | \
 sed -ne 's|pub .*/\([^ ]*\) .*|\1|gp' | \
 xargs -n1 sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys
```

Run this first, 
then sudo apt-get update 
and then sudo apt-get dist-upgrade
