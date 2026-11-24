
# 🏢 Small Office Network Design

## 📌 Project Overview

This project focuses on designing and implementing a Small Office Network using **Cisco Packet Tracer**.

The goal is to establish a reliable and functional Local Area Network (LAN) that allows multiple computers and network devices to communicate with each other while providing centralized IP address management and network services.

This project demonstrates fundamental networking concepts, including IP addressing, subnetting, DHCP configuration, DNS configuration, and basic network troubleshooting.

---

## 🎯 Objectives

- Design a functional Small Office Local Area Network (LAN).
- Configure routers and switches.
- Implement IPv4 addressing and subnetting.
- Configure DHCP for automatic IP address assignment.
- Configure DNS for domain name resolution.
- Establish connectivity between network devices.
- Test and troubleshoot network communication.

---

## 🛠️ Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Cisco Packet Tracer | Network simulation |
| Router | Connects different networks |
| Switch | Connects devices within the LAN |
| DHCP | Automatically assigns IP addresses |
| DNS | Resolves domain names into IP addresses |
| IPv4 | Network addressing |
| Ping | Tests network connectivity |

---

## 🌐 Network Topology

The network consists of a router, a switch, multiple client computers, and network services.

**Topology Diagram:**

> Insert your Cisco Packet Tracer network topology screenshot here.

![Network Topology]([screenshots/network-topology.png](https://github.com/ITZMEXYZ/Network-Engineering-Projects/blob/main/Office%20Network/Topology/Office%20network%20Topology.png))

---

## 📋 IP Addressing Table

| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| Router | G0/0 | TBD | TBD |
| Switch | VLAN 1 | TBD | TBD |
| DHCP Server | NIC | TBD | TBD |
| DNS Server | NIC | TBD | TBD |
| PC 1 | NIC | DHCP | DHCP |
| PC 2 | NIC | DHCP | DHCP |
| PC 3 | NIC | DHCP | DHCP |

*Replace TBD with the actual IP addresses and subnet masks used in your network configuration.*

---

## ⚙️ Configurations

### 1. Router Configuration

Configure the router's LAN interface with an IP address to serve as the default gateway.

```cisco
enable
configure terminal

interface gigabitEthernet 0/0
ip address [GATEWAY_IP] [SUBNET_MASK]
no shutdown

end
write memory
```

### 2. DHCP Configuration

Configure DHCP to automatically assign IP addresses to client computers.

```cisco
ip dhcp excluded-address [GATEWAY_IP]

ip dhcp pool OFFICE_LAN
network [NETWORK_ADDRESS] [SUBNET_MASK]
default-router [GATEWAY_IP]
dns-server [DNS_SERVER_IP]

end
write memory
```

### 3. DNS Configuration

Configure the DNS service on the DNS server.

- Enable DNS service.
- Add a domain name.
- Assign the corresponding server IP address.
- Test domain name resolution from client computers.

### 4. Switch Configuration

Configure the switch ports to connect the router, servers, and client computers.

```cisco
enable
configure terminal

interface range fastEthernet 0/1-24
switchport mode access
no shutdown

end
write memory
```

*Adjust interface names and port ranges based on your actual switch model and topology.*

---

## 🧪 Testing and Verification

The following tests are used to verify network functionality:

| Test | Command / Method | Expected Result |
|---|---|---|
| IP Address Assignment | `ipconfig` | Client receives a valid DHCP address |
| Gateway Connectivity | `ping [GATEWAY_IP]` | Successful response |
| Server Connectivity | `ping [SERVER_IP]` | Successful response |
| DNS Resolution | `nslookup [DOMAIN]` | Domain resolves to the correct IP |
| Network Connectivity | `ping [OTHER_PC_IP]` | Successful response |

**Testing Screenshots:**

> Add screenshots showing successful DHCP assignment, ping tests, and DNS resolution.

![Connectivity Test](screenshots/connectivity-test.png)

---

## 📁 Project Structure

```text
small-office-network/
│
├── README.md
│
├── topology/
│   └── network-topology.png
│
├── configurations/
│   ├── router-config.txt
│   └── switch-config.txt
│
├── screenshots/
│   ├── network-topology.png
│   ├── ip-configuration.png
│   └── connectivity-test.png
│
└── packet-tracer/
    └── small-office-network.pkt
```

---

## 📚 Skills Demonstrated

- LAN Design and Implementation
- IPv4 Addressing and Subnetting
- Router and Switch Configuration
- DHCP Configuration
- DNS Configuration
- Network Connectivity Testing
- Basic Network Troubleshooting
- Cisco IOS Command-Line Interface (CLI)

---

## 📝 Lessons Learned

Through this project, I gained practical experience in designing and configuring a small office network environment.

I developed a better understanding of how routers, switches, and end devices communicate within a LAN. I also learned how DHCP simplifies IP address management, how DNS provides domain name resolution, and how connectivity testing helps identify potential network issues.

---

## 📌 Project Information

| Details | Information |
|---|---|
| Project Name | Small Office Network Design |
| Category | Network Engineering |
| Platform | Cisco Packet Tracer |
| Difficulty | Beginner |
| Status | In Progress |

---

**Disclaimer:** This project is developed for educational and portfolio purposes using a simulated network environment in Cisco Packet Tracer.
