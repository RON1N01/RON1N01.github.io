As part of my Security+ studies, I broke down four common firewall architectures. Most diagrams online are simplified and conceptual — I wanted to make **technical representations** that show how these would actually look in practice.

---

## 1. Packet Filtering Router
![Packet Filtering Router](/assets/img/firewalls/packet-filtering-router.png)  
**Concept:** Filters traffic based on IP, protocol, and port. No deep inspection.  
- Simple, low-cost.  
- Weak against spoofing or advanced attacks.  

---

## 2. Screened Host Firewall
![Screened Host Firewall](/assets/img/firewalls/screened-host-firewall.png)  
**Concept:** Packet filtering router protects a **bastion host** (sacrificial host).  
- Router drops obvious bad traffic.  
- Bastion host handles authentication/proxy duties.  
- If bastion is compromised, LAN is at risk.  

---

## 3. Dual-Homed Host Firewall
![Dual-Homed Host Firewall](/assets/img/firewalls/dual-homed-host-firewall.png)  
**Concept:** A single host with **two NICs** (one untrusted, one trusted).  
- Host enforces firewall rules between interfaces.  
- No direct packet forwarding between NICs.  
- Rarely used standalone today, but key exam concept.  

---

## 4. Screened Subnet (DMZ)
![Screened Subnet Firewall](/assets/img/firewalls/screened-subnet-firewall.png)  
**Concept:** Adds a **DMZ segment** with two routers/firewalls.  
- Public-facing servers live in DMZ.  
- Even if compromised, attacker faces **second firewall** before LAN.  
- More secure, more complex.  

---

### Reflection
Drawing these helped me clear up the confusion between **conceptual diagrams** (what you see in textbooks) and **technical implementations** (what you’d actually deploy). Posting them here to reinforce memory — and to help others studying Security+ who might be struggling with the same.  
