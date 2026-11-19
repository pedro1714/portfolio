# DFIR con Velociraptor y Sysmon

> A DFIR lab: Velociraptor deployed over my Windows victim VM (with Sysmon) to run live hunts and collections — process trees, persistence mechanisms, network connections — and answer an incident scenario end to end with evidence.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Responder a un incidente sin telemetría es adivinar. Velociraptor es la herramienta DFIR abierta que usan equipos reales para recolectar y cazar en endpoints a escala; dominarla es una habilidad SOC/DFIR directamente vendible.

## Arquitectura y stack

- Velociraptor (servidor + agente)
- Sysmon con configuración conocida en la víctima Windows
- Artefactos VQL (consultas personalizadas)
- Escenario de incidente con Atomic Red Team como «atacante»
- Wazuh para correlacionar con las alertas del SIEM

## Paso a paso de construcción

1. Desplegar el servidor Velociraptor y enrolar la VM víctima con Sysmon activo.
2. Recorrer los artefactos base: procesos, conexiones, persistencia, usuarios, historial.
3. Escribir 3 consultas VQL propias (ej.: procesos hijos anómalos de Office; Run keys nuevas; conexiones a puertos raros).
4. Ejecutar el escenario de ataque y responder solo con Velociraptor: qué pasó, en qué orden, qué quedó en la máquina.
5. Correlacionar los hallazgos con las alertas que Wazuh generó del mismo escenario.
6. Redactar el informe del incidente con línea de tiempo y evidencias.

## Entregable / evidencia final

Informe DFIR completo del escenario + las 3 consultas VQL + línea de tiempo con evidencias exportadas.

## Qué demuestra de mis habilidades

DFIR, Velociraptor/VQL, Sysmon, respuesta a incidentes, threat hunting
