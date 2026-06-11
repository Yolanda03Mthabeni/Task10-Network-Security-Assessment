# Network Security Assessment Report

## Prepared By

Zinhle Yolanda Mthabeni

## Objective

The objective of this assessment was to evaluate the security posture of a local system using network scanning and packet analysis tools. Nmap was used to identify open ports and services, while Wireshark was used to capture and analyze network traffic.

---

# Scope

The assessment focused on:

* Localhost (127.0.0.1)
* Active network services
* Captured network traffic
* DNS and TCP communications

---

# Tools Used

| Tool      | Purpose                             |
| --------- | ----------------------------------- |
| Nmap      | Port scanning and service detection |
| Wireshark | Packet capture and traffic analysis |

---

# Nmap Scan Results

The Nmap scan identified the following open ports:

| Port | Service      | Description                     |
| ---- | ------------ | ------------------------------- |
| 135  | MSRPC        | Microsoft Remote Procedure Call |
| 445  | Microsoft-DS | SMB File and Printer Sharing    |

## Analysis

### Port 135 (MSRPC)

Port 135 is used by Microsoft Windows Remote Procedure Call services. It allows applications and system services to communicate over the network.

**Security Consideration:**
Attackers may use exposed RPC services to gather information about a system.

### Port 445 (SMB)

Port 445 supports Server Message Block (SMB) communications.

**Security Consideration:**
SMB has historically been targeted by malware and ransomware attacks. Organizations should ensure SMB services are properly secured and updated.

---

# Wireshark Traffic Analysis

Network traffic was captured using Wireshark.

The following protocols were observed:

* DNS
* TCP
* TLSv1.2
* SSDP

## DNS Analysis

DNS traffic was observed during domain name resolution activities.

DNS requests were sent from the local device to DNS servers and corresponding responses were received.

## TCP Analysis

TCP traffic was observed establishing and maintaining reliable communications between devices.

## TLS Analysis

TLS traffic indicated encrypted communications between the system and external servers.

Encrypted communications help protect sensitive information from interception.

---

# Security Findings

| Finding                | Risk Level                |
| ---------------------- | ------------------------- |
| Open Port 135 (RPC)    | Medium                    |
| Open Port 445 (SMB)    | Medium                    |
| DNS Traffic Visible    | Low                       |
| TLS Encryption Present | Positive Security Control |

---

# Recommendations

1. Regularly scan systems using Nmap.
2. Restrict unnecessary network services.
3. Keep SMB services fully patched.
4. Monitor DNS activity for suspicious requests.
5. Continue using encrypted communications through TLS.
6. Implement firewall rules to reduce exposure of unnecessary ports.

---

# Conclusion

The assessment successfully identified active network services and analyzed network traffic. The system was found to have two open ports commonly associated with Windows operating systems and was observed using DNS and encrypted TLS communications.

Regular vulnerability assessments and network monitoring are essential for maintaining a secure environment and identifying potential security risks before they can be exploited.
