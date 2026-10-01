# A2---Secured-Multi-Site-Network-Project
- Member 1 Name: Mohammed Omer Ahmed
- Member 1 Id: 12303667
- Member 2 Name: MD Tahsin Alom
- Member 2 ID: 12310850
- Member 3 Name: Antu Shil
- Member 3 ID: 12299198
- Campus: Sydney
- Tutor: Md Hossain
- Unit Coordinator: Steven Gordon

# Wireless Security Extension
In the future, should we decide to add wireless access to our secured multi-site network, we will need to add more security controls since wireless communication is less secure than a wired connection. An attacker does not necessarily need to have access to the organisation's equipment like with a wired network.

An evil twin attack, where an attacker sets up a fake wireless hotspot using a similar or identical network name, is one of the major dangers. It can be accessed by accident by a user who reveals sensitive data. A rogue access point is a potential threat as well, when an unauthorised wireless device is plugged in to the organisation's network. The deauthentication attack can also be employed to de-connect the legitimate user from the Wi-Fi, and the attack using the 4-way handshake (including KRACK attack) can target vulnerabilities in wireless authentication and encryption. These are the leading wireless related threats mentioned in the project specification.

In order to secure the wireless network, we would implement WPA3-Enterprise in combination with 802.1X authentication, EAP-TLS and RADIUS. This would be more secure than just having one shared password for everyone to use. A certificate-based authentication would also ensure that only authorized users and devices connect to the network.

We would also allow Management Frame Protection to help mitigate the threat of deauthentication and disassociation attacks. Also, SSID-to-VLAN segmentation would be used to separate the wireless network. For instance, there might be a staff VLAN and a guest VLAN where guests are not allowed to join the staff VLAN. Communication between these networks would be regulated by rules in the OPNsense firewall. Guest users would only have access to the internet, and not be able to reach important internal systems like the Kerberos KDC, management devices or protected servers.

Another idea would be to have a wireless intrusion-detection system to monitor wireless activity. This would assist in detecting rogue access points, suspicious authentication attempts or potential evil-twin networks. Alerts from the wireless monitoring system could then be similarly analyzed as the Suricata is used to analyze suspicious traffic in the current wired network.

These wireless security measures would complement our multi-site defence in depth network. There would not be a single control for security. Instead, the combination of WPA3-Enterprise, authentication, VLAN separation, management-frame protection and intrusion detection in OPNsense firewall rules would help minimize risk of unauthorised access.

The wireless portion of this assessment is merely a design discussion. We will NOT be required to design a wireless access point or set up a wireless network in GNS3. In this section, the authors provide an explanation of how the existing multi-site architecture can be expanded to provide wireless access in a secure manner.


# Project Planning and Kanban Board

The group used a GitHub Project Kanban board to plan, organise and track the progress of the secured multi-site network project. The board was divided into Todo, In Progress and Done sections so that the status of each task could be clearly monitored throughout the project. This matches the assessment requirement to use a GitHub Project for planning and task tracking. a2-secured-multisite-network-pr…
The tasks included building each member’s GNS3 site, configuring IP addressing, Tailscale, Kerberos, OPNsense firewall rules, the site-to-site VPN, Suricata IDS, packet-capture evidence, the wireless security section and final documentation. Tasks were moved between the columns as work progressed.
The Kanban board also helped divide responsibilities between the group members and made individual contribution easier to identify. GitHub Project activity can be used as one source of evidence when assessing each member’s contribution to the project.
<img width="1920" height="997" alt="{8BA7E0C5-245B-49E3-AF8B-137D84286588}" src="https://github.com/user-attachments/assets/2cc4fa89-e4a8-4421-a6bb-872606e3a763" />
Figure: GitHub Project Kanban board showing the planning and progress of the secured multi-site network project.

# Group Communication and Collaboration
Our group worked together regularly, so most of our communication was done face-to-face instead of through Microsoft Teams. During these meetings, we discussed the network design, divided tasks, tested configurations, and solved technical problems together.

Although the specification mentions using Microsoft Teams for communication, our group mainly relied on in-person collaboration because we were able to meet and work together directly.

We also have evidence of our teamwork through GitHub commits, the Kanban board, project files, screenshots, and other group activity. These show that all members contributed to the project. Below Selfie is the evidence that we were working together in the project.

<img width="4032" height="3024" alt="IMG_2465" src="https://github.com/user-attachments/assets/71255de1-996d-450b-be78-93e7943e9f61" />


<img width="1920" height="1080" alt="{15F37D22-E1E8-438E-8427-3624AD0D2AC6}" src="https://github.com/user-attachments/assets/24778fdf-0ba2-4e80-8259-c6124e7922af" />
