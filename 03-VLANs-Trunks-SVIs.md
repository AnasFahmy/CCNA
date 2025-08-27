# VLANs, Trunks, SVIs, DTP

## Create VLANs
```text
vlan 11
 name Users
vlan 22
 name Voice
vlan 33
 name Servers
vlan 44
 name Guests
```

## Access ports
```text
interface range fa0/3-6
 switchport mode access
 switchport access vlan 11
 spanning-tree portfast
 spanning-tree bpduguard enable
```

## Trunk ports
```text
interface fa0/0
 switchport mode trunk
 switchport trunk allowed vlan 1,11,22,33
 # prevent VLAN 44 on this trunk
 switchport nonegotiate       # (disable DTP)
```

## Display port switchport info
```text
show interfaces fa0/8 switchport
```

## SVI (Switch Virtual Interface) for mgmt
```text
interface vlan 1
 ip address 10.5.5.5 255.0.0.0
 no shutdown
ip default-gateway 10.5.5.1
```

> Fix typos: `switchport` is one word; `nonegotiate` (not nonegotitate).