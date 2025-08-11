

## 📡 VLAN Communication Summary

| From VLAN / To VLAN | 10 (Regular Customers) | 20 (Accounting) | 30 (Big Customers) | 40 (Management) | 50 (Tech Support) | 60 (Security) |
|---------------------|------------------------|-----------------|--------------------|-----------------|-------------------|---------------|
| **10** Regular Customers | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ |
| **20** Accounting        | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ |
| **30** Big Customers     | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ |
| **40** Management        | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ |
| **50** Tech Support      | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ |
| **60** Security          | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ |




```
conf t

ip access-list extended VLAN10-IN
 permit ip 192.168.10.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip 192.168.10.0 0.0.0.255 192.168.50.0 0.0.0.255
 deny ip any any
exit
interface g0/0.10
 ip access-group VLAN10-IN in
exit

ip access-list extended VLAN20-IN
 permit ip 192.168.20.0 0.0.0.255 192.168.10.0 0.0.0.255
 permit ip 192.168.20.0 0.0.0.255 192.168.30.0 0.0.0.255
 permit ip 192.168.20.0 0.0.0.255 192.168.40.0 0.0.0.255
 permit ip 192.168.20.0 0.0.0.255 192.168.50.0 0.0.0.255
 deny ip any any
exit
interface g0/0.20
 ip access-group VLAN20-IN in
exit

ip access-list extended VLAN30-IN
 permit ip 192.168.30.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip 192.168.30.0 0.0.0.255 192.168.50.0 0.0.0.255
 deny ip any any
exit
interface g0/0.30
 ip access-group VLAN30-IN in
exit

ip access-list extended VLAN40-IN
 permit ip 192.168.40.0 0.0.0.255 192.168.10.0 0.0.0.255
 permit ip 192.168.40.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip 192.168.40.0 0.0.0.255 192.168.30.0 0.0.0.255
 permit ip 192.168.40.0 0.0.0.255 192.168.50.0 0.0.0.255
 permit ip 192.168.40.0 0.0.0.255 192.168.60.0 0.0.0.255
 deny ip any any
exit
interface g0/0.40
 ip access-group VLAN40-IN in
exit

ip access-list extended VLAN50-IN
 permit ip 192.168.50.0 0.0.0.255 192.168.10.0 0.0.0.255
 permit ip 192.168.50.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip 192.168.50.0 0.0.0.255 192.168.30.0 0.0.0.255
 permit ip 192.168.50.0 0.0.0.255 192.168.40.0 0.0.0.255
 permit ip 192.168.50.0 0.0.0.255 192.168.60.0 0.0.0.255
 deny ip any any
exit
interface g0/0.50
 ip access-group VLAN50-IN in
exit

ip access-list extended VLAN60-IN
 permit ip 192.168.60.0 0.0.0.255 192.168.40.0 0.0.0.255
 permit ip 192.168.60.0 0.0.0.255 192.168.50.0 0.0.0.255
 deny ip any any
exit
interface g0/0.60
 ip access-group VLAN60-IN in
exit

end
wr

```
