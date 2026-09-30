
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

<img width="940" height="747" alt="image" src="https://github.com/user-attachments/assets/5e45728c-aa81-46d0-a4ba-ce9616159a48" />

<img width="940" height="703" alt="image" src="https://github.com/user-attachments/assets/ba65f861-81df-4979-9589-81123734a9a1" />

<img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/2d880609-bae2-4fef-ba70-62186d9855dd" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/17bcfa50-5eae-4f50-9d7a-f14324261546" />
<img width="940" height="244" alt="image" src="https://github.com/user-attachments/assets/b89d1164-fee9-4c75-a7fa-bd1c53a3e25b" />
<img width="940" height="229" alt="image" src="https://github.com/user-attachments/assets/674d7dd0-1ce9-41b3-972a-d53685e15554" />
<img width="940" height="233" alt="image" src="https://github.com/user-attachments/assets/c49769df-55e1-4572-a6c4-176b2ae9ac00" />
<img width="940" height="1061" alt="image" src="https://github.com/user-attachments/assets/907750d0-41b3-41dd-aeb2-4255e4db4123" />
<img width="940" height="514" alt="image" src="https://github.com/user-attachments/assets/d7d5df3e-a55d-4300-81a2-75f7445181e4" />
<img width="940" height="296" alt="image" src="https://github.com/user-attachments/assets/99524e1f-061d-4ad0-85b4-4f03812a6e5b" />
<img width="940" height="458" alt="image" src="https://github.com/user-attachments/assets/861e3b21-8231-4aa5-be25-c2a9aa865c47" />

<img width="1920" height="1080" alt="{8C3DED52-32C7-453E-B4AF-0A11B111EB35}" src="https://github.com/user-attachments/assets/23e9938f-4fde-4b6f-8021-706a8182fbdb" />

<img width="940" height="417" alt="image" src="https://github.com/user-attachments/assets/f1514e37-d4b3-4a8b-8552-c103875c6515" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/75dbb999-64db-4b0b-beb0-d7edbc2f84b1" />






