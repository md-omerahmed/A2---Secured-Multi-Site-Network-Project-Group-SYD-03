
# Demo Topology of Group Assesment
<img width="1920" height="1080" alt="{01D8856A-66F3-479E-9501-51DD22B07997}" src="https://github.com/user-attachments/assets/096a56eb-bcb0-4c2d-9ab4-8bc7517f4ace" />


<img width="940" height="516" alt="image" src="https://github.com/user-attachments/assets/0153edc3-8599-4ce6-b85f-ecc965fb14f7" />
<img width="940" height="677" alt="image" src="https://github.com/user-attachments/assets/8031467d-a981-4c20-b4e6-7964a367c481" />

# Figure 1 – Network Configuration:
## This screenshot shows the initial network configuration and interface setup used to prepare the host for communication within the secured network.
<img width="573" height="994" alt="{A2C5437C-2FA7-4AF9-A084-A7DE941470B6}" src="https://github.com/user-attachments/assets/25ff2353-8c69-4619-84c8-805c8bbc5ca6" />


# Figure 2 – OPNsense Interface Configuration:
## This screenshot shows the OPNsense interface configuration used to separate and manage traffic between the different network zones
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b608e445-0916-4334-adcf-8b4a2818f608" />

# Figure 3 – Firewall Connectivity Test:
## This screenshot demonstrates connectivity testing between hosts to verify whether the configured OPNsense firewall rules correctly allow or block network traffic.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1e1a0b87-f77f-4f2b-bd1a-4bc6e54cb029" />

# Figure 4 – OPNsense Firewall Live Log:
## This screenshot shows the OPNsense firewall live log, providing evidence of allowed and blocked traffic generated during firewall testing.
<img width="840" height="624" alt="image" src="https://github.com/user-attachments/assets/5717ecb0-872f-4a27-a537-bfd083bdba56" />

# WAN Firewall Rule:
## This screenshot shows the OPNsense WAN firewall rule configured to allow IPv4 TCP/HTTP traffic on port 80 to the DMZ_WEBSERVER, while other unmatched WAN traffic remains blocked by default.
<img width="1003" height="742" alt="image" src="https://github.com/user-attachments/assets/899de83c-8074-44ef-9b55-ec8af89b7b2e" />

# DMZ (OPT1) Firewall Rules:
## This screenshot shows the OPNsense DMZ (OPT1) firewall rules, allowing DNS traffic on port 53 from the DMZ_NET while blocking other unmatched IPv4 traffic to restrict access from the DMZ..
<img width="852" height="670" alt="image" src="https://github.com/user-attachments/assets/0cd600f4-e012-4447-9560-aa923cc57f94" />

# Figure 5Firewall Blocking Evidence:
## This screenshot shows the OPNsense firewall live log confirming that ICMP traffic from the LAN host (10.10.3.10) to 10.11.3.10 was blocked by the firewall.
<img width="940" height="648" alt="image" src="https://github.com/user-attachments/assets/ab848322-dd9c-4c31-a00d-7b6dabb04694" />

# Figure 6 – LAN Security Testing:
## This screenshot shows connectivity and access-control testing from the LAN host. The ping test received no replies, while the SSH connection to the DMZ host was refused, demonstrating the configured network restrictions.
<img width="940" height="753" alt="image" src="https://github.com/user-attachments/assets/a7edf2a4-358a-4370-b3ca-d30c944a4580" />

## Topology
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/31b12277-bb76-43d5-939a-1ed51a98e740" />

<img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/d3dd7741-d699-46c5-abb2-11d5c7b46a9e" />

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/fbc2363b-2dd9-44f8-85c9-e75685ce673f" />

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







