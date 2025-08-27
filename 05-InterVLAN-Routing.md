# Inter-VLAN Routing (Router-on-a-Stick)

```text
# On switch: trunk to router
interface g0/1
 switchport mode trunk

# On router: subinterfaces
interface g0/1.11
 encapsulation dot1Q 11
 ip address 10.11.0.1 255.255.255.0
interface g0/1.22
 encapsulation dot1Q 22
 ip address 10.22.0.1 255.255.255.0
```