# Task 1 — Local Network Port Scan (Cyber Security Internship)

## Objective
Perform network reconnaissance on my local subnet (192.168.29.0/24) to identify active hosts, open ports, and analyze potential security risks.

## Environment
- Host machine: Linux (IP: 192.168.29.228)
- Network range: 192.168.29.0/24
- Tools used: Nmap
- Date: 2025-10-20
- Command:
  ```bash
  sudo nmap -sS 192.168.29.0/24 -oN scans/scan_192.168.29.0_24.txt




## Wireshark Analysis (capture_192.168.29.pcapng)

- Capture filename: `scans/capture_192.168.29.pcapng`
- Capture time: <put actual date/time>
- Filters used:
  - `ip.addr == 192.168.29.228`
  - `tcp.flags.syn == 1 and tcp.flags.ack == 0`
  - `tcp.flags.syn == 1 and tcp.flags.ack == 1`
- Observations:
  - SYN packets sent to 192.168.29.1, 192.168.29.150, 192.168.29.26.
  - SYN-ACK responses received from 192.168.29.1 (ports 53,80,443,1900,7443,8080,8443) and 192.168.29.150 (135,139,445).
  - No responses (RST/filtered) from some hosts/ports (e.g., 192.168.29.26 SIP appears filtered).
- Evidence included:
  - `screenshots/syn_packets.png`
  - `screenshots/synack_example.png`
  - `scans/stream_192.168.29.1_80.txt`
  - `scans/capture_192.168.29_to_192.168.29.1.pcapng`
