```
#Create the VLANs (on every switch)

enable
configure terminal
vlan 10
 name regular-customers
vlan 20
 name accounting
vlan 30
 name big-customers
vlan 40
 name management
vlan 50
 name tech-support
vlan 60
 name security-cameras
end
write memory

#Map access ports to the correct VLANs

#Switch 2960-regular
enable
configure terminal
interface range fa0/2 - 7
 description Tellers - VLAN10
 switchport mode access
 switchport access vlan 10

end
wr

#Switch 2960-management-tech
enable
configure terminal
interface fa0/4
 description Manager-PC - VLAN40
 switchport mode access
 switchport access vlan 40

interface fa0/3
 description Tech-Support - VLAN50
 switchport mode access
 switchport access vlan 50

end
wr

#Switch 2960-bigclient-acc:
enable
configure terminal
interface range fa0/6 , fa0/7
 description Big-Clients - VLAN30
 switchport mode access
 switchport access vlan 30

interface range fa0/2 - 5
 description Accounting - VLAN20
 switchport mode access
 switchport access vlan 20

end
wr

# Configure trunk links between switches and to the router:

#router:
enable
configure terminal
interface ga0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,50,60
end
wr

#Switch 2960-bigclient-acc:
enable
configure terminal
interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,60
end
wr

#Switch 2960-management-tech:
enable
configure terminal
interface range fa0/1 - 2
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,60
end
wr

#Switch 2960-regular:
enable
configure terminal
interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,60
end
wr

#switch 2960- 3:
enable
configure terminal
interface range fa0/1 - 3
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40,50,60
end
wr

```












```
