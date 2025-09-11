# Daily Lab Notes :: 2025-09-10

Title: Showing NIC & CPU Architecture Information

## Security+ Exam Simulation
- Reviewed results from the **SY0-701 Exam Simulation** PDF.  

- **Show NICs (Kali)**  
  - All interfaces (clean): `ip -brief address`  
  - Verbose alternative: `ip a`  
  - Routes (helpful for pivoting): `ip route`  
  - Open listening sockets: `ss -tulpen`  

- **Check CPU architecture in VMware Fusion**  
  - Confirm whether the VM is running **ARM vs x86** with:  
    ```bash
    uname -m
    ```
