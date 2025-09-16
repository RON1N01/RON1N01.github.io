---
title: "Lab Notes – September 15, 2025: Risk Management & Identity"
date: 2025-09-15
categories: [Lab Notes, Security+]
---

# Lab Notes – September 15, 2025

## Key Topics Studied

- **Identity & Access Management**
  - Single Sign-On (SSO): one login grants access to multiple systems.  
    - Advantage: convenience, reduced password fatigue.  
    - Disadvantage: compromise = maximum exposure [oai_citation:0‡SY0-701 Exam Simulation-resullts-results.pdf](file-service://file-49oJfhqNbjPdwg2fCJU8mn).  
  - Authentication methods: smart cards, biometrics, Kerberos, LDAP, Active Directory, SAML.  
  - Federation: transitive trust across multiple enterprises.  

- **PKI Concepts**
  - **Certificate chaining**: trust relationship from root CA down to intermediates [oai_citation:1‡SY0-701 Exam Simulation-resullts-results.pdf](file-service://file-49oJfhqNbjPdwg2fCJU8mn).  
  - **Key escrow**: third party stores copies of private keys for recovery.  
  - **Certificate revocation**: CRLs identify invalid certs before expiry.  
  - **Key pairing**: every public key uniquely maps to a private key.  

- **Indicators of Compromise (IoCs)**
  - Impossible travel: logins from geographically distant places in impossible timeframes (e.g., New York → Tokyo in 20 seconds) [oai_citation:2‡SY0-701 Exam Simulation-resullts-results.pdf](file-service://file-49oJfhqNbjPdwg2fCJU8mn).  
  - Concurrent session usage: multiple simultaneous logins on one account.  
  - Resource consumption: bandwidth/disk exhaustion.  
  - Blocked content: firewalls filtering malicious activity.  

- **Risk Management**
  - Senior management responsibility: **expressing risk tolerance / appetite** [oai_citation:3‡SY0-701 Exam Simulation-resullts-results.pdf](file-service://file-49oJfhqNbjPdwg2fCJU8mn).  
  - Risk owner: selects treatment options (accept, mitigate, transfer, avoid).  
  - Risk practitioner: performs assessments.  
  - Security management: establishes cybersecurity controls.  

---
