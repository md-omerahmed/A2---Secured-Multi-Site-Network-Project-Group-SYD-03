

<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/012e63ad-8d8b-47b1-9fa1-fbb24208af62" />

<img width="940" height="739" alt="image" src="https://github.com/user-attachments/assets/68fc127f-d8da-4332-90d9-40709d5cbd9a" />

<img width="940" height="698" alt="image" src="https://github.com/user-attachments/assets/98c24c84-aded-424b-ad2f-5fce646e2e78" />







<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1af3e4aa-0bbc-4264-83d3-6df82e5901e7" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/a375d81e-e37a-4f37-8493-f5dae6a046b6" />

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/6bf656a4-1d1a-412c-9510-1bd63efcfcf9" />

<img width="940" height="605" alt="image" src="https://github.com/user-attachments/assets/cace6247-ac9d-41ce-bb38-5f4a8aeebfc8" />

<img width="940" height="562" alt="image" src="https://github.com/user-attachments/assets/117792ad-1619-4d3d-9700-2a98d9869d3b" />

<img width="940" height="676" alt="image" src="https://github.com/user-attachments/assets/9c38a81a-4d40-40ee-80d0-4d4ab06ab10e" />

<img width="940" height="521" alt="image" src="https://github.com/user-attachments/assets/e900e36e-2b71-4cd0-a68a-550a2fd508d3" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b79a195a-728d-4461-b274-bf0d2cf1bca0" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/d9a2c59e-58a1-45bc-9dcd-9f3702a8342f" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/43896081-ac32-46a5-9470-b0bbde5879ef" />












# Project Work

# Topology
<img width="1920" height="1080" alt="{C831F2EB-4318-456B-80B5-3789267F9B42}" src="https://github.com/user-attachments/assets/0d8b152f-3235-4c33-8a49-659b789e3499" />

# Start the Tailscale Server
<img width="1920" height="1080" alt="{DF46FE8A-E73B-4B1C-B6B3-436CD65870B9}" src="https://github.com/user-attachments/assets/7e3fd922-43b9-4703-87a2-aabb471a1323" />

# Successful pinging from Tahsin to Antu's site
<img width="1920" height="1080" alt="{2EA90A17-62F5-4FA2-8F55-E62125FA7C17}" src="https://github.com/user-attachments/assets/0b29ccba-eaac-4c4e-94de-9c855e274b0f" />


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

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/31b12277-bb76-43d5-939a-1ed51a98e740" />

<img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/d3dd7741-d699-46c5-abb2-11d5c7b46a9e" />

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/fbc2363b-2dd9-44f8-85c9-e75685ce673f" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/ecb4ad10-9733-4ad2-b34c-714c95211cad" />

<img width="940" height="747" alt="image" src="https://github.com/user-attachments/assets/5e45728c-aa81-46d0-a4ba-ce9616159a48" />

<img width="940" height="703" alt="image" src="https://github.com/user-attachments/assets/ba65f861-81df-4979-9589-81123734a9a1" />
