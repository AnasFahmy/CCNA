# Port Security (Access Edge)

```text
interface fa0/10
 switchport mode access
 switchport access vlan 11
 switchport port-security
 switchport port-security maximum 2
 switchport port-security violation restrict
 switchport port-security mac-address sticky
show port-security interface fa0/10
```