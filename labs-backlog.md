# Backlog de laboratorios para el portafolio — Pedro Gomez

Creado 2026-11-18 por orden de Pedro: convertir lo que guarda en su colección de Instagram **MUSE** y las plataformas tipo TryHackMe en laboratorios documentados que sumen renombre a su perfil (GitHub + LinkedIn + Instagram).

**Regla de honestidad:** todo lab nace como "pendiente de ejecutar". Solo pasa a "hecho" cuando Pedro lo corre en su PC/cuentas y hay evidencia (capturas). Cada lab terminado = un README en el repo `portfolio` + un post corto (LinkedIn/IG) con el formato de los referentes.

**Formato de writeup (el de los creadores que sigue):** objetivo → entorno → pasos con capturas → qué detectó el SIEM/defensa → regla o detección creada (Sigma si aplica) → lección aprendida → enlace a la plataforma.

## A. Desde su colección MUSE (guardados recientes, 16–18 nov 2026)

1. **Purple Team en un SOC real** — de @hacker.mentor (workshop en vivo, 18-nov): emular un ataque en su lab (Kali → víctima) y validar qué detecta su Wazuh. Es la extensión natural de su lab de tesis. Prioridad ALTA.
2. **TryHackMe — Advent of Cyber 2026** — de @realtryhackme (18-nov): GRATIS, un reto diario desde el 1-dic. 24 mini-labs = 24 entradas de portafolio y 24 posts cortos en diciembre. Prioridad ALTA (tiene fecha).
3. **RedTeam-Tools** — de @kobaskyy: repositorio de herramientas; probar 3 en el lab y documentar uso defensivo/ofensivo controlado.
4. **Auditoría de seguridad de código con IA** — de @pirknn (skill gratis de Cloudflare): auditar un repo propio, documentar hallazgos y correcciones. Conecta con su tema de tesis de LLMs.
5. **IA local por niveles de RAM** — de @alvaro.lazarus: Pedro tiene 64 GB y Ollama ya montado; convertirlo en writeup documentado ("qué modelos corren con 64 GB y para qué sirven en un SOC").

## B. Plataformas de labs (las que Pedro no recordaba)

- **TryHackMe** — ruta SOC Level 1 (SIEM, análisis de logs, Wazuh/Splunk) + Advent of Cyber.
- **Hack The Box** — máquinas y **Sherlocks** (retos blue team/DFIR).
- **CyberDefenders** — retos de análisis: PCAP, memoria, logs, endpoints.
- **LetsDefend** — SOC simulado con alertas reales para practicar triaje (su tema de tesis).
- **Blue Team Labs Online (BTLO)** — investigaciones blue team por puntos.
- **DockerLabs** — plataforma de **El Pingüino de Mario**: máquinas vulnerables en Docker, ligeras y en español; ideales para la parte ofensiva/purple sin VMs pesadas.
- **PortSwigger Web Security Academy** — labs web gratuitos (base para appsec y su tema de LLMs).
- **OverTheWire / PentesterLab / picoCTF** — apoyo puntual (Linux, web, CTF).

## Orden sugerido (encaja en sus bloques de estudio)
1. Advent of Cyber 2026 (diario, diciembre) — ritmo y constancia pública.
2. Purple Team en su Wazuh (1 lab grande, reutiliza su tesis).
3. SOC Level 1 de TryHackMe (2–3 rooms por semana).
4. Sherlocks / CyberDefenders (1 por semana, blue team puro).
5. DockerLabs (1 máquina por semana, en español, con writeup estilo Pingüino de Mario).
