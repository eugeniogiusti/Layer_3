# IPv4 Subnetting Quick Reference Guide 🌐
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Network](https://img.shields.io/badge/Networking-IPv4-green)

## 📋 Table of Contents
- [Common Subnet Masks](#common-subnet-masks)
- [Detailed Subnet Information](#detailed-subnet-information)
- [Quick Reference Table](#quick-reference-table)
- [Practical Examples](#practical-examples)

## 🔢 Common Subnet Masks

| CIDR | Subnet Mask     | Available Hosts | Total IPs | Network/Broadcast |
|------|----------------|-----------------|-----------|-------------------|
| /32  | 255.255.255.255| 1 host         | 1         | No               |
| /31  | 255.255.255.254| 2 hosts        | 2         | No (point-to-point)|
| /30  | 255.255.255.252| 2 hosts        | 4         | Yes (2 usable)   |
| /29  | 255.255.255.248| 6 hosts        | 8         | Yes (6 usable)   |
| /28  | 255.255.255.240| 14 hosts       | 16        | Yes (14 usable)  |
| /27  | 255.255.255.224| 30 hosts       | 32        | Yes (30 usable)  |
| /26  | 255.255.255.192| 62 hosts       | 64        | Yes (62 usable)  |
| /25  | 255.255.255.128| 126 hosts      | 128       | Yes (126 usable) |
| /24  | 255.255.255.0  | 254 hosts      | 256       | Yes (254 usable) |

## 📊 Detailed Subnet Information

### /30 Subnet (4 addresses)
- Total IPs: 4
- Usable Hosts: 2
- Network Address: 1
- Broadcast Address: 1
- Perfect for: Point-to-point links

### /29 Subnet (8 addresses)
- Total IPs: 8
- Usable Hosts: 6
- Network Address: 1
- Broadcast Address: 1
- Perfect for: Small office segments

### /28 Subnet (16 addresses)
- Total IPs: 16
- Usable Hosts: 14
- Network Address: 1
- Broadcast Address: 1
- Perfect for: Medium office segments

## 🔍 Quick Reference Table for Network Planning

| Use Case | Recommended CIDR | Max Hosts | Notes |
|----------|-----------------|-----------|-------|
| Point-to-Point Links | /30 | 2 | Most efficient for router links |
| Small VLAN | /29 | 6 | Good for small device groups |
| Medium VLAN | /28 | 14 | Suitable for small offices |
| Large VLAN | /24 | 254 | Standard for larger networks |

## 💡 Practical Examples

### Point-to-Point Link (/30)
```plaintext
Network: 192.168.1.0/30
- 192.168.1.0   - Network
- 192.168.1.1   - Usable (Router 1)
- 192.168.1.2   - Usable (Router 2)
- 192.168.1.3   - Broadcast
```

### Small Office VLAN (/29)
```plaintext
Network: 192.168.1.0/29
- 192.168.1.0   - Network
- 192.168.1.1   - Usable (Gateway)
- 192.168.1.2-6 - Usable (Hosts)
- 192.168.1.7   - Broadcast
```

### Medium Office VLAN (/28)
```plaintext
Network: 192.168.1.0/28
- 192.168.1.0   - Network
- 192.168.1.1   - Usable (Gateway)
- 192.168.1.2-14 - Usable (Hosts)
- 192.168.1.15  - Broadcast
```

## 🧮 Subnet Calculator Formula
- Total IPs = 2^(32-CIDR)
- Usable Hosts = 2^(32-CIDR) - 2 (except for /31 and /32)

## 🚀 Best Practices
1. Always plan for growth
2. Use appropriate subnet size
3. Document all subnet allocations
4. Reserve ranges for future use
5. Keep consistent naming/numbering

## 📝 Notes
- Network address is always the first address in the range
- Broadcast address is always the last address in the range
- Usable addresses are between network and broadcast
- /31 is special case for point-to-point (RFC 3021)

## 🔗 Quick Links
- [Subnet Calculator](https://example.com/subnet-calc)
- [IANA IPv4 Address Space](https://example.com/iana-ipv4)
- [RFC 1918 (Private Address Space)](https://example.com/rfc1918)
