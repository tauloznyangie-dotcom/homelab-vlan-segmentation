### homelab-vlan-segmentation
VLAN segmentation lab using pfSense and VMware to simulate enterprise network security and traffic isolation

### Overview 
This project demonstrates how to design and implement VLAN-based network segmentation using pfSense and VMware.

The goal is to isolate different network zones (Management, Staff, Guest, DMZ) and enforce security using firewall rules, simulating a real-world enterprise environment.

### Objectives 
Implement VLAN segmentation
Configure firewall rules to control traffic
Prevent unauthorized access between networks
Simulate enterprise-grade network security

### Lab Environments
pfSense (Firewall/Router)
VMware Workstation
Windows 11 (Management PC)

### Network Design 
Network	           Subnet             	Purpose
MGMT	        192.168.10.0/24	        Management
STAFF	        192.168.20.0/24	        Internal users
GUEST	        192.168.30.0/24         Guest users
DMZ	          192.168.40.0/24	      Public-facing servers

### Firewall Rules
Rule	    Source	     Destination	   Action	    Purpose
1       	STAFF net   	DMZ subnets     Block	    Prevent staff accessing DMZ

2	        STAFF net	   GUEST subnets	  Block	    Prevent staff accessing guest

3	        GUEST net   RFC1918 networks	Block	    Prevent guest accessing internal networks

4	        STAFF net     	Any           Pass	    Allow internet access

### Testing 
Test Case	                Command	                  Expected Result
Ping DMZ from STAFF      	ping 192.168.40.x           	Blocked
Ping GUEST from STAFF    	ping 192.168.30.x           	Blocked
Internet from STAFF        	ping 8.8.8.8                Allowed

### Screenshots 

# Project Files
[View all screenshots](Screenshots-lab/)

pfSense VLAN configuration
Firewall rules
Test results
Successful/blocked ping tests

### What I Learned 
How VLAN segmentation improves network security
How firewall rules control traffic between networksng
Traffic control between network zones
Troubleshooting virtualization and networking issues

### Challenges 
pfSense disk detection issues during installation
Understanding VLAN vs subnet concepts
Correct firewall rule configuration

### Conclusion 
This project demonstrates practical skills in network segmentation, firewall configuration, and troubleshooting—key competencies for IT Support, Network Engineering, and Cybersecurity roles.



