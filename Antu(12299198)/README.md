# Week 8 class work
## Topology made by me 
<img width="1916" height="946" alt="image" src="https://github.com/user-attachments/assets/bf08ae2a-458c-4c92-914c-df7af8dd6349" />

## Connecting with one of my group member Tahsin 
<img width="1920" height="989" alt="image" src="https://github.com/user-attachments/assets/d7a62a6c-6e44-4c5f-86d3-0119f21acde2" />

## Demo Topology 
<img width="1919" height="1027" alt="image" src="https://github.com/user-attachments/assets/95cea0a2-41c3-49bb-b63a-0ae5c73496d6" />

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
# 
