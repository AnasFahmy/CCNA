# DHCP Server (IOS)

```text
ip dhcp excluded-address 10.11.0.1 10.11.0.20
ip dhcp pool LAN11
 network 10.11.0.0 255.255.255.0
 default-router 10.11.0.1
 dns-server 8.8.8.8
 domain-name lab.local
```