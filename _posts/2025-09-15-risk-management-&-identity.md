---
title: "Risk Management & Identity"
date: 2025-09-15
categories: [Lab Notes, Security+]
---

## Key Topics Studied

- **Identity & Access Management**
  - Single Sign-On (SSO): one login grants access to multiple systems.  
    - Advantage: convenience, reduced password fatigue.  
    - Disadvantage: compromise = maximum exposure.  
  - Authentication methods: smart cards, biometrics, Kerberos, LDAP, Active Directory, SAML.  
  - Federation: transitive trust across multiple enterprises.  

- **PKI Concepts**
  - **Certificate chaining**: trust relationship from root CA down to intermediates.  
  - **Key escrow**: third party stores copies of private keys for recovery.  
  - **Certificate revocation**: CRLs identify invalid certs before expiry.  
  - **Key pairing**: every public key uniquely maps to a private key.  

- **Indicators of Compromise (IoCs)**
  - Impossible travel: logins from geographically distant places in impossible timeframes (e.g., New York → Tokyo in 20 seconds).  
  - Concurrent session usage: multiple simultaneous logins on one account.  
  - Resource consumption: bandwidth/disk exhaustion.  
  - Blocked content: firewalls filtering malicious activity.  

- **Risk Management**
  - Senior management responsibility: **expressing risk tolerance / appetite**.  
  - Risk owner: selects treatment options (accept, mitigate, transfer, avoid).  
  - Risk practitioner: performs assessments.  
  - Security management: establishes cybersecurity controls.  

---
