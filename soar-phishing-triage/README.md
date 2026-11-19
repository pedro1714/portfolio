# SOAR Casero: Triaje Automático de Phishing con n8n

> A SOAR-style playbook in n8n: a reported phishing email is parsed automatically — headers, SPF/DKIM/DMARC results, URL and attachment reputation — and the flow issues a verdict, creates the ticket and notifies the analyst with the full evidence attached.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

El phishing es la alerta más repetitiva de cualquier SOC: el analista pierde 15–30 minutos por correo en tareas mecánicas (cabeceras, reputación, capturas). Un playbook SOAR hace ese trabajo en segundos y deja al humano solo el veredicto difícil.

## Arquitectura y stack

- n8n como motor SOAR
- Análisis de cabeceras y resultados de autenticación (SPF/DKIM/DMARC)
- Consultas de reputación de URLs/dominios/hashes (APIs públicas)
- Sistema de tickets (webhook) + notificación al analista
- Registro de veredictos para medir precisión del playbook

## Paso a paso de construcción

1. Definir la entrada: buzón/carpeta de «reportar phishing» o reenvío manual a un webhook.
2. Parsear el correo: remitente real vs mostrado, Return-Path, resultados de autenticación, IPs de origen.
3. Extraer y desfuscar URLs y adjuntos; consultar su reputación y antigüedad de dominio.
4. Aplicar la matriz de veredicto: legítimo / sospechoso / malicioso, con la evidencia que lo sustenta.
5. Crear el ticket con todo adjunto y avisar al analista solo cuando el veredicto no sea concluyente o sea malicioso.
6. Medir durante 2 semanas: tiempo ahorrado por correo y % de veredictos correctos.

## Entregable / evidencia final

Flujo n8n exportado + matriz de veredicto documentada + métricas de la prueba (tiempo/correo y precisión).

## Qué demuestra de mis habilidades

SOAR, n8n, análisis de phishing, autenticación de correo, automatización SOC
