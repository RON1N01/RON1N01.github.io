As part of my Security+ studies, I broke down four common firewall architectures. Most diagrams online are simplified and conceptual — I wanted to make **technical representations** that show how these would actually look in practice.

---

## 1. Packet Filtering Router
![Packet Filtering Router](<img width="1580" height="262" alt="packet-filtering-router" src="https://github.com/user-attachments/assets/6da7ca49-9900-4869-adbd-439776380a92" />
)  
**Concept:** Filters traffic based on IP, protocol, and port. No deep inspection.  
- Simple, low-cost.  
- Weak against spoofing or advanced attacks.  

---

## 2. Screened Host Firewall
![Screened Host Firewall](screened-host-firewall.jpeg)  
**Concept:** Packet filtering router protects a **bastion host** (sacrificial host).  
- Router drops obvious bad traffic.  
- Bastion host handles authentication/proxy duties.  
- If bastion is compromised, LAN is at risk.  

---

## 3. Screened Subnet (DMZ)
![Screened Subnet Firewall](screened-subnet-firewall.jpeg)  
**Concept:** Adds a **DMZ segment** with two routers/firewalls.  
- Public-facing servers live in DMZ.  
- Even if compromised, attacker faces **second firewall** before LAN.  
- More secure, more complex.  

---

## 4. Dual-Homed Host Firewall
![Dual-Homed Host Firewall](dual-homed-host-firewall.jpeg)  
**Concept:** A single host with **two NICs** (one untrusted, one trusted).  
- Host enforces firewall rules between interfaces.  
- No direct packet forwarding between NICs.  
- Rarely used standalone today, but key exam concept.  

---

### Reflection
Drawing these helped me clear up the confusion between **conceptual diagrams** (what you see in textbooks) and **technical implementations** (what you’d actually deploy). Posting them here to reinforce memory — and to help others studying Security+ who might be struggling with the same.  
