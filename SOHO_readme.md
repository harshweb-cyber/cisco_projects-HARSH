# SOHO (Small Office/Home Office) Networking

## Overview
A **SOHO (Small Office/Home Office) network** is a small-scale network setup used in home offices and small businesses. It typically consists of **a router, switches, computers, printers, and IoT devices** connected to the internet.

---
## Key Concepts

### **1️⃣ Subnet & IP Addressing**
- **Subnet**: A division of an IP network that improves efficiency and security.
- **Base Network**: The first address in a subnet that identifies the network (e.g., `192.168.1.0/24`).
- **DHCP (Dynamic Host Configuration Protocol)**: Automatically assigns IP addresses to devices.

```bash
Router(config)# ip dhcp pool SOHO_NETWORK
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# dns-server 8.8.8.8
Router(dhcp-config)# lease 7
```

---
### **2️⃣ VLANs (Virtual Local Area Networks)**
- **VLANs** separate network traffic logically.
- Example: VLAN 10 for IT, VLAN 20 for Sales.

```bash
Switch(config)# vlan 10
Switch(config-vlan)# name IT_Department
Switch(config)# vlan 20
Switch(config-vlan)# name Sales_Department
```

- **Access & Trunk Ports**:
```bash
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
```
```bash
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk encapsulation dot1Q
```

---
### **3️⃣ Router & Switch Configuration**
- **Viewing Configurations:**
```bash
Switch# show running-config
Switch# show vlan brief
Switch# show interfaces status
Router# show ip route
```
- **Saving Configurations:**
```bash
Switch# copy running-config startup-config
```

---
### **4️⃣ Wireless Networking & SSID**
- **SSID (Service Set Identifier)**: Name of a Wi-Fi network.
- Use **WPA2/WPA3 encryption** for security.
- Hide SSID for additional security:
```bash
Router(config)# interface wlan0
Router(config-if)# no broadcast-ssid
```

---
### **5️⃣ Security Best Practices**
✅ Change default router credentials.
✅ Use VLANs to segment the network.
✅ Enable MAC filtering for Wi-Fi.
✅ Keep firmware & OS updated.
✅ Use a firewall for security.

---
## **Conclusion**
SOHO networking ensures **efficient and secure** connectivity for small businesses and home offices. Configuring VLANs, DHCP, and SSIDs properly helps **optimize performance and security**.

Would you like to see a **Packet Tracer simulation** for SOHO networks? 🚀

