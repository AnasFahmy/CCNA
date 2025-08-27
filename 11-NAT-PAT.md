# NAT & PAT (Overload)

```text
# Inside / outside
interface g0/0
 ip address 10.11.0.1 255.255.255.0
 ip nat inside
interface g0/1
 ip address 203.0.113.2 255.255.255.248
 ip nat outside

# Define interesting traffic
access-list 1 permit 10.11.0.0 0.0.0.255

# PAT
ip nat inside source list 1 interface g0/1 overload

# Static NAT example
ip nat inside source static 10.11.0.10 203.0.113.10

# Verify
show ip nat translations
show ip nat statistics
```