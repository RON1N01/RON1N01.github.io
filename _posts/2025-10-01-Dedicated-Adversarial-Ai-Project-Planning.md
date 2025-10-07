---
title: "DAAI — Isolated Adversarial AI Lab Project Planning"
date: 2025-10-01
tags: [adversarial-ai, model-security, isolation]
---

## Objective
Establish an air-gapped lab to test LLM adversarial behavior safely.

## Key Controls
- Air-gapped host; network disabled by default.
- No external APIs or telemetry; controlled.

## Initial Actions
- Provision Ubuntu LTS sandbox and Python venv template.
- Import first local model (Qwen/Mistral), run red-team prompt suite.

