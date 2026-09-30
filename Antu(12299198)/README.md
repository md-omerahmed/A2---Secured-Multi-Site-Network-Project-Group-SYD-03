# Week 8 class work
## Topology made by me 
<img width="1916" height="946" alt="image" src="https://github.com/user-attachments/assets/bf08ae2a-458c-4c92-914c-df7af8dd6349" />

## Connecting with one of my group member Tahsin 
<img width="1920" height="989" alt="image" src="https://github.com/user-attachments/assets/d7a62a6c-6e44-4c5f-86d3-0119f21acde2" />

## Demo Topology 

<img width="1919" height="1027" alt="image" src="https://github.com/user-attachments/assets/95cea0a2-41c3-49bb-b63a-0ae5c73496d6" />

## Final Topology 

<img width="1920" height="1042" alt="{114F09EC-5291-4B7A-9B4E-CA8DC18A05AD}" src="https://github.com/user-attachments/assets/f6f0cd04-f0e1-45ab-b70a-28c0b7389f27" />


# Host1 Initial Network Check
The ip addr command was used to inspect Host1 before configuring the Kerberos KDC. The eth0 interface was active but did not have an IPv4 address assigned, confirming that the Kerberos address could be configured without conflicting with an existing IPv4 configuration.
<img width="708" height="313" alt="image" src="https://github.com/user-attachments/assets/81132e52-2eab-448b-b8df-8fe330536483" />
# Task 2 – KDC Hostname and IP Configuration
Host1 was configured as the Kerberos Key Distribution Centre (KDC). The hostname was set to kdc.example.com and the eth0 interface was assigned the static IPv4 address 10.10.1.10/24. The configuration was verified using the hostname and ip addr show eth0 commands.
<img width="658" height="283" alt="image" src="https://github.com/user-attachments/assets/105e8769-99f4-46de-a9d7-cfdbca7cbdb8" />
# Task 3 – Kerberos SSH Server Network Configuration
Server1 was configured as the Kerberos-enabled SSH server. Its hostname was set to server1.example.com and the eth0 interface was assigned the static IPv4 address 10.10.1.20/24. The configuration was verified using the hostname and ip addr show eth0 commands.
<img width="729" height="272" alt="image" src="https://github.com/user-attachments/assets/ba8bfbb4-1352-4b65-a81f-e6f09af492ee" />
# Task 4 – Kerberos Client Network Configuration
Host2 was configured as the Kerberos client. Its hostname was set to client1.example.com and the eth0 interface was assigned the static IPv4 address 10.10.1.30/24. The configuration was verified using the hostname and ip addr show eth0 commands.
<img width="665" height="226" alt="image" src="https://github.com/user-attachments/assets/11a95a9a-db11-4f6b-9af2-b28411d1fe4b" />
# Task 5 – KDC Hostname Resolution Configuration
The /etc/hosts file on the Kerberos KDC was configured with static mappings for the KDC, SSH server and Kerberos client. This ensures that all Kerberos systems can resolve each other using fully qualified domain names rather than relying only on IP addresses.
<img width="703" height="354" alt="image" src="https://github.com/user-attachments/assets/90556b16-11ee-4983-8dac-4f44af03eb12" />
# Task 6 – Server Hostname Resolution Configuration
The /etc/hosts file on Server1 was configured with static hostname mappings for the Kerberos KDC, SSH server and Kerberos client. This allows Server1 to resolve all Kerberos-related systems using their fully qualified domain names.
<img width="669" height="384" alt="image" src="https://github.com/user-attachments/assets/709ae284-0803-491f-86af-85ae09f363ed" />
# Task 7 – Client Hostname Resolution Configuration
The /etc/hosts file on the Kerberos client was configured with static mappings for the KDC, SSH server and client host. This ensures that the client can resolve all Kerberos systems by their fully qualified domain names.
<img width="652" height="358" alt="image" src="https://github.com/user-attachments/assets/710c76db-e339-4900-b705-78789ac66b9a" />
# Task 8 – Kerberos Network Connectivity Verification
Connectivity and hostname resolution were verified from the Kerberos client. The client successfully resolved and pinged kdc.example.com at 10.10.1.10 and server1.example.com at 10.10.1.20, with 0% packet loss. This confirms that the three Kerberos systems can communicate using their fully qualified domain names.

<img width="675" height="532" alt="image" src="https://github.com/user-attachments/assets/6b2ca6f0-ef87-462b-b5eb-475fc885adb8" />

# Task 9 – Kerberos Realm Verification
The Kerberos configuration was verified using /etc/krb5.conf. The system is configured to use the EXAMPLE.COM realm, which will be shared by the Kerberos clients and servers.

<img width="680" height="655" alt="image" src="https://github.com/user-attachments/assets/02af7daf-ce10-4a0e-aa41-e12ef966594b" />

# Task 10 – Kerberos KDC Alias Configuration
The KDC hostname mapping was updated so that kerberos.example.com, which is referenced by the Kerberos configuration, resolves to the KDC address 10.10.1.10. The getent hosts kerberos.example.com command confirmed successful hostname resolution.
<img width="669" height="701" alt="image" src="https://github.com/user-attachments/assets/e315fc98-508a-4e97-b638-9c4eeb8d0e24" />
# Task 11 – Server Kerberos KDC Resolution
Server1 was configured to resolve kerberos.example.com to the Kerberos KDC at 10.10.1.10. The configuration was verified using getent hosts kerberos.example.com, confirming successful name resolution.
<img width="715" height="422" alt="image" src="https://github.com/user-attachments/assets/a67648fd-abfb-4f33-a2a5-1cb603ba8b6d" />
# Task 12 – Client Kerberos KDC Resolution
The Kerberos client was configured to resolve kerberos.example.com to the KDC address 10.10.1.10. The getent hosts kerberos.example.com command confirmed that the client can correctly locate the KDC using the hostname specified in the Kerberos configuration.
<img width="658" height="537" alt="image" src="https://github.com/user-attachments/assets/fbae6ee6-9ccc-48ae-b984-9b55a278e7ea" />
# Task 13 - Initial Network Topology
The network topology was created with OPNsense connecting the LAN, WAN and DMZ networks through separate interfaces and switches. This provides network segmentation so that firewall rules can control communication between each network.
<img width="1920" height="1080" alt="initial topology" src="https://github.com/user-attachments/assets/f68afb8f-f5ce-4513-8572-a194498616b6" />
# Task 14 - All Gateways Connectivity Test
The OPNsense ping utility was used to test connectivity with the configured network gateways. Successful replies with 0% packet loss confirmed that the interfaces and connected networks were reachable.
<img width="1920" height="1080" alt="All the gateways is pinging 1" src="https://github.com/user-attachments/assets/308b325b-6fce-453e-8ac0-1ec7a2a86ae0" />
# Task 15 - DMZ Web Server Setup
A simple web server was configured on the DMZ host using Python on port 80. The successful HTTP GET requests confirmed that the DMZ web service was running and accessible from permitted hosts.
<img width="1920" height="1080" alt="DNZ web server" src="https://github.com/user-attachments/assets/bd4fe183-cfcc-4498-bc5e-8dff1f8891a3" />
# Task 16 - LAN Host Connectivity Test
The LAN host was used to ping the OPNsense LAN interface at 10.10.1.1. The successful replies with 0% packet loss confirmed connectivity between the LAN host and the firewall.
<img width="1920" height="1080" alt="Firefox ping for the opnsense" src="https://github.com/user-attachments/assets/5a71dd22-ab28-4bd7-b1c9-8879a12af750" />
# Task 17 - LAN Firewall Rules
Five firewall rules were configured on the LAN interface to control traffic from the LAN network. The rules permit selected services such as HTTP, HTTPS, DNS and SSH while restricting other traffic.
<img width="1920" height="1080" alt="LAN 5 rules" src="https://github.com/user-attachments/assets/def73a2c-f30c-4f91-965b-99e9c6681dc8" />
# task 18 - WAN Firewall Rule
A WAN firewall rule was configured to permit IPv4 TCP traffic to the DMZ web server on port 80. This allows authorised HTTP access to the web server while other unsolicited WAN traffic remains restricted.
<img width="1920" height="1080" alt="WAN RULES" src="https://github.com/user-attachments/assets/94ef3f4a-9fce-4786-ab06-58b6d330b016" />
# Task 19 - OPT1/DMZ Firewall Rules
Firewall rules were configured on the OPT1 interface for the DMZ network. DNS traffic was permitted while other traffic was blocked to restrict unnecessary communication from the DMZ.
<img width="1813" height="1080" alt="OPT1 RULES" src="https://github.com/user-attachments/assets/ffa9fb9b-fe7f-4e9e-b34b-0a3599ac26f9" />
# Task 20 - WAN Interface Configuration
The OPNsense WAN interface was enabled and configured with a static IPv4 configuration. The private and bogon network blocking options were left unticked for the laboratory network environment.
<img width="1920" height="1080" alt="unticked firefox block" src="https://github.com/user-attachments/assets/c4c84156-2db7-45c7-890e-07e96616cf93" />
# Task 21 - LAN Access to DMZ Web Server
The configured LAN firewall rule was tested by accessing the DMZ web server at 10.12.1.20. The successful response confirmed that HTTP traffic from the LAN to the DMZ web server was permitted.
<img width="1920" height="1080" alt="LAN rule 1 permits" src="https://github.com/user-attachments/assets/5505c106-5a89-46dd-a59a-96f2eaf231b1" />
# Task 22 - LAN Block Rule – Live View
The OPNsense firewall Live View was used to verify blocked LAN traffic. The red log entries show ICMP traffic being blocked, confirming that the firewall rule was operating correctly.
<img width="1920" height="1080" alt="LAN rule block live view" src="https://github.com/user-attachments/assets/db65c317-c0b5-4c38-85ca-2309858c95c3" />
# Task 23 - WAN Interface Preparation
The WAN interface was configured for the private lab network. The private-network and bogon-network blocking options were disabled so that communication using the 10.0.0.0/8 addressing range could pass between the OPNsense firewalls.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/eea31bcf-3c26-47a9-ab4e-821a313e18f5" />

# Task 24 - WAN Firewall Rule Configuration
A WAN firewall rule was configured to permit the required inbound HTTP traffic to the DMZ web server. This provides controlled access to the web service while keeping the rule specific to the required destination and port.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/da69ee08-887e-46ca-a20e-7033d33751ba" />

# Task 25 - OPT1 / DMZ Firewall Rule Configuration
The OPT1 interface rules were configured to control DMZ traffic. The screenshot shows the permitted DNS traffic and the additional rule used to manage traffic entering through the DMZ interface.

<img width="1020" height="608" alt="image" src="https://github.com/user-attachments/assets/9050e83a-245e-44b5-90ed-271b5f4a82ad" />

# Task 26 - IPsec Tunnel Established on OPNsense1
The IPsec status page on OPNsense1 confirms that the IKEv2 tunnel is established between 10.0.1.1 and 10.0.1.2. Phase 2 is installed for communication between the 10.10.1.0/24 and 10.13.1.0/24 networks.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/2b69f471-0f1f-4b58-a5f4-43a871d6ae36" />

# Task 27 - IPsec Tunnel Established on OPNsense2
The IPsec status page on OPNsense2 confirms the same tunnel from the remote side. The Phase 2 entry shows the 10.13.1.0/24 local network and 10.10.1.0/24 remote network in the INSTALLED state.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/79e85abc-cb58-4178-8c72-09347ecc5ff4" />

# Task 28 - IPsec Firewall Rule on OPNsense1
An IPsec firewall rule was added on OPNsense1 to allow IPv4 traffic arriving from the remote 10.13.1.0/24 network to the local 10.10.1.0/24 network.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/c4a7e75a-be8a-4b23-8279-adb2c03c4744" />

# Task 29 - IPsec Firewall Rule on OPNsense2
The corresponding IPsec firewall rule was added on OPNsense2 to allow IPv4 traffic from 10.10.1.0/24 to 10.13.1.0/24. This completes the bidirectional policy for the site-to-site tunnel.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/6bfdb428-b742-4c01-a3d9-e9b8ec0814e5" />

# Task 30 - Inter-Site Connectivity Verification
Connectivity was tested from Host1 to the remote 10.13.1.0/24 network. Successful replies from 10.13.1.10, 10.13.1.20 and the remote gateway 10.13.1.1 confirm that routing, IPsec and firewall rules are operating correctly.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/38a250d3-2803-4404-ab4d-6d16c2ff5d5e" />

# Task 31 - Tailscale / Remote Site Connectivity Test
Remote site connectivity was also verified using the VPN routing environment. Successful ICMP replies from hosts in other 10.13.x networks demonstrate that the VPN router can reach the advertised remote subnets.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/de3dcfa0-9014-4775-bae1-96b02c554ed5" />

# Task 32 - Suricata Base Configuration
Suricata was configured with HOME_NET covering the private laboratory address ranges. This allows the IDS to treat internal traffic as protected network traffic and apply the detection rules correctly.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/109fa764-5259-48cd-a1b0-b9bfd7dcaacf" />

# Task 33 - Custom Suricata Detection Rules
Custom Suricata rules were created to detect a suspicious HTTP User-Agent and outbound TCP connections to port 4444. These rules provide evidence of both web-application and possible reverse-shell detection.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/5127997c-6f4c-478e-9e1b-0d449e871140" />

# Task 34 - Web Server Service Started
The server at 10.11.1.30 was started with an HTTP service on port 80. The server log records successful GET requests from the client, confirming that normal web traffic was generated for IDS monitoring.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/897b326f-b8ff-43db-9488-88d1630bf66f" />

# Task 35 - Client Web Request Test
The client generated HTTP traffic to the server using a curl request. The returned directory listing confirms successful client-to-server communication over HTTP.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/1da01759-4180-44c3-b6a1-0d0d43803c17" />

# Task 36 - Additional Client Traffic and Port 4444 Test
The client continued to communicate with the HTTP server and generated traffic toward TCP port 4444. This traffic was used to trigger the custom Suricata detection rule for a possible reverse-shell connection.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/cd113a26-4231-4a19-b18b-f43298fd3286" />

# Task 37 - Server Reception of Test Traffic
The server received the generated HTTP requests and the test connection on port 4444. The displayed message confirms that the test traffic successfully reached the destination server.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/af7d8090-0688-4569-8ecb-50905652b7c7" />

# Task 38 - Suricata Alert Verification
Suricata was started successfully in IDS mode and the alert log was reviewed. The log shows alerts for the suspicious BadBot User-Agent and outbound connections to port 4444, confirming that the custom detection rules operated as intended.

<img width="1020" height="574" alt="image" src="https://github.com/user-attachments/assets/57ba4a0c-d827-4356-b32c-e4c2542d5616" />

