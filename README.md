# Pedro Gomez

**Information Security | IT Support | AI Automation**

Systems Engineer (UNAPEC, 2023) from Santo Domingo, Dominican Republic. I worked in information security and IT support in the Dominican financial sector (Bolsa y Mercados de Valores RD), with hands-on experience in vulnerability management (Tenable, Rapid7), endpoint protection (Trellix EDR) and Active Directory environments. I am currently pursuing a Master's in Cybersecurity (in progress) and I design and build my own AI automation systems with n8n and Python — every project in this portfolio was directed and built by me, end to end. Advanced English.

This portfolio is deliberately honest: every project is labeled with its **real** status — ✅ built, 🔄 in progress, 💡 planned — and the practice labs are step-by-step guides I have prepared but **not yet executed**. Nothing here is presented as finished if it isn't.

## En español (resumen)

Ingeniero en Sistemas (UNAPEC, 2023). Experiencia en seguridad de la información y soporte TI en el sector financiero dominicano. Maestría en Ciberseguridad en curso. Construyo sistemas reales de automatización con IA (n8n, Python) y laboratorios de seguridad (Wazuh, IAM). Cada proyecto indica su estado real: construido, en curso o planeado.

## Skills

| Area | Tools & skills (all hands-on) |
|---|---|
| Security operations | Wazuh (SIEM), Tenable, Rapid7, Trellix EDR, vulnerability management, alert triage |
| IT support & infrastructure | Active Directory, Windows / Windows Server, Linux, VMware, help desk |
| Networks | TCP/IP, DNS, DHCP, Wireshark |
| Email security | SPF, DKIM, DMARC deployment and reporting |
| Automation & AI | n8n (self-hosted workflows, webhooks), Python, local LLMs (Ollama), REST APIs, prompt engineering |
| Cloud & platforms | Cloudflare (Pages, Workers), Supabase, Shopify order flows |

## Projects

### ✅ Built

| Project | What it is |
|---|---|
| [Brain Router v2 (n8n)](router-de-cerebros-n8n/) | Academic research router for my master's thesis: queries scholarly APIs with automatic fallback and per-session memory |
| [SIEM False-Positive Triage Lab](lab-triaje-siem-wazuh/) | Kali + victim VM lab with Wazuh; an n8n + local LLM workflow triages alerts and measures false-positive reduction |
| [ATS Resume Reviewer (n8n)](revisor-cv-ats-n8n/) | Webhooks that compare a resume (text or PDF) against a job posting and report keyword coverage and gaps — it never invents skills |
| [AI Content Factory (n8n)](fabrica-contenido-ia-n8n/) | Image generation with consistent characters + a voice factory (Python + edge-TTS) exposed via webhooks |
| [Telegram Bot + Cloudflare Worker](bot-telegram-cloudflare-worker/) | Personal assistant that keeps answering even when the PC is off |
| [Ganalaloto](ganalaloto/) | Dominican lottery statistics page (frequencies, pairs, overdue numbers) from historical data |
| [Household Expense App](app-gastos-casa/) | Web app (Cloudflare Pages + Supabase) that auto-registers expenses from bank notification emails, with deduplication |
| [Local Second Brain](segundo-cerebro-local/) | Obsidian vault + a script that answers questions **only** from my own notes + an n8n capture flow. 100% local and free |
| [Coding Agent Harness](coding-agent-harness/) | A tool-using coding agent loop written from scratch in pure Python: confirmation before execution, destructive commands blocked |
| [AI Animated Video Pipeline](pipeline-video-animado-ia/) | Local rendering pipeline (FFmpeg + Python) with consistent characters and TTS voices; 2 episodes produced |
| [Study & Habit Tracking System](sistema-estudio-habitos/) | Python scripts that log study blocks, water and meals, with daily balance reports |

### 🔄 In progress

| Project | What it is |
|---|---|
| [IAM Mirror Lab](lab-iam-espejo/) | Microsoft 365 E5 (Entra ID) + Okta Developer tenant in parallel; path to SC-300 and Okta Certified Professional |
| [Kubernetes Learning with k3d](aprendizaje-kubernetes-k3d/) | Local cluster and a guided lab path |
| [Cybersecurity Master's Thesis](tesis-maestria-ciberseguridad/) | Two submitted topics: LLM vulnerabilities (prompt injection / jailbreak) and SIEM optimization with AI anomaly detection |

### 💡 Planned

| Project | What it is |
|---|---|
| [Personal Agent Team on a VPS](equipo-agentes-vps/) | OpenClaw + Hermes agents working in shifts under central direction, with n8n as the board |
| [Ecommerce Order System](sistema-ordenes-ecommerce/) | Shopify webhook → n8n → status board so no design order gets lost (proposal already presented; pilot designed) |
| [Digital Products](productos-digitales/) | n8n template packs for SMBs, an SMB cybersecurity playbook, a Certification Study Tracker |
| [Premium Automated Video Factory](fabrica-video-premium/) | Idea → published animated episode with no manual editing |

## From projects to services

Each built project is also proof of a service I offer as a freelancer (Fiverr / Upwork). The portfolio shows the work; the services are how a client can hire it.

| Built project | What it proves | Service |
|---|---|---|
| [ATS Resume Reviewer](revisor-cv-ats-n8n/) + [AI Content Factory](fabrica-contenido-ia-n8n/) | Production n8n workflows with webhooks, APIs and local/cloud AI | **Email security consulting — SPF / DKIM / DMARC**: domain authentication setup through to `p=reject`, with monitoring reports, so business email stops being spoofed and lands in the inbox |
| [Brain Router v2](router-de-cerebros-n8n/) + [AI Content Factory](fabrica-contenido-ia-n8n/) + [Second Brain](segundo-cerebro-local/) | End-to-end automation design: triggers, fallbacks, memory, integrations (Zotero/Notion, Telegram, Cloudflare) | **AI automation for SMBs**: custom n8n workflows that remove manual, repetitive work — order tracking, notifications, content pipelines, internal assistants |
| [SIEM Triage Lab](lab-triaje-siem-wazuh/) | Wazuh deployment, detection logic, and measurable alert-triage methodology | **Security consulting for small teams**: SIEM alert triage and false-positive reduction, vulnerability scan review and prioritized remediation guidance |
| [ATS Resume Reviewer](revisor-cv-ats-n8n/) | Document processing (PDF/text), keyword analysis, honest gap reporting | **HR process automation**: resume screening support and candidate-document workflows that report what is missing instead of inventing it |
| [Household Expense App](app-gastos-casa/) + [Ecommerce Order System](sistema-ordenes-ecommerce/) (planned) | Web apps with auth, databases and event-driven registration | **Internal tools & dashboards**: lightweight web apps and status boards for small operations |

## Practice labs — 💡 guides ready, pending execution

These are step-by-step labs I designed to practice and evidence specific job-posting skills on my own equipment (PC with 64 GB RAM, VMware, k3d, and an existing Wazuh lab with Kali + victim VMs). They are **guides I will execute**, not completed work — each one defines the final evidence I must produce when I run it.

| Lab | Skill it evidences | Est. time |
|---|---|---|
| [Advanced IAM Lab](labs/lab-iam-avanzado/) | Conditional Access + PIM in Entra ID; SSO + SCIM provisioning in Okta | 4–6 h |
| [SOC Lab](labs/lab-soc-wazuh-mitre/) | Wazuh + Sysmon detections mapped to MITRE ATT&CK, tested with Atomic Red Team | 5–7 h |
| [Real DMARC Lab](labs/lab-dmarc-real/) | SPF/DKIM/DMARC deployment to `p=reject` with rua reporting on a practice domain | 3–4 h + report cycles |
| [Windows Server / AD Hardening Lab](labs/lab-hardening-windows-ad/) | GPO baselines, LAPS, administrative tiering | 4–6 h |
| [Prompt-Injection Defense Lab](labs/lab-defensa-prompt-injection/) | OWASP Top 10 for LLM testing and guardrails on a small LLM app | 4–5 h |
| [n8n Webhook Security Lab](labs/lab-seguridad-webhooks-n8n/) | HMAC validation, secrets outside the flow, rate limiting | 2–3 h |
| [Observability Lab](labs/lab-observabilidad-k3d/) | Prometheus + Grafana monitoring of a k3d cluster | 3–4 h |
| [Home Tenable Lab](labs/lab-tenable-casero/) | Vulnerability scanning of my own lab + prioritized remediation report | 3–5 h |

## What I'm building next

- **Personal agent team on a VPS** — OpenClaw + Hermes agents in shifts, n8n as the control board.
- **Ecommerce order system** — Shopify → n8n → status board; proposal already presented to a real store, pilot designed.
- **Digital products** — n8n template packs and an SMB cybersecurity playbook.
- **Premium video factory** — from one-line idea to published episode, fully automated.

## Contact

- LinkedIn: [linkedin.com/in/pedro-gomezbernabel](https://www.linkedin.com/in/pedro-gomezbernabel)
- Freelance: Fiverr & Upwork — IT support, email security and n8n automation
