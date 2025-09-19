# September 17, 2025 – Lab Notes

## Research & Exploration
- Asked about **Claude AI misuse** and adversarial fine-tuning risks.  
  - Key takeaway: *LoRA/PEFT can be abused to alter model behavior.*  
  - Learned that poisoned fine-tuning data can act as a **backdoor**, enabling unauthorized actions.  
  - Example risks: data exfiltration, lateral movement, adversarial prompts.

- Explored **open weights**:  
  - Parameters are trained weights.  
  - “Open weights” = public release of those trained parameters.  
  - These can be wrapped into an agent and run locally.

- Learned about **mixture-of-experts (MoE)**:  
  - Technique where only a subset of model experts are activated per query → efficiency and scaling.  

- Built an **LLM + Agent + Tools diagram** to visualize roles:  
  - **LLM** = core reasoning engine.  
  - **Agent** = orchestration + decision layer.  
  - **Tools/Environment** = APIs, shells, browsers, etc.

![diagram](/assets/img/llm/2025-09-17-llm-agent-tools-diagram.png)

---

## Sys Admin
- Investigated **Intune enrollments**.
