# OSPFv2 (IPv4) & OSPFv3 (IPv6)

## Wildcard Mask (WCM) = 255.255.255.255 − netmask
- /24 mask 255.255.255.0 → WCM 0.0.0.255

## OSPFv2 (process-id is local)
```text
router ospf 1
 router-id 1.1.1.1
 network 10.4.4.0 0.0.0.3 area 0
 network 10.3.3.0 0.0.0.255 area 0
 passive-interface default
 no passive-interface g0/0
!
interface g0/0
 ip ospf 1 area 0      # interface-based alternative
```

## OSPFv3 (IPv6)
```text
ipv6 unicast-routing
interface g0/0
 ipv6 address 2001:db8:1::1/64
 ipv6 ospf 10 area 0
!
router ospf 10
 router-id 1.1.1.1
```

> Area 0 is the backbone; all other areas must connect to it (directly or via ABR).