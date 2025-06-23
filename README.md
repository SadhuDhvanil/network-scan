Task 1: Scan Your Local Network for Open Ports

🔍 Objective
To discover active hosts and open TCP ports in the local network using Nmap, understand the services running, and identify potential security risks.

🛠 Tools Used
- [Nmap](https://nmap.org/)
- Wireshark 

🧾 Steps Followed
1. Installed Nmap on Kali Linux.
2. Identified local IP and subnet using `ifconfig`(since using Linux(kali OS)).
3. Ran a TCP SYN scan:  nmap -sS 10.0.2.0/24
4. Analyzed the scan results and identified open ports.
5. Also analysed the working of stealth scanning through wireshark using this filter "tcp.flags.syn==1 && tcp.flags.ack==0".
6. Took screenshots for reference.

📂 Files Included
- **screenshots/**: Contains `ifconfig` and Nmap scan screenshots and wireshark packets showing scan results.

📊 Findings Summary
| IP Address | Open Ports | Services Detected |
|------------|------------|-------------------|
| 10.0.2.2   | 5000, 7000 | UPnP, AFS Fileserver |
| 10.0.2.3   | 53         | DNS |
| 10.0.2.15  | None       | - |

⚠️ Potential Risks
- **UPnP** and **AFS Fileserver** may be unnecessary services.
- Ensure DNS is properly configured and not exposed externally.

✅ Conclusion
This scan provided insights into network exposure. The unnecessary services should be reviewed or disabled for better security.
