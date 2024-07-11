## To list and modify interface on the host
````bash
ip link 
 ````
 ## To see the IP addresses assigned to those interfaces
````bash
ip addr  
````
## To set IP addresses on the interfaces
Assign new IPs to each host 
````bash
ip addr add 192.168.1.10/24 dev eth0
````
## To view the routing table
````bash
ip route 
````
or
````bash
route  
````
## To add entries in the routing table
````bash
ip route add 192.168.1.0/24 via 192.168.2.1
````
## To check if IP forwarding is enabled on a host
````bash
 cat /proc/sys/net/ipv4/ip_forward
````
output
````bash
1
````
