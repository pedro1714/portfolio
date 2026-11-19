# Backups Inmutables y Drills de Restauración Anti-Ransomware

> A ransomware-resilient backup system for my lab following 3-2-1: restic repositories with immutable snapshots, offline copies, integrity verification, and timed restore drills that prove the backups actually work — including a simulated ransomware event.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

El backup que nunca se restaura es una esperanza, no un control. Y si el ransomware alcanza los backups, no hay recuperación. Este proyecto monta copias inmutables y las prueba con drills cronometrados y un evento simulado.

## Arquitectura y stack

- restic (snapshots cifrados e inmutables)
- Regla 3-2-1: 3 copias, 2 medios, 1 fuera de línea/externa
- Verificación de integridad programada (restic check)
- Drills de restauración con cronómetro y checklist
- Simulación de ransomware en una VM del lab

## Paso a paso de construcción

1. Definir qué se respalda (VMs clave, flujos n8n, documentos) y su RPO/RTO objetivo.
2. Montar restic con repositorio local + copia externa con inmutabilidad (snapshots que ni el admin del origen puede borrar).
3. Automatizar respaldos y verificación de integridad con alertas si algo falla.
4. Drill 1: restaurar un servicio completo desde cero, cronometrado, siguiendo solo el checklist.
5. Evento simulado: «cifrar» la VM origen y sus respaldos alcanzables; recuperar desde la copia inmutable.
6. Documentar el runbook de recuperación con los tiempos reales de cada drill.

## Entregable / evidencia final

Runbook de recuperación + resultados de los drills (tiempos reales) + evidencia del evento simulado recuperado.

## Qué demuestra de mis habilidades

Backup & recovery, restic, resiliencia ransomware, 3-2-1, runbooks
