```

enable
configure terminal
service dhcp

(VLAN 10)
ip dhcp excluded-address 192.168.10.1 192.168.10.10
ip dhcp pool VLAN10
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

(VLAN 20)
ip dhcp excluded-address 192.168.20.1 192.168.20.10
ip dhcp pool VLAN20
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

(VLAN 30)
ip dhcp excluded-address 192.168.30.1 192.168.30.10
ip dhcp pool VLAN30
 network 192.168.30.0 255.255.255.0
 default-router 192.168.30.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

(VLAN 40)
ip dhcp excluded-address 192.168.40.1 192.168.40.10
ip dhcp pool VLAN40
 network 192.168.40.0 255.255.255.0
 default-router 192.168.40.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

(VLAN 50)
ip dhcp excluded-address 192.168.50.1 192.168.50.10
ip dhcp pool VLAN50
 network 192.168.50.0 255.255.255.0
 default-router 192.168.50.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

(VLAN 60)
ip dhcp excluded-address 192.168.60.1 192.168.60.10
ip dhcp pool VLAN60
 network 192.168.60.0 255.255.255.0
 default-router 192.168.60.1
 dns-server 8.8.8.8 1.1.1.1
 lease 7

```

end
write memory
