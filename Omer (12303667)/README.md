# Topology Overview
The topology represents a secured multi-site network built in GNS3 for the COIT12202 Secured Multi-Site Network Project. The assessment requires each member to build a site, connect the sites into a federated network, and apply multiple security controls such as Kerberos, OPNsense firewalls, VPN connectivity, and intrusion detection.
<img width="1919" height="1002" alt="{A25B73DB-B29F-487B-8739-609341D80FA3}" src="https://github.com/user-attachments/assets/d56fcb4e-4968-460c-acdc-4e382f1d0714" />
Figure: Secured multi-site GNS3 network topology.

# Kerberos Authentication Report
This activity demonstrates Kerberos-based authentication in GNS3. The purpose is to configure a Key Distribution Centre (KDC) so that a client can obtain a Kerberos ticket and use it to log in to an SSH server without entering the SSH password.

# Network Topology and Addressing
The topology consists of three Kerberos hosts connected through an Ethernet switch: KDC, Server, and Client. Each device is configured with a fully qualified domain name because Kerberos relies heavily on hostname resolution rather than only IP addresses.

KDC	    kdc.example.com	    10.11.2.10/24   Issues Kerberos tickets
Server	server.example.com	10.11.2.20/24	  SSH server
Client	client.example.com	10.11.2.30/24	  Requests tickets and SSH login

# Server Keytab and SSH Configuration
The server keytab was successfully installed and verified. The keytab contained the Kerberos principal for host/server.example.com@EXAMPLE.COM. GSSAPI authentication was also enabled in the SSH configuration, and the Kerberos-compatible SSH service was started.
The screenshot also shows some troubleshooting while configuring the local omer account and checking system files. These steps were part of preparing the server for Kerberos-based SSH authentication.
<img width="940" height="498" alt="image" src="https://github.com/user-attachments/assets/5b491627-7d06-45c4-8158-539220273c3e" />
Figure:  Server keytab verification, GSSAPI configuration and SSH server preparation.

# KDC Database and Principal Configuration
The Kerberos database was created for the EXAMPLE.COM realm and the KDC services were started successfully.
Using the Kerberos administration interface, the required principals were created for the user and participating hosts. The server's host principal was then exported to /tmp/server.keytab. The screenshot also shows the keytab being made available through a temporary HTTP server so that it could be transferred to the SSH server.
<img width="940" height="486" alt="image" src="https://github.com/user-attachments/assets/55ba87d6-0e1b-4968-a48d-17692f35d2a6" />
Figure: Kerberos KDC configuration, principal creation and server keytab generation.

# Client Ticket and Kerberos SSH Authentication
On the client, Kerberos authentication was tested using the user principal omer@EXAMPLE.COM.
The screenshot shows several authentication attempts during troubleshooting. Initially, SSH access was denied because the required Kerberos credentials were not yet available or correctly configured.
After successfully obtaining a Kerberos Ticket Granting Ticket, klist displayed the principal:
omer@EXAMPLE.COM
with the Ticket Granting Ticket:
krbtgt/EXAMPLE.COM@EXAMPLE.COM
The client was then able to connect successfully to server.example.com, and the Welcome to Alpine! message confirms that the SSH session was established.
<img width="940" height="479" alt="image" src="https://github.com/user-attachments/assets/644c2b42-dcee-4ed0-bf2a-43ae4c5b0d3f" />
Figure: Kerberos ticket acquisition and successful SSH authentication from the client.

# Service Ticket Verification and Authentication Test
After the successful SSH connection, the client's ticket cache was checked again.
The screenshot shows two important Kerberos tickets:
- krbtgt/EXAMPLE.COM@EXAMPLE.COM
- host/server.example.com@EXAMPLE.COM
The first is the Ticket Granting Ticket, while the second is the service ticket issued specifically for accessing the SSH server.
The Kerberos tickets were then removed using kdestroy. After the credentials were destroyed, another Kerberos-only SSH attempt was made and access was denied with a Permission denied message.
This confirms that the earlier successful SSH login depended on the Kerberos ticket rather than password authentication.
<img width="940" height="455" alt="image" src="https://github.com/user-attachments/assets/ab6b140f-ba88-432a-92c4-9c20e858b1c9" />
Figure: Kerberos service ticket verification and failed SSH authentication after ticket destruction.

# Wireshark Packet Capture
Wireshark was used to capture traffic between the Kerberos systems. The unfiltered capture shows communication between:
- Client: 10.10.2.50
- KDC: 10.10.2.30
- Server: 10.10.2.40
The capture also shows normal SSH/TCP communication between the client and server. 
<img width="940" height="495" alt="image" src="https://github.com/user-attachments/assets/fdc36af5-7a7f-4253-b797-d81c6e83f572" />
Figure: Network traffic generated during Kerberos authentication and SSH communication.

# Kerberos Packet Analysis
The Wireshark display was filtered using Kerberos, allowing the authentication packets to be clearly identified.
The screenshot contains several important Kerberos messages, including:
AS-REQ – Authentication request sent from the client to the KDC.
AS-REP – KDC response containing information required for the client's Ticket Granting Ticket.
TGS-REQ – Request for a service-specific ticket.
TGS-REP – KDC response containing the service ticket.
The traffic is primarily between 10.10.2.50 and 10.10.2.30, confirming communication between the client and KDC. week 5 network
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/55f93b8b-5999-44a3-b245-f44478e8c4d3" />
Figure: AS-REQ, AS-REP, TGS-REQ and TGS-REP Kerberos packets captured in Wireshark.

# Firewalls & Network Defence
OPNsense firewall rules were configured on the different interfaces to control traffic moving through the network. Separate rules were applied to the LAN, DMZ and WAN interfaces so that only required traffic could pass between network zones.
The LAN rules were used to control traffic generated from trusted internal devices. These rules allowed necessary communication from the LAN to other permitted networks and services.
The DMZ rules were configured to control traffic from systems located in the DMZ. This helped keep publicly accessible or less-trusted systems separated from the internal LAN.
The WAN rules controlled traffic entering from the external or transit network. Only required traffic was permitted, while unnecessary or unauthorised traffic was blocked.
Using separate firewall rules for each interface creates clear trust boundaries and supports the defence-in-depth security approach used in the project. The assignment specifically requires OPNsense security zones and appropriate firewall rules as part of the secured multi-site network. a2-secured-multisite-network-pr…
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/6278c4e5-b38d-484d-86c2-4a7ab53393a4" />
Figure – OPNsense LAN firewall rules controlling traffic from the trusted internal network.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/963976b9-9e38-4bbd-8e3c-f8c5d376a3c4" />
Figure – OPNsense DMZ firewall rules controlling traffic from the DMZ network.
<img width="940" height="605" alt="image" src="https://github.com/user-attachments/assets/bb905a51-3601-42cf-bc45-84a289e35c17" />
Figure – OPNsense WAN firewall rules controlling incoming traffic from the external or transit network.

The OPNsense firewall live log was used to monitor traffic passing through the firewall and identify packets that were blocked by the configured security rules.
The log provides information such as the source address, destination address, protocol, interface and whether the packet was passed or blocked. This was useful during testing because it helped identify when traffic was being denied by the firewall.
The blocked traffic shown in the live log demonstrates that the firewall rules were actively enforcing the configured security policy rather than allowing unrestricted network communication.
This provides evidence that traffic outside the permitted rules was prevented from crossing the network trust boundaries.
<img width="1906" height="971" alt="16 network week 6" src="https://github.com/user-attachments/assets/9fa2311f-0313-4fd3-b765-cb8c8df5bbaa" />
Figure – OPNsense firewall live log showing traffic blocked by the configured firewall policy.

# OPNsense Firewall Report
This activity focused on building a segmented network using OPNsense with separate WAN, LAN, and DMZ zones. Firewall rules were configured to control communication between the zones and ensure that only permitted traffic could pass.

# WireGuard VPN Report
This activity focused on configuring and verifying a site-to-site VPN connection between two networks. The screenshots show the VPN configuration in the firewall interface, tunnel status information, command-line verification, and packet capture evidence.

# VPN Configuration
The VPN configuration was completed through the firewall web interface. The screenshots show the VPN settings and configured tunnel entries of 192.168.56.101:6080, indicating that the required VPN connection parameters were added successfully.
<img width="940" height="473" alt="image" src="https://github.com/user-attachments/assets/b8b07e19-e7bd-4047-bc5e-709999fdffc7" />
Figure 1: VPN configuration page showing the configured site-to-site VPN connection.

The second screenshot further confirms the VPN tunnel configuration of 192.168.56.101:6090 and shows the established connection details in the firewall interface.
<img width="940" height="479" alt="image" src="https://github.com/user-attachments/assets/bc61f93e-dc07-4dbe-83a6-205d2eba1fe1" />
Figure 2: Configured VPN tunnel details displayed in the firewall management interface.

# Tunnel Status
The VPN status page was checked to confirm whether the tunnel was active. The screenshots show the VPN connection status and phase information, indicating that the tunnel configuration had been applied and the connection was being monitored for 192.168.56.101:6080
<img width="940" height="478" alt="image" src="https://github.com/user-attachments/assets/656f57d6-aa43-4223-941c-64b0b9adcff3" />
Figure 3: VPN status page showing the current state of the configured tunnel.

The status information was reviewed again to verify that the tunnel remained active and that the configured VPN connection was functioning of 192.168.56.101:6090.
<img width="940" height="475" alt="image" src="https://github.com/user-attachments/assets/2cb39d52-cadc-456f-a898-eb3b51565270" />
Figure 4: VPN tunnel status confirming the configured site-to-site connection.

# Connectivity Verification
Command-line testing was performed to verify communication between the two networks. The screenshots show network interface and routing information together with connectivity testing, which was used to confirm that traffic could travel through the VPN path.
<img width="940" height="483" alt="image" src="https://github.com/user-attachments/assets/e2841760-6220-453b-bc97-f7c189781277" />
Figure 5: Command-line verification of network configuration and VPN connectivity.

# VPN Traffic Verification
Further command-line testing was performed to verify that traffic was successfully passing between the two VPN-connected networks.
<img width="940" height="474" alt="image" src="https://github.com/user-attachments/assets/351b0162-11d6-4bd8-b593-1234acb9cdcf" />
Figure 6: Successful communication and network verification through the configured VPN tunnel.

# Packet Capture Analysis
A packet capture was performed in Wireshark to inspect the VPN traffic. The screenshot shows encrypted VPN packets, including ESP traffic, which indicates that the data transmitted between the VPN endpoints was protected rather than being sent as clear-text traffic.
<img width="940" height="490" alt="image" src="https://github.com/user-attachments/assets/b67245c9-a40a-414d-b4e6-f28e1d52d6ea" />
Figure 7: Wireshark packet capture showing encrypted ESP traffic generated by the VPN connection.


# Suricata IDS Report
This activity focused on configuring and testing Suricata as a passive Intrusion Detection System (IDS) in GNS3. The purpose was to monitor network traffic, create custom detection rules, trigger those rules using test traffic, and verify the generated alerts. suricata-basics-instructions

# Network Connectivity
The client was successfully connected to the server on the internal network. The client was able to ping the server at 10.11.2.30, showing successful communication between both devices. The client also accessed the HTTP server and received the directory listing successfully.
<img width="1911" height="986" alt="1 network week 8" src="https://github.com/user-attachments/assets/030ec394-5324-47d3-9fe1-f478749f200b" />
Figure 1: Client successfully pinging the server and accessing the HTTP web service.

The HTTP server was successfully started on the server node. The server received HTTP GET requests from the client, confirming that the web service and network communication were working correctly.
<img width="1919" height="1011" alt="2 network week 8" src="https://github.com/user-attachments/assets/2a3b46ed-c377-4e71-8f1f-0d9eede2177a" />
Figure 2: HTTP server running successfully and receiving requests from the client.

# Suricata Configuration
The Suricata configuration file was reviewed on the IDS node. The HOME_NET setting included private network ranges such as 10.0.0.0/8, meaning the 10.11.2.0/24 network used in this activity was covered by the Suricata monitoring configuration. The activity also specifies that Suricata monitors traffic using its configured data interface and loads custom detection rules from the custom rules file. suricata-basics-instructions
<img width="1919" height="1023" alt="3 network week 8" src="https://github.com/user-attachments/assets/8606451c-5278-410c-98cf-85d9d04593b9" />
Figure 3: Suricata configuration showing the HOME_NET network settings.

The Suricata configuration directory was checked to confirm that the required configuration files were available, including the main suricata.yaml file.
<img width="1912" height="989" alt="4 network week 8" src="https://github.com/user-attachments/assets/a09bf58b-e2ad-414e-aaed-34e922c49cda" />
Figure 4: Suricata configuration files available on the IDS node.

# Custom Detection Rules
Two custom Suricata rules were configured. The first rule was designed to detect HTTP traffic containing the suspicious BadBot User-Agent, while the second rule monitored outbound TCP connections to port 4444, which can be associated with reverse-shell activity. suricata-basics-instructions
<img width="1906" height="980" alt="5 network week 8" src="https://github.com/user-attachments/assets/20c3f634-6d61-4e2f-97d7-9c875cfaa20a" />
Figure 5: Custom Suricata rules for BadBot User-Agent detection and TCP port 4444 monitoring.

# Rule Validation
The Suricata configuration was initially tested and showed that the custom rules were not yet loaded. This was corrected by reviewing and updating the custom rules configuration.
<img width="1919" height="982" alt="6 network week 8" src="https://github.com/user-attachments/assets/7cc859ce-ec92-4b0d-97e3-1b589bb2f8df" />
Figure 6: Initial Suricata validation showing that no custom rules were loaded.
After correcting the rule configuration, Suricata successfully processed the custom rules. The output confirmed that two rules were successfully loaded with zero failed rules. The IDS engine then started successfully on interface eth0, and the running process was confirmed.
This matches the expected validation process described in the activity, where successful loading should show two rules loaded and no failed rules. suricata-basics-instructions
<img width="1919" height="1020" alt="7 network week 8" src="https://github.com/user-attachments/assets/517d8e4d-c17d-4668-a097-f8a73841dcb6" />
Figure 7: Successful Suricata validation, two custom rules loaded, and IDS engine started successfully.

# Traffic Generation
Test traffic was generated from the client to verify whether Suricata could detect suspicious activity. HTTP traffic was sent to the web server, and TCP traffic was also generated toward the server to test the port-based detection rule.
The activity requires the BadBot User-Agent rule to trigger when matching HTTP traffic is observed and the port 4444 rule to trigger when an established TCP connection is detected. suricata-basics-instructions suricata-basics-instructions
<img width="1910" height="983" alt="8 network week 8" src="https://github.com/user-attachments/assets/b93ffc47-6b17-46cc-b0e9-d6f4834de559" />
Figure 8: Client generating HTTP and TCP traffic for Suricata detection testing.

The server successfully received the generated test traffic. The HTTP GET requests were recorded by the web server, and the TCP test traffic was also received.
<img width="1919" height="993" alt="9 network week 8" src="https://github.com/user-attachments/assets/edf50807-6bb8-4094-a097-daa6fb14918c" />
Figure 9: Server receiving HTTP requests and TCP test traffic generated by the client.

# Alert Verification
The final Suricata logs confirmed that both custom detection rules were functioning successfully. The fast.log file showed alerts for the suspicious BadBot User-Agent using SID 1000001 and the outbound connection to port 4444 using SID 1000002.
The eve.json output also contained detailed information about the detected event, including source and destination addresses, protocol information, HTTP details, and alert information. The activity explains that fast.log provides a quick one-line alert summary, whereas eve.json provides more detailed structured event information. suricata-basics-instructions
<img width="1919" height="997" alt="10 network week 8" src="https://github.com/user-attachments/assets/9ed83655-eccb-4152-b6a9-07d8afac9692" />
Figure 10: Suricata fast.log and eve.json confirming successful detection of the BadBot User-Agent and port 4444 traffic.
