# homepass

## dependencies
* systemd
* hostapd

## installation
* This package is on the AUR (or will be shortly)

### binaries
```
# cp homepass /usr/bin/
```

### config
```
# mkdir -p /etc/homepass
# cp homepass.conf.example /etc/homepass/homepass.conf
```

### systemd
```
# cp homepass\@.service /etc/systemd/system/
```

## configuration
Edit `/etc/homepass/homepass.conf`

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
# systemctl enable homepass@homepass.conf
# systemctl start homepass@homepass.conf
```
