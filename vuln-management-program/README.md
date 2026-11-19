# Programa de Gestión de Vulnerabilidades (Tenable + EPSS/KEV)

> A small but complete vulnerability management program: scheduled Tenable scans of my lab, prioritization that goes beyond CVSS (EPSS exploit probability + CISA KEV), SLA clocks per severity, and an n8n dashboard that tracks remediation like a real program.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Escanear no es gestionar: sin priorización real ni SLA, los informes se acumulan y lo crítico se mezcla con el ruido. Este proyecto monta el ciclo completo — descubrir, priorizar, remediar, verificar — a escala de laboratorio pero con criterios de empresa.

## Arquitectura y stack

- Tenable (Nessus Essentials) — escaneos programados
- CVSS + EPSS + catálogo CISA KEV para priorizar
- n8n + hoja/tablero para SLA y seguimiento
- Re-escaneo de verificación por ciclo
- Informe ejecutivo por ciclo (una página)

## Paso a paso de construcción

1. Definir el alcance y el calendario de escaneos del lab (descubrimiento + vulnerabilidades con credenciales).
2. Crear la matriz de priorización: CVSS base ajustado por EPSS y presencia en KEV.
3. Definir SLA por severidad (crítico 7 días, alto 30, medio 90) y el tablero que los vigila.
4. Correr el primer ciclo completo: escanear, priorizar, remediar lo crítico, re-escanear.
5. Automatizar con n8n el aviso de SLA vencidos y el informe del ciclo.
6. Cerrar con el informe ejecutivo: riesgo inicial vs residual y qué quedó fuera de SLA y por qué.

## Entregable / evidencia final

Matriz de priorización + tablero de SLA + informe ejecutivo de un ciclo completo con riesgo antes/después.

## Qué demuestra de mis habilidades

Vulnerability management, Tenable, EPSS, CISA KEV, SLA, reporting ejecutivo
