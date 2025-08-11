```

#port-security configuration:

regular:
enable
configure terminal
interface range fastEthernet0/2 - 7
 switchport mode access
 switchport access vlan 10
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
end
write memory


big & acc:
enable
configure terminal
interface range fastEthernet0/2 - 5
 switchport mode access
 switchport access vlan 20
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
end
write memory

enable
configure terminal
interface range fastEthernet0/6 - 7
 switchport mode access
 switchport access vlan 30
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
end
write memory


managment & support:
enable
configure terminal
interface fastEthernet0/3
 switchport mode access
 switchport access vlan 50
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
end
write memory

enable
configure terminal
interface fastEthernet0/4
 switchport mode access
 switchport access vlan 40
 switchport port-security
 switchport port-security maximum 1
 switchport port-security violation restrict
 switchport port-security mac-address sticky
end
write memory


```
