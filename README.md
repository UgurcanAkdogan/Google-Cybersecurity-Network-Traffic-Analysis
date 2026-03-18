# Google-Cybersecurity-Network-Traffic-Analysis
A detailed cybersecurity incident report analyzing DNS and ICMP traffic patterns using tcpdump. Completed as part of the Google Cybersecurity Professional Certificate.
Network Traffic Analysis & Incident Report (DNS/ICMP)
📌 Project Overview

This project is part of the Google Cybersecurity Professional Certificate program. It involves a simulated real-world scenario where I act as a Cybersecurity Analyst to investigate a network connectivity issue using tcpdump. The primary goal was to identify why users could not access a specific website and to provide a detailed incident report based on packet analysis.
🛠 Tools & Technologies

    Network Analysis: tcpdump

    Protocols: UDP, DNS (Port 53), ICMP

    Reporting: Incident Documentation & Root Cause Analysis

📄 Cybersecurity Incident Report
Part 1: Summary of the problem found in the DNS and ICMP traffic log

The UDP protocol reveals that the browser attempted to retrieve the IP address for www.yummyrecipesforme.com by sending queries to the DNS server. However, these requests were not successful, and a connection could not be established to load the website.

This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message: "udp port 53 unreachable." The log entries clearly demonstrate that for every outgoing DNS request sent, the network responded with this specific ICMP error, indicating a delivery failure.

    Affected Port: Port 53 (Standard for DNS)

    Status: Service Unreachable

Part 2: Analysis of the data and root cause

Incident Details:

    Time incident occurred: 1:24 p.m.

    Detection: Several customers reported a "destination port unreachable" error when trying to load the website.

Investigation Process:
To investigate, I used tcpdump to capture traffic in real-time. The logs showed that while the browser initiated standard DNS queries via UDP, the server responded with ICMP error packets. This confirms that the request reached the network but was rejected at the destination port.

Root Cause Analysis:
The network security team suspects the likely cause is either a service failure on the DNS server (the service is not running) or a misconfigured firewall rule that is dropping or rejecting traffic on UDP port 53. This prevents the domain name resolution, making the website inaccessible to users.
🚀 Skills Demonstrated

    Packet Inspection: Interpreting raw network traffic from tcpdump.

    Troubleshooting: Identifying connectivity issues across different layers of the TCP/IP model.

    Communication: Drafting professional cybersecurity reports for technical and non-technical stakeholders.

🎓 About This Project

This lab was completed to demonstrate proficiency in network security monitoring and incident response as part of my journey toward becoming a SOC Analyst.
