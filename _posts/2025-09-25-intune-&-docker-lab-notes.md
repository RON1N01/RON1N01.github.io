# Lab Notes – September 25, 2025

## Docker Experiments
- Verified Docker Desktop installation with `docker run hello-world`.  
- Launched an Ubuntu container using `docker run -it ubuntu bash`, confirming entry into a minimal shell environment.  
  - Key observation: Docker images are lightweight because they reuse the host kernel, unlike full virtual machine ISOs.  
- Considered security implications of container isolation and potential pivoting to the host kernel.  
- Evaluated the feasibility of running Kali Linux in a container.  
  - Determined that while command-line use is practical, graphical interface support is limited, making hypervisors better suited for GUI-heavy tools.  
- Noted Red Team use cases for Docker:
  - Rapid deployment of disposable lab environments.  
  - Packaging and distributing custom tools or exploits.  
  - Simulating attacker infrastructure without impacting the host environment.  

## Sysadmin Work – Intune and Autopilot
- Tasked with preparing a new Windows 11 ThinkPad under company device management.  
- Worked across `admin.microsoft.com`, `intune.microsoft.com`, and `entra.microsoft.com` to configure user and device enrollment.  
- Key steps completed:
  - Created a user account in Entra.  
  - Established device groups for the Project Manager role.  
  - Identified that Autopilot requires a hardware hash rather than the standard hardware ID.  
  - Observed the OOBE screen device-naming prompt as part of enrollment.  
- Clarified that Autopilot deployment profiles must be pre-assigned to groups/devices prior to user login.  
- Determined that Security Groups are preferable to Microsoft 365 Groups for device targeting in Entra.  

## GitHub Workflow
- Edited and published Markdown-based lab notes directly from the terminal using `vim`.  
- Reviewed the distinction between commit and push operations:  
  - `git commit` records changes locally within the repository history.  
  - `git push` transmits committed changes to the remote repository on GitHub.  
- Successfully published lab notes to the GitHub Pages site via the command line.  

## Open WebUI and Containers
- Deployed the Open WebUI container and confirmed its healthy running status using `docker ps`.  
- Compared Open WebUI’s interface to ChatGPT and noted similarities.  
- Practiced container lifecycle management, including termination and restart.  
- Prepared to rerun setup using an extracted one-liner script from a referenced tutorial.  

## Additional Technical Notes
- Practiced handling special characters during file renaming in zsh (escaping `&`).  
- Verified staged files and commit status within Git.  

---

### Reflections
- The day focused on strengthening both **endpoint management** (Autopilot/Intune) and **containerization fundamentals** (Docker).  
- Sysadmin exposure reinforced understanding of enterprise device onboarding, an area highly relevant to defensive and offensive security perspectives.  
- Docker continues to emerge as an efficient method for rapid lab creation, though the trade-offs with virtual machines remain important for penetration testing.  
