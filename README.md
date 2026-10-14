Project Overview

Project: Networking Capstone Project for NetCore Systems Ltd.
Tool: Cisco Packet Tracer
Focus: Network design, IP addressing, connectivity testing, and access control

This project involved designing and implementing a functional network connecting three departments: IT, Sales, and HR. The goal was to establish network communication between devices while applying access restrictions to protect the IT department without preventing the Sales department from accessing the server's services.

Project Objectives
Design and implement a network topology in Cisco Packet Tracer.
Connect three departments using a router and switches.
Configure IP addresses and default gateways for network devices.
Use DHCP to assign IP addresses to connected devices.
Test communication between devices across departments.
Implement an Access Control List on the router.
Restrict Sales department access to IT devices.
Preserve Sales department access to the server and other permitted network traffic.
Verify the results through connectivity tests.
Network Topology

The implemented network consisted of:

1 Cisco 2911 router — Used to connect the network segments and apply access restrictions.
3 Cisco 2960 switches — Used to connect the departmental devices.
6 PCs — Two PCs for each of the IT, Sales, and HR departments.
1 server — Installed within the IT department.
Implementation Process
1. Network Design and Device Setup

I created the network topology in Cisco Packet Tracer and connected the router, three switches, six PCs, and one server.

The devices were organized to support connectivity across the three departments.

2. IP Addressing and DHCP Configuration

I assigned IP addresses to the connected devices through DHCP. I also configured the router interfaces with the appropriate subnet addresses and set the correct default gateway on each device.

These configurations provided the addressing information needed for network communication.

3. Connectivity Testing

After configuring the network, I used the ping command to test connectivity across the IT, Sales, and HR departments.

The tests confirmed that devices could communicate successfully before the access restrictions were applied.

4. Access Control List Configuration

I configured an Access Control List (ACL) on the router to enforce the required network access policy.

The ACL was designed to:

Prevent PCs in the Sales department from accessing PCs in the IT department.
Allow the Sales department to access the server's services.
Permit all other network traffic that was not restricted by the ACL.

This implementation demonstrated how router-based access controls can be used to enforce communication policies within an organizational network.

5. Verification and Testing

I tested the network after applying the ACL to confirm that the intended restrictions and permitted connections behaved correctly.

The results demonstrated that:

The restricted Sales-to-IT communication was blocked.
Sales department users could still access the server's services.
Other permitted network traffic remained available.
Key Outcomes

Through this project, I gained practical experience in:

Building a multi-department network topology.
Configuring Cisco networking devices in a simulated environment.
Working with DHCP and IP addressing.
Configuring router interfaces and default gateways.
Testing network connectivity with ping.
Implementing router ACLs to restrict specific network communication.
Verifying that security restrictions did not unnecessarily disrupt permitted services.

Key takeaway: This project strengthened my understanding of how network configuration and access control work together to provide connectivity while enforcing organizational security requirements.
