# Cybersecurity Incident Report: DNS & ICMP Network Traffic Analysis

## Problem Summary

A DNS query was sent using UDP to `203.0.113.2` on port `53`. The attempt failed, and the ICMP error message `udp port 53 unreachable` was returned. This indicates that the DNS server could not receive or respond to the request, likely due to:

- DNS server misconfiguration or downtime
- A firewall blocking outbound UDP traffic on port 53

---

## Incident Details

- **Time of Incident:** 1:24 p.m., 32.192571 seconds
- **Issue Detected:** Customers reported being unable to access `www.yummyrecipesforme.com` and received a “destination port unreachable” error.
- **Detection Method:** Reports from users → IT confirmed the error → Used `tcpdump` to analyze the network traffic.
- **Key Findings:**
  - DNS requests were blocked or not resolved
  - ICMP echo replies confirmed `udp port 53 unreachable`
  - Indicates DNS is either down, misconfigured, or blocked

---

## 🛠Root Cause (Likely)

- Misconfigured or offline DNS server
- Firewall rule blocking UDP port 53
