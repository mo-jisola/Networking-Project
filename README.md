# Networking Capstone Project – NetCore Systems Ltd.

## 📌 Project Overview

Welcome to my **Networking Capstone Project**, developed for **NetCore Systems Ltd.** using **Cisco Packet Tracer**.

The purpose of this project was to design, configure, and test a functional network connecting three organizational departments: **IT, Sales, and Human Resources (HR)**. The network was designed to support communication between departments while implementing security restrictions to protect IT department devices.

A key requirement was to prevent Sales department computers from accessing IT department PCs while maintaining access to the server and allowing other permitted network traffic.

This project demonstrates practical networking skills in network topology design, IP addressing, Dynamic Host Configuration Protocol (DHCP), connectivity testing, and router-based Access Control Lists (ACLs).

## 🎯 Project Objectives

The main objectives of this project were to:

- Design and implement a network topology using Cisco Packet Tracer.
- Connect the IT, Sales, and HR departments through a router and switches.
- Configure router interfaces and IP addressing for network communication.
- Implement DHCP to assign IP addresses automatically to connected devices.
- Configure appropriate default gateways for network devices.
- Test connectivity between devices across different departments.
- Configure an Access Control List (ACL) on the router.
- Restrict Sales department PCs from communicating with IT department PCs.
- Preserve Sales department access to the server and its permitted services.
- Verify network connectivity and security policies through testing.

## 🛠️ Technologies and Tools Used

The following networking technologies and tools were used to complete the project:

- **Cisco Packet Tracer:** Network design, configuration, and simulation.
- **Cisco 2911 Router:** Interdepartmental routing and ACL implementation.
- **Cisco 2960 Switches:** Connecting departmental computers and network devices.
- **Dynamic Host Configuration Protocol (DHCP):** Automatic IP address assignment.
- **Internet Protocol (IP) Addressing:** Configuring network addressing and communication.
- **Default Gateways:** Providing a path for devices to reach other networks.
- **Access Control Lists (ACLs):** Controlling traffic based on defined security rules.
- **Ping Command:** Testing connectivity between network devices.

## 🖥️ Network Topology

The network consisted of three departments connected through a router and their respective switches. A server was placed within the IT department to provide services to authorized devices.

### Network Devices

| Device | Quantity | Purpose |
|---|---:|---|
| Cisco 2911 Router | 1 | Routing between network segments and enforcing access restrictions |
| Cisco 2960 Switch | 3 | Connecting devices within the departments |
| PCs | 6 | Two computers per department |
| Server | 1 | Providing network services from the IT department |
| Cisco Packet Tracer | 1 simulation environment | Designing and testing the network |

### Departmental Distribution

| Department | Number of PCs | Additional Devices |
|---|---:|---|
| IT | 2 | 1 server |
| Sales | 2 | None |
| HR | 2 | None |

### Logical Network Design

The network was organized around the following logical structure:

- **IT Department:** Contains two PCs and the server.
- **Sales Department:** Contains two PCs and is subject to restrictions on accessing IT workstations.
- **HR Department:** Contains two PCs with access determined by the configured network policies.
- **Router:** Connects the departmental network segments and applies traffic filtering.
- **Switches:** Provide local connectivity between departmental devices and the network infrastructure.

The router serves as the central point for interdepartmental communication and enforcement of the configured ACL rules.

## ⚙️ Project Implementation

### 1. Network Design and Device Setup

I began by creating the network topology in Cisco Packet Tracer.

The setup included:

- One Cisco 2911 router.
- Three Cisco 2960 switches.
- Six PCs distributed across IT, Sales, and HR.
- One server located in the IT department.

I connected the devices using appropriate network connections and organized them according to their departmental roles.

The objective was to establish a functional network infrastructure that supported communication between the different network segments.

### 2. IP Addressing and DHCP Configuration

After establishing the physical and logical topology, I configured IP addressing to enable communication between devices.

The configuration involved:

- Assigning appropriate IP addresses through DHCP.
- Configuring the router interfaces with the appropriate subnet addresses.
- Setting the correct default gateway for each network segment.
- Ensuring that devices received the addressing information required for network communication.

DHCP simplified device configuration by allowing connected PCs to obtain their IP configuration automatically.

The router's interface addressing provided the necessary gateways for communication between the departmental networks.

**Key learning:** IP addressing, subnet configuration, and default gateways are essential components of a properly functioning network.

### 3. Initial Connectivity Testing

Before implementing security restrictions, I tested the network to verify that devices could communicate across the departmental segments.

I used the `ping` command to test connectivity between devices.

Example command:

```bash
ping <destination-IP-address>
```

The command was used to determine whether a destination device could be reached over the network.

Initial connectivity testing helped establish a baseline and identify potential configuration issues before applying the ACL.

**Testing objectives:**

- Verify that devices received valid IP addresses.
- Confirm that the default gateways were configured correctly.
- Test communication between departmental PCs.
- Confirm that the router could support interdepartmental communication.

The initial tests confirmed successful communication before the access restrictions were applied.

### 4. Access Control List (ACL) Configuration

A major component of the project was implementing an Access Control List on the router to enforce the organization's security requirements.

An ACL is a set of rules used to permit or deny network traffic according to defined conditions, such as source and destination IP addresses.

For this project, the ACL was designed to implement the following policies:

- **Restrict Sales-to-IT workstation access:** Sales PCs must not communicate with PCs in the IT department.
- **Preserve server access:** Sales users must retain access to the server's permitted services.
- **Allow other permitted traffic:** Network traffic not covered by the restrictions should remain available according to the intended policy.

The ACL demonstrated how a router can be used to enforce communication restrictions between different departments without unnecessarily blocking legitimate network services.

#### Intended Access Control Policy

| Source | Destination | Expected Result |
|---|---|---|
| Sales PCs | IT PCs | Denied |
| Sales PCs | IT server | Permitted for authorized services |
| HR PCs | Other network segments | Based on the configured policy |
| IT PCs | Other network segments | Based on the configured policy |
| Other permitted traffic | Authorized destinations | Permitted |

**Important security consideration:** ACL rules must be ordered carefully. The server's permitted traffic should be explicitly allowed before a broader rule denies access to IT workstation addresses. Otherwise, the server may become inaccessible to Sales users.

The actual result also depends on the ACL type, the interface where it is applied, and the direction of traffic filtering.

### 5. Post-Configuration Verification

After applying the ACL, I repeated the connectivity tests to verify that the security policy behaved as intended.

The verification process focused on both restricted and permitted traffic.

#### Tests Performed

**Test 1: Sales PC to IT PC**

- Attempted communication from a Sales PC to an IT workstation.
- Expected result: Communication should be blocked by the ACL.

**Test 2: Sales PC to Server**

- Attempted communication from a Sales PC to the IT department server.
- Expected result: Access to authorized server services should remain available.

**Test 3: Other Permitted Network Traffic**

- Tested communication that was not restricted by the ACL.
- Expected result: Permitted traffic should continue to function according to the network policy.

**Test 4: Network Connectivity**

- Used the `ping` command to check reachability where appropriate.
- Compared the results before and after implementing the access restrictions.

These tests helped verify that the ACL enforced the intended security requirements while preserving necessary network functionality.

**Note:** A successful ping is not the same as successful application-level service access. If ICMP traffic is blocked but a server service is permitted, a ping may fail even when the service is accessible. Service-specific testing is therefore important.

## 📊 Project Results and Key Outcomes

The project demonstrated how a multi-department network can be designed and configured to support communication while enforcing security restrictions.

The intended outcomes were:

- A functional network topology connecting IT, Sales, and HR.
- Automatic IP address assignment through DHCP.
- Correctly configured router interfaces and default gateways.
- Successful initial connectivity testing before ACL implementation.
- Restricted communication from Sales PCs to IT workstation PCs.
- Preserved access from Sales PCs to authorized server services.
- Continued availability of other permitted network traffic.
- Verification of network behavior after implementing access controls.

The project provided practical experience in combining network connectivity requirements with departmental security policies.

## 🔐 Network Security Considerations

This project highlighted several important network security principles.

### Least Privilege

Devices and departments should receive only the network access necessary to perform their functions.

### Traffic Filtering

Router ACLs can help enforce boundaries between departments by permitting or denying traffic based on defined rules.

### Rule Ordering

ACL entries are evaluated in sequence. Specific permissions should be considered carefully when broader restrictions are also required.

### Testing After Configuration

Security rules should be tested against both permitted and denied traffic to reduce the risk of accidental service disruption.

### Defense in Depth

ACLs provide one layer of protection but should not be treated as a complete security solution. Additional controls, such as appropriate server permissions, endpoint security, and network monitoring, may also be necessary.

## 🧠 Skills Demonstrated

Through this project, I developed and applied practical skills in:

- Network topology design and implementation.
- Cisco Packet Tracer network simulation.
- Cisco router and switch configuration.
- IPv4 addressing and subnetting fundamentals.
- DHCP configuration and address assignment.
- Router interface configuration.
- Default gateway configuration.
- Interdepartmental network communication.
- Access Control List configuration and traffic filtering.
- Connectivity troubleshooting using `ping`.
- Network security policy implementation.
- Functional testing and verification.
- Technical documentation and problem-solving.

## 🚧 Challenges and Lessons Learned

Working through this project reinforced several important networking concepts.

### Maintaining Connectivity While Restricting Access

One of the main challenges was balancing network security with operational requirements. Sales users needed to be prevented from accessing IT workstations without losing access to the server's authorized services.

This highlighted the importance of designing specific ACL rules instead of applying overly broad restrictions.

### Understanding Network Addressing

The project reinforced the relationship between IP addresses, subnet masks, router interfaces, and default gateways.

Incorrect addressing can prevent devices from communicating even when the physical topology is correct.

### Verifying ACL Behavior

Testing both permitted and denied connections was essential to determining whether the security policy worked as intended.

A network can appear functional while still containing security configuration errors, so verification must cover multiple traffic scenarios.

### Troubleshooting Connectivity

Using `ping` helped identify whether devices could reach their intended destinations. The project also demonstrated why additional checks may be needed when ICMP results do not reflect the availability of a particular service.

## 🚀 Future Improvements

Potential improvements to this project include:

- Documenting the complete IP addressing scheme and subnet allocations.
- Including a network topology diagram or Cisco Packet Tracer screenshot.
- Documenting the router interface configuration and DHCP settings.
- Adding the final ACL configuration and explaining each rule.
- Testing access to individual server services, such as HTTP or DNS, if configured.
- Expanding the network with additional departments or devices.
- Implementing VLANs to provide stronger logical separation between departments.
- Exploring extended ACLs and more granular traffic filtering.
- Adding network monitoring and logging to improve visibility into traffic.
- Developing a troubleshooting guide for common connectivity and addressing problems.

These improvements would make the network easier to maintain, troubleshoot, document, and expand.

## ▶️ How to Explore the Project

To explore or reproduce the network simulation:

1. Install Cisco Packet Tracer.
2. Clone or download this repository.
3. Open the `.pkt` project file in Cisco Packet Tracer, if included.
4. Review the network topology and device connections.
5. Inspect the IP addressing and DHCP configuration.
6. Review the router interfaces and ACL rules.
7. Test connectivity between devices using `ping`.
8. Verify that restricted communication is blocked and permitted server services remain accessible.

If the Packet Tracer file is not included, use the documented device inventory and implementation steps to recreate the topology.

## 💡 Key Takeaway

This Networking Capstone Project strengthened my understanding of how network infrastructure, IP addressing, routing, DHCP, and access control work together in an organizational environment.

It demonstrated that effective network design requires more than establishing connectivity. It also requires implementing appropriate security restrictions, preserving essential services, and thoroughly testing the results.

By completing this project, I gained valuable hands-on experience with Cisco networking concepts and developed a stronger foundation in network administration, troubleshooting, and security.

## 👨‍💻 About This Project

- **Project Name:** Networking Capstone Project
- **Organization:** NetCore Systems Ltd.
- **Platform:** Cisco Packet Tracer
- **Project Focus:** Network Design, IP Addressing, DHCP, Connectivity Testing, and Access Control
- **Project Type:** Networking and Infrastructure Simulation

## 📬 Connect With Me

I am continuously developing my technical skills and building practical projects to strengthen my knowledge of networking, IT infrastructure, and cybersecurity.

Thank you for taking the time to explore my Networking Capstone Project!

If you find this project useful, feel free to ⭐ star the repository.

---

**Disclaimer:** This project was completed in a simulated Cisco Packet Tracer environment for educational and practical learning purposes.
