# OSPF-
OSPF-OPEN SHORTEST PATH FIRST
# Definition
OSPF is a link-state routing protocol used to dynamically exchange routing information within an IP network. It calculates the shortest path to each network using Dijkstra’s algorithm and updates routes efficiently when the network topology changes.

# PROJECT DEFINITION
OSPF was configured on four LAN routers, all within Area 0, to enable dynamic routing between the networks. The LAN networks were as follows: LAN1 – 192.168.1.0/24, LAN2 – 192.168.2.0/24, LAN3 – 192.168.3.0/24, and LAN4 – 192.168.4.0/24. Each router was configured with OSPF to advertise its connected networks and establish OSPF neighbor relationships for proper routing across all LANs.

# CLI-COMMANDS  configure router

Router# config terminal

Router(config)# int gig 0/0

Router(config-if)# ip address 192.168.1.1 255.255.255.0

Router(config-if)# no shutdown

Router# config terminal

Router(config)# int gig 0/0

Router(config-if)# ip address 192.168.2.1 255.255.255.0

Router(config-if)# no shutdown

Router# config terminal

Router(config)# int gig 0/0

Router(config-if)# ip address 192.168.3.1 255.255.255.0

Router(config-if)# no shutdown

Router# config terminal

Router(config)# int gig 0/0

Router(config-if)# ip address 192.168.4.1 255.255.255.0

Router(config-if)# no shutdown

# ENABLE OSPF CLI-COMMANDS

**LAN1 ROUTER**

Router# config terminal

Router(config)# router ospf 1

Router(config-router)# network 192.168.1.0 255.255.255.0 area0

Router(config-router)# network 192.168.2.0 255.255.255.0 area0

Router(config-router)# network 192.168.3.0 255.255.255.0 area0

exit

**LAN2 ROUTER**

Router(config)# router ospf 1

Router(config-router)# network 192.168.2.0 255.255.255.0 area0

Router(config-router)# network 192.168.4.0 255.255.255.0 area0

Router(config-router)# network 192.168.1.0 255.255.255.0 area0

exit

**LAN4 ROUTER**

Router(config)# router ospf 1

Router(config-router)# network 192.168.4.0 255.255.255.0 area0

Router(config-router)# network 192.168.2.0 255.255.255.0 area0

Router(config-router)# network 192.168.3.0 255.255.255.0 area0

exit

**LAN3 ROUTER**

Router(config)# router ospf 1

Router(config-router)# network 192.168.3.0 255.255.255.0 area0

Router(config-router)# network 192.168.4.0 255.255.255.0 area0

Router(config-router)# network 192.168.1.0 255.255.255.0 area0

exit
