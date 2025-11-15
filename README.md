# 🏠 Smart Home Network Simulation - IoT Device Discovery & Automation

**A complete smart home network simulation demonstrating mDNS device discovery, real-time automation, and security analysis.**

![Smart Home Topology](screenshots/packet_tracer_topology.png)

## 📋 Project Overview

This project simulates a complete smart home IoT network with 12+ connected devices, exploring:
- **Automatic device discovery** using mDNS (Multicast DNS) protocol
- **Real-time automation** with 5 conditional scenarios (fire emergency, security, climate control)
- **Network security** vulnerabilities and mitigation strategies
- **Protocol analysis** using Wireshark (mDNS & SSDP packet captures)

**Course:** BCSE308L - Computer Networks  
**Institution:** VIT Vellore  
**Date:** November 2025

---

## 🎯 Features

- ✅ **15+ IoT Devices:** Smoke detectors, fire sprinklers, smart doors, windows, thermostat, siren
- ✅ **Zero-Configuration Networking:** Automatic device discovery via mDNS
- ✅ **Real-Time Automation:** Fire emergency response, security access control, climate management
- ✅ **Performance:** <100ms response time, 0% packet loss
- ✅ **Security Analysis:** Vulnerability demonstrations and mitigation strategies
- ✅ **Protocol Captures:** Real Wireshark captures of mDNS/SSDP traffic

---

## 📁 Repository Contents

├── home_final.pkt # Cisco Packet Tracer simulation file
├── mdns_capture.pcapng # Wireshark mDNS protocol capture
├── report/ # Complete case study documentation
├── presentation/ # PowerPoint slides
├── screenshots/ # Key simulation screenshots
└── README.md # This file


---

## 🚀 Quick Start

### Prerequisites
- **Cisco Packet Tracer 8.2+** ([Download here](https://www.netacad.com/courses/packet-tracer))
- **Wireshark** (optional, for packet analysis)

### Running the Simulation

1. Download `home_final.pkt`
2. Open in Cisco Packet Tracer
3. Switch to **Simulation Mode** to see packets in real-time
4. Test automation:
   - Click on Smoke Detector → Config → Set value to `0.6`
   - Watch automated response: sprinklers activate, siren sounds, doors unlock

---

## 🏗️ Network Architecture

**Three-Tier Design:**

- **Tier 1 - IoT Devices (Edge):** 12 sensors and actuators
- **Tier 2 - Gateway:** Home Gateway (192.168.25.1) - coordination hub
- **Tier 3 - Control/Storage:** Smartphone interface + IoT data server

**Network:** 192.168.25.0/24  
**Protocol:** mDNS (UDP 5353), DHCP, HTTP  
**Connectivity:** Mixed WiFi (802.11) + Ethernet

---

## 🔥 Automation Examples

| Scenario | Trigger | Action | Response Time |
|----------|---------|--------|---------------|
| Fire Emergency (Garage) | Smoke > 0.15 | Sprinkler ON + Door unlock | <100ms |
| House Fire | Smoke in 2+ rooms | All sprinklers + Windows open + Siren | <100ms |
| Access Control | RFID card scan | Door unlock | <50ms |
| Climate Control | Temp > 28°C | Close windows | Real-time |

---

## 🔒 Security Analysis

**Vulnerabilities Identified:**
- ❌ Unencrypted mDNS traffic (plain text device names/IPs)
- ❌ No authentication in UPnP/SSDP
- ❌ Default credentials on IoT devices

**Mitigations Implemented:**
- ✅ Network segmentation (separate IoT VLAN)
- ✅ WPA2/WPA3 WiFi encryption
- ✅ Application-layer authentication
- ✅ Firewall rules

---

## 📊 Performance Results

- **Average Latency:** 41ms (gateway to server)
- **Packet Loss:** 0% (4/4 packets delivered)
- **Comparison:** 5-12× faster than cloud-dependent systems (200-500ms)

---

## 🔬 Wireshark Analysis

Captured 91 packets in 30 seconds:
- **87 mDNS packets** (95.6%) - device discovery
- **4 SSDP packets** (4.4%) - UPnP service announcements

**Real devices captured:** Laptops, MacBooks, Chromecasts from VIT network

![Wireshark Capture](screenshots/wireshark_mdns.png)

---

## 📚 Key Learnings

1. **Edge Computing > Cloud:** Local processing (41ms) significantly outperforms cloud (200-500ms)
2. **Zero-Config Essential:** mDNS enables plug-and-play IoT adoption
3. **Multicast Efficiency:** O(1) device discovery vs O(n) unicast
4. **Security by Design:** Cannot be an afterthought in IoT systems
5. **Standards Matter:** Matter protocol solving interoperability

---

## 🎓 Course Topics Covered

- **Application Layer:** mDNS protocol (RFC 6762), HTTP/REST APIs
- **Transport Layer:** UDP vs TCP trade-offs
- **Network Layer:** Multicast addressing (224.0.0.251)
- **Security:** Encryption, authentication, attack vectors

---

## 🛠️ Tools Used

- **Cisco Packet Tracer 8.2.1** - Network simulation
- **Wireshark 4.0** - Protocol analysis
- **LibreOffice** - Documentation
- **Git/GitHub** - Version control

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⭐ **Star this repo if you found it helpful!**

Made with ❤️ for Computer Networks enthusiasts
