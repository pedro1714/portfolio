# Labs de práctica — índice

Guías paso a paso que diseñé para practicar y **evidenciar** habilidades que piden las vacantes, usando mi propio equipo. Estado de todos: 💡 **Guía lista — pendiente de ejecutar**. Nada de esto se presenta como trabajo realizado: cada lab define la evidencia que debo producir el día que lo ejecute.

**Mi equipo base:** PC con 64 GB RAM, VMware Workstation, Docker + k3d, laboratorio Wazuh con VM Kali (atacante) + VM víctima ya montado, n8n autohospedado y Ollama local.

| Lab | Habilidad que evidencia | Tiempo estimado |
|---|---|---|
| [Lab IAM Avanzado](lab-iam-avanzado/) | Acceso condicional + PIM (Entra ID); SSO + SCIM (Okta) | 4–6 h |
| [Lab SOC](lab-soc-wazuh-mitre/) | Detecciones Wazuh + Sysmon mapeadas a MITRE ATT&CK | 5–7 h |
| [Lab DMARC Real](lab-dmarc-real/) | SPF/DKIM/DMARC hasta `p=reject` con reportes rua | 3–4 h + ciclos de reporte |
| [Lab Hardening Windows Server / AD](lab-hardening-windows-ad/) | GPO baseline, LAPS, tiering administrativo | 4–6 h |
| [Lab Defensa contra Prompt Injection](lab-defensa-prompt-injection/) | OWASP Top 10 for LLM + guardarraíles | 4–5 h |
| [Lab Seguridad de Webhooks en n8n](lab-seguridad-webhooks-n8n/) | HMAC, secretos fuera del flujo, rate limiting | 2–3 h |
| [Lab Observabilidad](lab-observabilidad-k3d/) | Prometheus + Grafana sobre k3d | 3–4 h |
| [Lab Tenable Casero](lab-tenable-casero/) | Escaneo de vulnerabilidades + informe de remediación | 3–5 h |
