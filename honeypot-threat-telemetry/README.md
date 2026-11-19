# Honeypot en VPS: Telemetría Real de Ataques

> A honeypot deployment (Cowrie/T-Pot) on a VPS: real internet attackers interact with a fake SSH/service surface, every session is logged, and a dashboard summarizes who attacks, from where, with what credentials and commands — pure defensive telemetry.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

La mejor forma de entender al atacante es observarlo sin riesgo. Un honeypot en un VPS barato recoge telemetría real (diccionarios de contraseñas, comandos post-explotación, orígenes) que alimenta criterio de defensa y contenido técnico con datos propios.

## Arquitectura y stack

- VPS (Oracle Always Free o Hetzner)
- Cowrie (honeypot SSH) o T-Pot (multi-honeypot)
- Panel de telemetría: sesiones, credenciales probadas, comandos, países
- Endurecimiento del host real: el honeypot es la única superficie
- Exportación de IOCs observados (para mi MISP)

## Paso a paso de construcción

1. Levantar el VPS endurecido: solo el honeypot expuesto, administración por llave y red separada.
2. Desplegar Cowrie con un sistema de archivos falso creíble y logging completo.
3. Dejarlo correr 2–4 semanas recogiendo sesiones reales.
4. Analizar: top de usuarios/contraseñas probadas, comandos más ejecutados, orígenes y horarios.
5. Exportar los IOCs útiles a mi instancia MISP del lab.
6. Publicar el informe de telemetría con las lecciones defensivas (qué contraseñas y puertos hay que proteger primero).

## Entregable / evidencia final

Dashboard de telemetría + informe de hallazgos con datos reales + lista de IOCs exportada.

## Qué demuestra de mis habilidades

Honeypots, Cowrie/T-Pot, threat telemetry, VPS hardening, análisis de atacantes
