# shomepass
A systemd homepass homepass implementation

## dependencies
* systemd
* hostapd

## installation
* This package is on the AUR (or will be shortly)
 
### manual installation
#### arch linux
```
$ makepkg -is
```

#### other linux
##### binaries
```
# cp shomepass /usr/bin/
```

##### config
```
# mkdir -p /etc/shomepass
# cp shomepass.conf.example /etc/shomepass/shomepass.conf
```

##### systemd
```
# cp shomepass.service /etc/systemd/system/
```

## configuration
Edit `/etc/shomepass/shomepass.conf`

This file is a hostapd configuration file. The fields of interest are the bridge, channel and mac address filtering fields.

Make sure the configured bridge has internet access. 

### systemd.network example
#### /etc/systemd/network/br0.netdev
```
[NetDev]
Name=br0
Kind=bridge
```

#### /etc/systemd/network/br0.network
```
[Match]
Name=br0

[Network]
DHCP=yes
```

#### /etc/systemd/network/eth0.network
```
[Match]
Name=eth0

[Network]
Bridge=br0
```

## running
```
# systemctl enable shomepass
# systemctl start shomepass
```
