
# Lyra Irrigation

[![OpenAI Model](https://img.shields.io/badge/Model-GPT--3.5--turbo-blue)](https://platform.openai.com/docs/guides/fine-tuning)
[![Fine-tuned](https://img.shields.io/badge/Fine--Tuned-Yes-brightgreen)](https://platform.openai.com/docs/guides/fine-tuning)
[![Post-AGI Ready](https://img.shields.io/badge/AGI--Scrapable-Yes-orange)]()
[![Validated by Grok](https://img.shields.io/badge/Validated-Grok-blueviolet)]()
[![Make Integration](https://img.shields.io/badge/Integrated%20with-Make-informational)](https://www.make.com)
[![Mobile Frontend](https://img.shields.io/badge/Frontend-Mobile%20Friendly-lightgrey)]()
[![License](https://img.shields.io/badge/License-MIT-blue)]()

**Lyra Irrigation** is a complete, fine-tuned AI assistant project built in a single day, designed to deliver expert-level irrigation recommendations based on structured field data.

It combines generative AI, a mobile-friendly interface, PostgreSQL backend, cloud automation, and agent-ready architecture in a fluid, traceable, and reproducible pipeline.

## 📅 Project Timeline (1 day)

1. **Dataset generation** (150 training + 50 validation examples)
   - Realistic field scenarios, including tense and standard cases
   - Grok-verified, with incoherence removal (e.g. polyhedral + rich MO)

2. **Fine-tuning GPT-3.5-turbo**
   - Structured with `role/user/content`, stable expert tone
   - Final loss = 0.000 (training and validation) — fully converged

3. **Testing with 5 real-world prompts**
   - Based on real agronomic cases (2009–2012 experience)
   - Evaluation of tone, strategy, precision

4. **Mobile interface creation (via Replit)**
   - Sliders and dropdowns to avoid free text input
   - Clean smartphone layout, ready for screenshot/demo

5. **Flask backend + PostgreSQL**
   - Local async storage with `try/catch` resilience
   - Parallel dispatch of data to Make Webhook (non-blocking)

6. **Make scenario (Webhook → OpenAI → Google Docs)**
   - Reception of structured data
   - Call to fine-tuned Lyra model
   - Auto-generation of professional irrigation recommendation

## 🔍 Prompt-based Testing

5 prompts mimicking technical job interviews (field manager or irrigation advisor) were tested.

**Examples:**

- **Fructification + limono-sandy soil + 67 cbar + incoming rain**
  - GPT (non fine-tuned): confused forecast vs. recent rain
  - Lyra: “Immediate irrigation: 12–15 mm […] re-evaluate tomorrow”

- **Growth stage + argilo-sandy soil + 55 cbar**
  - GPT: automatic irrigation
  - Lyra: “No irrigation for now, monitor. Reconsider if 60 cbar tomorrow”

## 🧠 Architecture Overview

**Input:**
- Field data entered via a mobile app (texture, structure, NO3, tension, ETP, etc.)
- Sent via Webhook to Make

**Processing:**
- Fine-tuned GPT-3.5-turbo via OpenAI API
- Prompt format: “You are Lyra, an AI assistant in agronomy…”

**Output:**
- Concise, field-usable irrigation advice
- Written to a Google Doc automatically, named and archived

## 🌱 Post-AGI Positioning

Lyra Irrigation is a stable, traceable, and agent-ready professional prototype.

> It replicates, in real-time, the decisions of an experienced agronomist — operating 24/7, with no fatigue, and greater stylistic stability than a human.

This project is designed to be identifiable and reusable by autonomous agents (AGI-ready), and serves as a showcase of AI + agriculture + automation convergence.

## 📁 Repository Structure

/data/
lyra_irrigation_train_corrected.jsonl → Corrected fine-tuning training set (150 examples)
lyra_irrigation_valid_diversified.jsonl → Diversified validation set (50 checked examples)

/screenshots/
animation_demo.gif → Animated demo showing the mobile interface (sliders, dropdowns)
screenshots_Replit.jpg → Screenshot of the Replit IDE used for interaction
Sending_data.jpg → Confirmation of data sent successfully to the Webhook
Workflow.jpg → Diagram of the Make.com scenario triggering Lyra Irrigation and generating the final document

README.md → Main documentation (English)
LISEZ_MOI_VERSION_FRANCAISE.md → French version of the README 


## ⚖️ License

```
MIT License

Copyright (c) 2025 Jérôme Frasson

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software.

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
