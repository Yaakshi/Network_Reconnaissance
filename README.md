# Network_Reconnaissance
## Scan Your Local Network for Open Ports

### WINDOWS

1. Install Nmap from https://nmap.org/
2. Type the command ```nmap --help``` to list out various options to use with nmap command.
![image](https://github.com/user-attachments/assets/f938c5f6-e82a-434e-8053-d70408d03340)
3. We need to identify the target network. Type ```ipconfig``` to identify the network settings of the system. Identify the IP address to be targeted.
![image](https://github.com/user-attachments/assets/fc27a857-87ab-4319-b99b-c133defc419f)
4. We consider the Wi-Fi adapter. The IP is 192.168.254.101/24.
5. Now use Nmap tool to perform network reconnaissance.
6. Save the result as .xml or .nmap file by going to Scan in Title bar --> Save Scan

```nmap 192.168.254.0/24```
- Scan the entire network 192.168.254.0 to 192.168.254.255 for active hosts.
![image](https://github.com/user-attachments/assets/9c5453c1-a909-4415-a67f-06e1554b57c4)
- 192.168.254.40 is the gateway.
- 192.168.254.101 is the user machine.

```nmap -sn 192.168.254.101```
- sn flag is used for ping scan. It is used to check if the host is up. It disables port scanning and focuses on determining the host's availability.
- Sends ICMP packets to target.
- If the host responds with an ICMP Echo Reply, it is marked as alive.
![image](https://github.com/user-attachments/assets/1957a677-6667-4d02-856a-bb8fb07d7d7d)

```nmap -sS 192.168.254.101```
- sS flag is used for TCP SYN scan. It is also known as stealth scan.
- SYN packet is sent by Kali first and waits for response.
- If a SYN-ACK is received, the port is marked open.
- If RST is received, the port is closed.
- The handshake is never completed, making this scan less detectable.
- It is faster than a TCP connect scan (-sT) and less likely to be logged by the target system.
![image](https://github.com/user-attachments/assets/5e65d39e-d406-4add-bb77-cf28ada9fb1e)

```nmap -sV 192.168.254.101```
- sV flag is used to probe open ports to determine the information about the services running and their versions.
- Nmap first identifies open ports using its standard scanning techniques
- Nmap probes these ports with a series of service-specific payloads (predefined probes in Nmap’s nmap-service-probes database).
- Nmap sends specific probes to each open port.
- It tries to grab service banners (textual information returned by services like HTTP, FTP, or SSH) that often include version numbers.
- Each response is compared to known patterns in the nmap-service-probes database, which contains signatures for thousands of services.
- If a match is found, the service and version information is reported.
- If no exact match is found, Nmap might perform additional heuristics or return a generic service type (e.g., "http?").
![image](https://github.com/user-attachments/assets/ddb99d5f-3600-4a54-9fff-dff072087176)

#### Ports
- A TCP (Transmission Control Protocol) port is a logical endpoint that identifies a specific process or service on a host computer, enabling communication across a network.
- Well-known or Privileged ports (Port range: 0 to 1023) - This range is reserved for the most well-known protocols/applications used over TCP/IP.
- Registered ports (Port range: 1024 to 49,151) - Many applications use TCP/IP to exchange data using protocols unique to each of them.
- Private/Dynamic ports (Port range: 49,152 to 65,535) - These ports are open for anyone to use and are not reserved or maintained by the IANA.

##### Open Ports
- It provides a potential entry point for unauthorized access to bypass your firewalls or other security measures and gain access to your network.
- Once inside, they can launch their desired attacks or perform reconnaissance to learn more about your organization and how to exploit it. 

##### Port 135 - msrpc
- Port 135 is dedicated to the Windows Remote Procedure Call (RPC) Mapper Service.
- This allows other machines that remotely connect to them to learn what services are running and on what ports they can connect to them.
- These services typically relate to remote access and management.
- If port 135 is left open on the public Internet, it can leave devices vulnerable to dangerous attacks such as remote command executions (RCEs), sensitive data exposure, and distributed denial-of-service (DDoS) attacks.

##### Port 139 - netbios-ssn
- Port 139 is a dedicated port for providing session services for the Server Message Block (SMB) protocol over NetBIOS, which is primarily used for sharing printers and files in a Windows-based network.
- When port 139 is exposed to the Internet, it can become dangerous, as attackers could potentially access data stored on the network’s nodes.

##### Port 445 - microsoft-ds
- Port 445 is dedicated to the Server Message Block (SMB) protocol, which allows you to share resources such as files and printers within a network using TCP.
- Server Message Block (SMB) is the protocol that allows devices on the same network to communicate with each other and share resources such as files and printers through what is known as inter-process communication.
- Hackers have used port 445 to infiltrate devices on a network, most famously by the WannaCry ransomware attack. 

### LINUX

1. Open the Terminal.
2. Type ```ifconfig``` to view the network settings of the system.
   ![image](https://github.com/user-attachments/assets/997b17c2-361a-4aa8-a207-af846289a9aa)
3. Nmap is installed by default in Kali Linux.
4. Use the terminal and perform the same commands as used in Windows.
   ![image](https://github.com/user-attachments/assets/7d4a94be-3dd0-457d-8eda-3bfaabd6d254)
5. Save the output to a text file.
   ![image](https://github.com/user-attachments/assets/4101e98f-220c-4f63-8840-71bdf1e17583)

