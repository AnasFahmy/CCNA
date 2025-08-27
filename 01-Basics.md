# IOS Basics & Housekeeping

```text
# Enter privileged exec
enable

# Enter global config
configure terminal    # or: conf t

# Hostname
hostname R1

# Save & reload
copy running-config startup-config   # or: write memory
reload

# Erase configs (lab only)
write erase
delete vlan.dat
reload

# Timestamps & encryption
service timestamps log datetime msec
service password-encryption

# Banners
banner motd ^ Authorized access only! ^
```

### Interfaces
```text
interface GigabitEthernet0/0
 description To-LAN
 ip address 10.1.1.1 255.255.255.0
 no shutdown
exit
```

### Useful `show`
```text
show running-config
show ip interface brief
show interfaces status
show version
show cdp neighbors detail
show lldp neighbors detail
```