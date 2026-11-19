# Enriquecimiento de Alertas SIEM con Threat Intelligence

> A threat-intel enrichment layer for my Wazuh lab: a MISP instance feeds indicators (IPs, domains, hashes) into an n8n enrichment flow that annotates every SIEM alert with reputation and context before the analyst sees it.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Una alerta sin contexto obliga al analista a investigar cada IP/dominio a mano. Con una capa de inteligencia, la alerta llega ya anotada — «esta IP está en tal feed, vista en tales campañas» — y el triaje se acelera y se equivoca menos.

## Arquitectura y stack

- MISP (plataforma de threat intelligence)
- Feeds públicos de IOCs
- n8n como capa de enriquecimiento (consulta y anotación)
- Wazuh (alertas) + mi clasificador de triaje
- Caché de consultas para no repetir llamadas

## Paso a paso de construcción

1. Desplegar MISP en el lab y conectar 2–3 feeds públicos de indicadores.
2. Mapear qué campos de una alerta de Wazuh son enriquecibles (IP origen, dominio, hash, URL).
3. Construir el flujo n8n: por cada alerta, consultar MISP y anotar coincidencias y reputación.
4. Integrar la anotación en mi clasificador de triaje (la coincidencia con un IOC conocido pesa en el veredicto).
5. Probar con tráfico del lab que toque indicadores reales de los feeds y con indicadores sembrados.
6. Medir: % de alertas enriquecidas y tiempo de triaje antes/después en el mismo set de alertas.

## Entregable / evidencia final

Flujo de enriquecimiento exportado + ejemplos de alertas anotadas + medición de impacto en el triaje.

## Qué demuestra de mis habilidades

Threat intelligence, MISP, Wazuh, n8n, SOC automation
