# network-environment-setting
 Create an intranet which contains several VMs:
 ○ Router
 ■ The only VM is directly connected to the outside world (Internet). 
■ Provides NAT and DHCP.
 ■ Can connect to all VMs inside your subnet. 
■ Can connect to the VPN server and the whole 10.113.0.0/16 intranet. 
○ Agent
 ■ Simulates a simple VM inside your subnet to help TAs and OJ verify 
results. 

Routing
 • All inbound and outbound traffic in and out your subnet should go through 
Router.
 • Traffic from Private zone to Internet should be NAT masqueraded.
 • Traffic from Private zone to VPN zone should not be NAT masqueraded.
 • Traffic from VPN zone to Private zone should go to its destination. 

  Firewall
 • Consider you are providing services to the Internet, so several firewall 
configurations must be taken for security. 
• Configure firewall rules on Router. 
• Rules:
 • By default, all connections from Internet and VPN zone to Private zone should be 
rejected.
 • By default, all connections from Private zone to VPN zone should be rejected. 
• SSH connections from anywhere to “Agent” are allowed.
 • SSH connections from VPN zone to “Router” are not allowed.
 • ICMP connections from anywhere to anywhere are allowed.
 • Allow HTTP (80)/HTTPS (443) from Private zone to VPN zone  
