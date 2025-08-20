# Network_Reconnaissance
## Scan Your Local Network for Open Ports

### LINUX

1. Open the Terminal.
2. Type ```ifconfig``` to view the network settings of the system.
   ![image](https://github.com/user-attachments/assets/997b17c2-361a-4aa8-a207-af846289a9aa)
3. Nmap is installed by default in Kali Linux.
4. Use the terminal and perform the same commands as used in Windows.
   ![image](https://github.com/user-attachments/assets/7d4a94be-3dd0-457d-8eda-3bfaabd6d254)
5. Save the output to a text file.
   ![image](https://github.com/user-attachments/assets/4101e98f-220c-4f63-8840-71bdf1e17583)

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
