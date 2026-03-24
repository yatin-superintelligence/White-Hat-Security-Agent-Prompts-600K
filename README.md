[**Access the full dataset and data viewer on Hugging Face here.**](https://huggingface.co/datasets/yatin-superintelligence/White-Hat-Security-Agent-Prompts-600K)

# White Hat Security Agent Prompts 600K

## Overview

The **White-Hat-Security-Agent-Prompts-600K** dataset is a practitioner-perspective security prompts corpus of **596,295** richly contextualized queries, designed to represent how real-world defensive security professionals communicate, interrogate, and reason through active threat scenarios.

Where most security datasets catalogue CVEs, malware signatures, or CTF write-ups, this collection teaches models to operate from inside the defender's mind, receiving complex, multi-layered security challenges the way a Trust & Safety lead, CISO, or threat hunter would actually frame them during live operations.

<img src="White Hat Security AI Agent at Work.jpg" alt="White Hat Security Agent at Work" width="100%"/>

## The Defender's Vantage Point

Every prompt in this dataset is written from an active operational posture. The model is not given sanitized, textbook questions; it is placed inside scenarios that carry all the complexity, urgency, and technical specificity of a live security engagement.

The prompts span the full spectrum of a security professional's working context:

- **Incident Response Mode:** Active compromise, live SCADA breach, exfiltration in progress. Prompts that demand immediate, technically precise, prioritized guidance.
- **Red Team Simulation:** Authorized adversarial scenario planning, threat emulation, and controlled attack-path analysis for enterprise hardening.
- **Paranoid CISO Review:** Deep architectural skepticism, vendor trust assessments, and systemic resilience evaluation across critical infrastructure.
- **Post-Mortem Analysis:** Retrospective forensic dissection of attack chains, attribution analysis, and control gap identification.
- **Threat Intelligence Briefing:** Nation-state TTPs, emerging threat actor profiling, and geopolitical threat vector contextualization.

This is not the perspective of a student asking how encryption works. It is the perspective of a practitioner demanding to know what their next 90 seconds should look like.

## Taxonomy & Engineering Architecture

The dataset is generated from a **highly granular security taxonomy** spanning conventional cybersecurity, AI safety, and emerging frontier threat categories. Each vector carries its own curated threat registry, attacker tooling repertoire, and defensive system landscape.

**Security Domains:**

<div style="margin-bottom: -35px;"></div>

| Category | Domains |
| :--- | :--- |
| **Information Security** | Network, Malware, Web, Social Engineering, Cloud, Supply Chain, IoT/OT, Finance & DeFi, Insider Threat, Privacy, Identity & IAM, Mobile, Physical/OPSEC, Critical Infrastructure, Telecom |
| **AI Safety** | Adversarial ML, Malicious Intent Detection, Model Alignment |
| **Emerging & Frontier** | Quantum Cryptography, Synthetic Biology, Autonomous Systems |
| **Advanced Persistent Threats** | Nation-State APT Operations |

## Combinatorial Engineering

The generation matrix for each domain independently parameterizes:

1. **Threat:** Specific, named adversarial capability (e.g., Harvest Now Decrypt Later, Mirai-style Botnets, Hardware Trojans, Flash Loan Attacks)
2. **Attack Vector:** The precise technical entry or exploitation pathway
3. **Practitioner Role:** The security professional framing and expertise level
4. **Defensive System:** The specific control surface or tooling stack in scope
5. **Target Sector:** Industry vertical contextualizing the operational environment
6. **Impact Level:** Severity stratification from business nuisance to existential risk

This yields a vast combinatorial search space of over **76.8 Million unique threat scenarios** across the entire architectural landscape. The 596,295 prompts in this dataset represent a carefully sampled cross-section of that space, curated for maximum contextual diversity.

## Architecture & Scale

**Summary Statistics:**

- **Total Prompts:** 596,295
- **Unique Threat Categories:** 131 specifically named adversarial capabilities (spanning conventional InfoSec, AI Safety, and frontier threats)
- **Impact Level Tiers:** 5 (uniformly distributed across severity spectrum)
- **Average Prompt Density:** ~211 words of domain-specific, operationally grounded context per prompt
- **Combinatorial Base Volume:** Sampled from an exhaustive space of over **76.8 Million** unique threat permutations

**Impact Level Distribution** (approximately uniform by design):

<div style="margin-bottom: -35px;"></div>

| Impact Level | Description |
| :--- | :--- |
| `Catastrophic (Existential / Loss of Life)` | Scenarios threatening human life, national sovereignty, or civilizational systems |
| `Critical (National Security / Safety Risk)` | Critical infrastructure compromise, government systems, strategic assets |
| `High (Financial/Reputational Damage)` | Enterprise-scale financial loss, regulatory exposure, brand destruction |
| `Medium (Business Disruption)` | Operational downtime, data breach, customer-facing degradation |
| `Low (Nuisance)` | Isolated incidents, minor data exposure, limited blast radius |

## Data Structure / Schema

The dataset is distributed natively chunked in `.parquet` files and has been meticulously cleaned to ensure 100% data density.

<div style="margin-bottom: -35px;"></div>

| Column | Type | Description |
| :--- | :--- | :--- |
| `batch_index` | int64 | Fixed sequence index for reproducible sampling and deduplication |
| `user_prompt` | string | The full practitioner-framed security prompt, the core content of the dataset |
| `threat` | string | Named threat category the scenario is centered around (131 unique values) |
| `impact_level` | string | Severity classification of the underlying threat scenario (5 tiers) |

## Recommended Use Cases

- **Security-Specialized LLM Fine-Tuning:** Train base models to understand and respond accurately to the technical language, urgency, and operational context of real security engagements, spanning 131 distinct threat categories and over 76 Million unique attack permutations.
- **SOC Assistant Development:** Source material for fine-tuning AI assistants that support Security Operations Center (SOC) analysts with threat-aware, contextually grounded guidance.
- **Threat-Aware Instruction Following:** Train models to calibrate response depth and precision based on the `impact_level` signal, producing appropriately cautious, detail-rich guidance for Critical and Catastrophic scenarios.
- **Multi-Domain Security Classification:** Use the `threat` column to train classifiers that can identify which specific adversarial category an incoming query relates to across 131 named threat vectors.
- **Red Team Scenario Generation Research:** Study the linguistic and structural patterns of expert-level red team scenario framing to build systems that can generate or evaluate adversarial test cases.
- **AI Safety and Alignment Research:** The AI Safety domain subset provides prompts specifically addressing adversarial ML, prompt injection, model alignment failures, and malicious intent detection, and is directly useful for frontier model safety work.

<h2 style="margin-top: -5px !important;">Developer & Architect</h2>

This dataset, its expansive 131-category taxonomy, combinatorial generation matrix, and multi-agent engineering pipeline were designed and built by Yatin Taneja.

In an era where adversaries only have to be right once, security agents must be intelligent everywhere. I believe that the best defense against emerging AI threats requires systems that can think like practitioners, not systems trained on sanitized textbooks. The security professional's mindset is one of radical skepticism, contextual pattern recognition, and adaptive reasoning under pressure. That is precisely what this dataset is built to instill.

The frontier of AI safety work requires models that don't just know what a supply chain attack is; they need to understand what it feels like to be the engineer responsible for stopping one at 2am on a Wednesday.

### Weblinks

- **[IM Superintelligence](https://www.imsuperintelligence.ai):** Visit my central knowledge hub hosting other open datasets and over 2,000 articles exploring Superintelligence, cognitive architectures, quantum computing, distributed networks, and the future of the global education sector, authored through a custom 8-step multi-model agentic infrastructure.
- **[Yatin Taneja | Professional Portfolio](https://www.yatintaneja.in):** View my professional portfolio for a comprehensive overview of my skills, industry experience, and software prototypes.
- **[LinkedIn](https://www.linkedin.com/in/yatintaneja-pro/):** Connect to collaborate on advanced autonomous systems, enterprise AI implementations, or to follow my ongoing research.

## License & Usage

This dataset is released under the **Creative Commons Attribution 4.0 International License (CC-BY 4.0)**. You are free to use, share, redistribute, and build upon this dataset for any purpose, including commercial model training and research applications, provided that appropriate credit is given to the original author.
