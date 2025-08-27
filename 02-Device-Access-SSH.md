# Local User, Console/VTY, and SSH

## Local user + privilege
```text
username admin secret Pa55w0rd
enable secret S3cure!
```

## Console & VTY login
```text
line console 0
 login local
 logging synchronous
 exec-timeout 10 0
line vty 0 4
 login local
 transport input ssh    # disable telnet
```

## SSH v2 setup
```text
ip domain-name lab.local
crypto key generate rsa modulus 2048
ip ssh version 2
ip ssh time-out 60
ip ssh authentication-retries 3
```

> Fix typo from notes: `enable`, `configure terminal` (not *enavle config tr*).