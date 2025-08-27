# STP (PVST+/Rapid-PVST) & EtherChannel (LACP)

## Concepts refresher
- Bridge ID (BID) = priority + MAC. Lowest wins **Root Bridge**.
- Root Port: lowest cost **toward** the root (one per non-root switch).
- Designated Port: one per link/segment.
- Classic timers: MaxAge 20s, Listening 15s, Learning 15s, Forwarding.
- Rapid-PVST converges faster.

## Verify and tune
```text
show spanning-tree
spanning-tree mode rapid-pvst
spanning-tree vlan 1 priority 12288            # prefer as root
spanning-tree vlan 1 root primary               # macro to set low priority
interface fa0/8
 spanning-tree vlan 1 cost 45
interface fa0/1
 spanning-tree portfast
 spanning-tree bpduguard enable
```

## EtherChannel (LACP)
```text
interface range g0/1 - 2
 channel-group 1 mode active       # LACP active
 switchport mode trunk
 switchport trunk allowed vlan 1,11,22,33
!
interface port-channel 1
 switchport mode trunk
 switchport trunk allowed vlan 1,11,22,33
```