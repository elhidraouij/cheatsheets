# Linux

## Networking commands

### 1. Debian based distributions

#### a. Configure with _ip_ command

`ip a`  
`ip addr add [ipv4_adress] dev [interface_name]`  
`ip addr del [ipv4_adress] dev [interface_name]`

`ip link set dev [interface_name] up`  
`ip link set dev [interface_name] down`

`ip link set dev [interface_name] address [new_mac_address]`
`ip link set dev [interface_name] name [new_interface_name]`

#### b. Configure with _netplan_

`nano /etc/netplan/[file].yaml`

```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    interface_name:
      dhcp4: no|yes
      dhcp6: no|yes
      addresses:
        - 172.16.0.1/24
      gateway4: 172.16.0.3/24
      nameservers:
        addresses:
          - 8.8.8.8
          - 4.4.4.4
```

`sudo netplan apply`

#### c. Configure with _systemd-networkd_

`nano /etc/systemd/network/[interface_name].network`

```
[Match]
Name=[interface_name]

[Network]
Address=192.168.1.1
Gateway=192.168.1.254
DNS=8.8.8.8

[Route]
Destination=192.168.2.0/24
Gateway=192.168.1.100
```

Allow ip forwarding `sudo nano /etc/sysctl.conf` by uncommenting `net.ipv4.ip_forward=1`