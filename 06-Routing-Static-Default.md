# Static & Default Routes (IPv4)

```text
# Interfaces
interface fa0/1
 ip address 10.4.4.2 255.255.255.252
 no shut
interface fa1/0
 ip address 10.4.4.10 255.255.255.252
 no shut
interface fa1/1
 ip address 10.3.3.1 255.255.255.0
 no shut
```

## Static route forms
```text
ip route 10.2.2.0 255.255.255.0 10.4.4.2        # via next-hop
ip route 10.2.2.0 255.255.255.0 fa0/1           # via exit int
ip route 10.2.2.0 255.255.255.0 fa0/1 10.4.4.2  # fully specified
ip route 10.2.2.10 255.255.255.255 fa0/1 10.4.4.2   # host route

# Floating static (higher AD)
ip route 10.2.2.0 255.255.255.0 10.4.4.2 5      # AD=5

# Default route
ip route 0.0.0.0 0.0.0.0 10.4.4.1
```

> Routing table only keeps the **best** routes (lowest AD, best metric).