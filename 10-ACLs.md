# ACLs (Standard & Extended)

## Rules of thumb
1. Decide **permit/deny** logic first.
2. Apply to **interface + direction**.
3. Implicit **deny all** at the end.
4. Standard ACLs filter **source** only — place **near destination**.
5. Extended ACLs filter source/destination/ports — place **near source**.

## Standard (numbered 1–99)
```text
access-list 10 permit 10.11.0.0 0.0.0.255
access-list 10 deny any
interface g0/0
 ip access-group 10 in
```

## Standard (named)
```text
ip access-list standard USERS_OK
 permit 10.11.0.0 0.0.0.255
 deny any
interface g0/0
 ip access-group USERS_OK in
```

## Extended (numbered 100–199)
```text
access-list 101 permit tcp 10.11.0.0 0.0.0.255 any eq 80
access-list 101 deny ip any any
interface g0/1
 ip access-group 101 out
```

## Extended (named)
```text
ip access-list extended WEB_ONLY
 permit tcp 10.11.0.0 0.0.0.255 any eq 80
 deny ip any any
interface g0/1
 ip access-group WEB_ONLY out
```

Notes:
- ICMP is ping.
- Use `show access-lists` and `show ip interface` to verify.
- For VTY restriction:
```
ip access-list standard MGMT
 permit 10.5.5.0 0.0.0.255
line vty 0 4
 access-class MGMT in
 transport input ssh
 login local
```