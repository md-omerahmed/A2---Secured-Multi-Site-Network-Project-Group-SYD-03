
# Topology of Group Assesment
<img width="1920" height="851" alt="image" src="https://github.com/user-attachments/assets/606dbd08-795d-40fe-9362-3f3074a142af" />

#  Network Configuration:
## This screenshot shows the initial network configuration and interface setup used to prepare the host for communication within the secured network.
<img width="573" height="994" alt="{A2C5437C-2FA7-4AF9-A084-A7DE941470B6}" src="https://github.com/user-attachments/assets/25ff2353-8c69-4619-84c8-805c8bbc5ca6" />


# OPNsense Interface Configuration:
## This screenshot shows the OPNsense interface configuration used to separate and manage traffic between the different network zones
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b608e445-0916-4334-adcf-8b4a2818f608" />

# Firewall Connectivity Test:
## This screenshot demonstrates connectivity testing between hosts to verify whether the configured OPNsense firewall rules correctly allow or block network traffic.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1e1a0b87-f77f-4f2b-bd1a-4bc6e54cb029" />

#  OPNsense Firewall Live Log:
## This screenshot shows the OPNsense firewall live log, providing evidence of allowed and blocked traffic generated during firewall testing.
<img width="840" height="624" alt="image" src="https://github.com/user-attachments/assets/5717ecb0-872f-4a27-a537-bfd083bdba56" />

# WAN Firewall Rule:
## This screenshot shows the OPNsense WAN firewall rule configured to allow IPv4 TCP/HTTP traffic on port 80 to the DMZ_WEBSERVER, while other unmatched WAN traffic remains blocked by default.
<img width="1003" height="742" alt="image" src="https://github.com/user-attachments/assets/899de83c-8074-44ef-9b55-ec8af89b7b2e" />

# DMZ (OPT1) Firewall Rules:
## This screenshot shows the OPNsense DMZ (OPT1) firewall rules, allowing DNS traffic on port 53 from the DMZ_NET while blocking other unmatched IPv4 traffic to restrict access from the DMZ..
<img width="852" height="670" alt="image" src="https://github.com/user-attachments/assets/0cd600f4-e012-4447-9560-aa923cc57f94" />

# Firewall Blocking Evidence:
## This screenshot shows the OPNsense firewall live log confirming that ICMP traffic from the LAN host (10.10.3.10) to 10.11.3.10 was blocked by the firewall.
<img width="940" height="648" alt="image" src="https://github.com/user-attachments/assets/ab848322-dd9c-4c31-a00d-7b6dabb04694" />

#  LAN Security Testing:
## This screenshot shows connectivity and access-control testing from the LAN host. The ping test received no replies, while the SSH connection to the DMZ host was refused, demonstrating the configured network restrictions.
<img width="940" height="753" alt="image" src="https://github.com/user-attachments/assets/a7edf2a4-358a-4370-b3ca-d30c944a4580" />

# IPsec VPN – Phase 2 Configuration

## This screenshot shows the IPsec Phase 2 tunnel configuration in OPNsense. I configured Phase 2 to define which networks are allowed to communicate securely through the site-to-site VPN tunnel
## The Local Network was configured as 10.10.3.0/24, while the Remote Network was set to 10.13.3.0/24. I selected ESP (Encapsulating Security Payload) as the protocol to protect the traffic travelling between the two networks. For security, AES-256-GCM was selected as the encryption algorithm and SHA-256 was configured for hashing/authentication.
## This configuration allows traffic between the two LAN networks to be protected through the IPsec VPN tunnel, providing secure communication between the two sites

<img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/d3dd7741-d699-46c5-abb2-11d5c7b46a9e" />

# IPsec VPN – Phase 1 Configuration
## This screenshot shows the IPsec Phase 1 configuration in OPNsense. I configured the VPN using IKEv2 with IPv4 and selected the WAN interface for the VPN connection. The remote gateway was configured as 10.0.3.1, which represents the VPN endpoint on the remote site.
## For authentication, I selected Mutual PSK (Pre-Shared Key) so that both OPNsense firewalls can authenticate each other using the same shared secret. This Phase 1 configuration establishes the secure connection between the two VPN gateways before Phase 2 handles communication between the internal networks.

<img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/6725afbf-e7b2-44f0-b19e-23150d4423cc" />

# IPsec VPN – Tunnel Status Verification
## IPsec Status Overview in OPNsense, confirming that the site-to-site VPN tunnel was successfully established. Phase 1 is active using IKEv2, with the local VPN endpoint 10.0.3.1 communicating with the remote endpoint 10.0.3.2.
# Under Phase 2, the tunnel between the local subnet 10.10.3.0/24 and the remote subnet 10.13.3.0/24 shows the state INSTALLED. This confirms that the IPsec security associations were successfully created and the VPN tunnel is ready to carry protected traffic between the two sites.

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/fbc2363b-2dd9-44f8-85c9-e75685ce673f" />

# It shows the completed IPsec site-to-site VPN configuration in OPNsense. Phase 1 is enabled using IPv4 IKEv2, with the remote VPN gateway configured as 10.0.3.2. The Phase 1 proposal uses AES-GCM encryption with SHA-256 for secure tunnel establishment.
## For Phase 2, I configured the local subnet as 10.10.3.0/24 and the remote subnet as 10.13.3.0/24. The Phase 2 proposal uses AES-256-GCM, SHA-256, and DH Group 14.

## Finally, IPsec was enabled, allowing the two remote LAN networks to communicate securely through the configured VPN tunnel.

<img width="940" height="704" alt="image" src="https://github.com/user-attachments/assets/0ea1bcfd-0305-41c5-b6a6-c6f554a52f81" />

# IPsec VPN – Successful Tunnel Verification
## his screenshot provides evidence that the IPsec site-to-site VPN tunnel is successfully established between the two OPNsense firewalls.
## The Phase 1 connection is active using IKEv2, with the local VPN endpoint 10.0.3.2 connected to the remote endpoint 10.0.3.1. In Phase 2, the local subnet 10.13.3.0/24 is connected to the remote subnet 10.10.3.0/24, and the status is shown as INSTALLED.
## This confirms that the IPsec security associations have been successfully established on this side of the VPN and that the tunnel is ready to securely carry traffic between the two site networks.

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/bc98d9af-2a81-4e80-a6cf-779de1fb6929" />

# IPsec VPN – Ping Connectivity Test
## This screenshot shows the connectivity test performed after establishing the IPsec VPN tunnel. I used the ping command to test communication with the remote host 10.13.3.20.
## The test successfully received replies from the remote host, with 3 packets transmitted, 3 packets received, and 0% packet loss. This confirms that traffic can successfully pass between the two sites through the configured IPsec VPN tunnel.
## This test provides practical evidence that the site-to-site VPN configuration is working correctly and end-to-end communication between the remote networks has been achieved.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/ecb4ad10-9733-4ad2-b34c-714c95211cad" />

# IPsec VPN Traffic Verification Using Wireshark
## To validate the operation of the site-to-site IPsec VPN, I captured network traffic between the two OPNsense VPN gateways using Wireshark. The packet capture shows multiple Encapsulating Security Payload (ESP) packets exchanged between 10.0.3.1 and 10.0.3.2.
## ESP is used by IPsec to provide protection for data transmitted across the VPN tunnel. The capture also shows distinct Security Parameter Index (SPI) values for the security associations, demonstrating bidirectional IPsec traffic between the two VPN endpoints.
## This capture provides network-level evidence that the configured IPsec tunnel is active and that traffic between the sites is being encapsulated by IPsec before transmission across the inter-site network. Together with the successful Phase 1/Phase 2 status and connectivity testing, this verifies the successful implementation of the site-to-site VPN.
<img width="940" height="747" alt="image" src="https://github.com/user-attachments/assets/5e45728c-aa81-46d0-a4ba-ce9616159a48" />

# Detailed Analysis of IPsec ESP Packet
## A detailed Wireshark analysis of an ESP packet captured from the active IPsec VPN tunnel. An ESP display filter was applied to isolate IPsec-protected traffic and verify the operation of the tunnel.
## The selected packet shows communication from 10.0.3.1 to 10.0.3.2 using Encapsulating Security Payload (ESP). Wireshark identifies the packet with an SPI value of 0xc2eac949 and an ESP sequence number of 8. The SPI identifies the relevant IPsec Security Association, while the sequence number is used as part of ESP's anti-replay protection mechanism.
## The packet contents are not displayed as normal application-layer data, which is consistent with the traffic being protected by ESP. This capture therefore provides packet-level evidence that the configured IPsec Security Association is actively processing traffic between the two OPNsense VPN endpoints.
<img width="940" height="703" alt="image" src="https://github.com/user-attachments/assets/ba65f861-81df-4979-9589-81123734a9a1" />

# End-to-End Network Connectivity and Service Validation
## This screenshot provides evidence of successful end-to-end network connectivity and application service accessibility within the configured network environment.
## Connectivity was validated from the client host 10.14.3.10 by sending ICMP echo requests to 10.14.3.20 and 10.14.3.30. Both destination hosts responded successfully with 0% packet loss, confirming that IP addressing, routing, and the applicable firewall policies are permitting communication between the systems.
## Following the connectivity test, I used curl to access the HTTP service hosted on 10.14.3.20. The server returned a valid HTML response containing a directory listing, confirming successful TCP/HTTP communication and demonstrating that the web service is reachable from the client.
## These results provide evidence that both network-layer connectivity and application-layer communication are functioning as intended.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/17bcfa50-5eae-4f50-9d7a-f14324261546" />

# HTTP Server Deployment and Client Request Verification
## This screenshot demonstrates the successful deployment and validation of an HTTP service on the server host. A Python-based HTTP server was started using python3 -m http.server 80, binding the service to TCP port 80 and making it available to network clients.
## The server subsequently received an HTTP GET request from the client at 10.14.3.20. The request was processed successfully and returned the HTTP status code 200, confirming that the requested resource was successfully served.
## This result provides application-layer evidence that the HTTP service is operational, TCP port 80 is reachable, and client-to-server communication is functioning correctly across the configured network.
<img width="940" height="244" alt="image" src="https://github.com/user-attachments/assets/b89d1164-fee9-4c75-a7fa-bd1c53a3e25b" />

# Suricata IDS Configuration and Rule Validation
## This screenshot demonstrates the successful configuration and validation of Suricata as a Network Intrusion Detection System (IDS). The Suricata configuration file and custom rule set were prepared, after which the configuration was validated using Suricata’s test mode (-T).
## The validation output confirms that Suricata successfully loaded the configuration and initialized its detection components. The system loaded 1 rule successfully with 0 failed and 0 skipped rules, and the final message “Configuration provided was successfully loaded” confirms that no configuration errors were detected.
## This verification ensures that the Suricata IDS configuration and custom detection rule are syntactically valid and ready for network traffic monitoring and security event detection.
<img width="940" height="229" alt="image" src="https://github.com/user-attachments/assets/674d7dd0-1ce9-41b3-972a-d53685e15554" />

# Suricata IDS Deployment and Runtime Verification
## This screenshot demonstrates the successful deployment and execution of Suricata in Intrusion Detection System (IDS) mode on the designated monitoring interface. Suricata was started using the configured rule set, with logging directed to the standard Suricata log directory.
## The runtime output confirms that the detection engine initialized successfully and loaded one custom detection rule with zero failed or skipped rules. The message “Engine started” verifies that Suricata entered an operational state and was ready to inspect network traffic.
## The running process was also verified using pgrep -x suricata, which returned a valid process ID, confirming that the Suricata IDS process remained active after startup. This provides evidence that the IDS was correctly configured, successfully launched, and ready to monitor network traffic for activity matching the defined security rules.
## Figure: Successful deployment and runtime verification of Suricata IDS with the detection engine active and custom rule loaded.
<img width="940" height="233" alt="image" src="https://github.com/user-attachments/assets/c49769df-55e1-4572-a6c4-176b2ae9ac00" />

# IDS Testing Using Simulated Suspicious Network Traffic
## This screenshot demonstrates the generation of controlled test traffic to validate the Suricata IDS monitoring environment. HTTP connectivity was first confirmed by successfully retrieving content from the web server.
## To test detection capabilities, HTTP requests were generated using curl with a custom BadBot User-Agent, providing recognizable traffic that can be matched by a corresponding Suricata detection rule. In addition, Netcat (nc) was used to establish a TCP connection to host 10.14.3.10 on port 4444, where test messages were exchanged successfully.
## These controlled tests generate specific network patterns that can be inspected by Suricata. The results can then be correlated with Suricata's alert logs to demonstrate that the IDS is capable of identifying traffic matching the configured detection rules.
## Figure: Generation of controlled HTTP and TCP test traffic using curl and Netcat for Suricata IDS detection and alert validation.
<img width="940" height="1061" alt="image" src="https://github.com/user-attachments/assets/907750d0-41b3-41dd-aeb2-4255e4db4123" />


# HTTP and TCP Service Testing for IDS Validation
## This screenshot demonstrates the server-side configuration used to generate and verify network traffic for Suricata IDS testing. A Python HTTP server was deployed on TCP port 80, and multiple HTTP GET requests were successfully received from the client at 10.14.3.20. Each request returned an HTTP 200 status code, confirming successful application-layer communication.
## A Netcat listener was also configured on TCP port 4444 using nc -l -p 4444. The server successfully received test messages sent from the remote client, confirming bidirectional TCP communication over the designated test port.
## These controlled HTTP and Netcat sessions provide reproducible network traffic that can be monitored by Suricata and correlated with the configured IDS rules and alert logs. This supports verification that the IDS can observe and analyse traffic across the monitored network.
## Figure: Server-side HTTP and Netcat services receiving test traffic for Suricata IDS monitoring and detection validation.
<img width="940" height="514" alt="image" src="https://github.com/user-attachments/assets/d7d5df3e-a55d-4300-81a2-75f7445181e4" />

# Suricata IDS Alert Generation and Detection Verification
## This screenshot demonstrates the successful detection and logging of suspicious network activity by the Suricata Intrusion Detection System (IDS). Suricata was executed on the monitored eth0 interface, and the detection engine initialized successfully with the configured custom rules.
## The fast.log output confirms that Suricata generated alerts for the controlled security tests. A suspicious HTTP User-Agent (BadBot) was detected and classified as a Web Application Attack. Suricata also detected outbound TCP connections to port 4444, which were identified by the custom rule as potential reverse-shell activity and classified as Network Trojan traffic.
## The alerts include relevant information such as timestamps, source and destination IP addresses, TCP ports, classification, and priority, demonstrating that Suricata was actively inspecting traffic and correctly matching network activity against the configured detection rules.
## This provides clear evidence that the Suricata IDS deployment is operational and capable of generating security alerts for predefined suspicious network behaviour.
## Figure: Suricata fast.log showing successful detection of a suspicious HTTP User-Agent and TCP port 4444 traffic generated during controlled IDS testing.
<img width="940" height="296" alt="image" src="https://github.com/user-attachments/assets/99524e1f-061d-4ad0-85b4-4f03812a6e5b" />

# Suricata EVE JSON Alert Verification
## This screenshot shows the Suricata eve.json log generated during IDS testing. The log confirms that the custom BadBot User-Agent rule was successfully triggered and classified as a Web Application Attack. It also records key details such as source/destination IP addresses, ports, protocol, and HTTP information.
## Figure: Suricata eve.json log confirming successful detection and detailed logging of the custom security alert.
<img width="940" height="458" alt="image" src="https://github.com/user-attachments/assets/861e3b21-8231-4aa5-be25-c2a9aa865c47" />

<img width="1920" height="1080" alt="{8C3DED52-32C7-453E-B4AF-0A11B111EB35}" src="https://github.com/user-attachments/assets/23e9938f-4fde-4b6f-8021-706a8182fbdb" />

# KDC Server – DNS and Connectivity Verification
# Configured the KDC server’s /etc/hosts file with hostname-to-IP mappings for the KDC, server, client, and OPNsense hosts. I then tested connectivity by pinging client.example.com from the KDC server. The successful replies with 0% packet loss confirmed that hostname resolution and network connectivity between the KDC and client were working correctly.
<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/290df722-7c21-408c-8b8e-15ea3204706c" />
# Kerberos Server – Connectivity and Keytab Verification
## Verified connectivity from the server to both the client and KDC using ping tests with 0% packet loss. I then downloaded the server.keytab file from the KDC and used klist -k to confirm that the required Kerberos service principals were successfully stored in the keytab.
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/8497a5c7-4ef6-4140-8aa0-5dd3d52fd7b3" />
# KDC – Kerberos Principal and Keytab Configuration
## Initialized the Kerberos database for the EXAMPLE.COM realm and started the KDC services. I then created the admin, host/server, and host/client principals and generated the server.keytab. Finally, I used listprincs to verify that all required Kerberos principals were successfully created.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/39a0c2eb-8152-4bfb-b439-91e0008e1f2d" />
# Kerberos Client – Authentication Verification
## Authenticated the user tahsin@EXAMPLE.COM using the kinit command. I then used klist to verify that a valid Kerberos Ticket Granting Ticket (TGT) was successfully issued by the KDC, confirming that Kerberos client authentication was working correctly.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/fa00e3b6-1de1-445e-b6b6-c91293bc7e98" />

# Kerberos SSH – Passwordless Authentication Verification
## Successfully authenticated with Kerberos using kinit and verified the valid ticket with klist. I then connected from the client to server.example.com using SSH with GSSAPI/Kerberos authentication, without entering the server account password. The final test with password authentication disabled confirmed that access was provided through Kerberos authentication rather than a password.
<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/1029ae0d-7e55-48c2-a451-5b53ef936646" />

# Kerberos Traffic Capture – Wireshark Verification
## Captured the Kerberos authentication traffic using Wireshark. The capture shows Kerberos packets, including TGS-REQ and TGS-REP, exchanged between the client and KDC. This provides network-level evidence that the client requested and received a service ticket as part of the Kerberos authentication process.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/e5ed563f-b7ab-4e45-a03b-4777c48bd2d6" />

# Kerberos Protocol – Wireshark Analysis
## Applied the kerberos display filter in Wireshark to isolate Kerberos traffic. The capture clearly shows AS-REQ/AS-REP and TGS-REQ/TGS-REP exchanges between the client and KDC, confirming successful ticket-based Kerberos authentication and service ticket exchange.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/e00f35c4-14a7-4bf5-8e26-616039a8a946" />

# Tailscale Inter-Site Connectivity Verification
## Established a Tailscale connection between my site and my teammate Antu’s site. I then tested cross-site connectivity using ping, and the successful replies with 0% packet loss confirmed that both sites were securely connected and able to communicate through the Tailscale VPN.
<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/f1514e37-d4b3-4a8b-8552-c103875c6515" />

# SSH Server – GSSAPI Configuration
## Configured the SSH server to support Kerberos/GSSAPI authentication by enabling GSSAPIAuthentication and GSSAPICleanupCredentials in sshd_config. I also verified the server keytab file and restarted the SSH service to apply the configuration.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/75dbb999-64db-4b0b-beb0-d7edbc2f84b1" />






