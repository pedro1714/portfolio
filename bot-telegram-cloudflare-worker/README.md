# Bot de Telegram + Worker en la nube (Cloudflare)

> A personal assistant in two pieces: a Telegram bot on my PC for heavy work, and a Cloudflare Worker that keeps answering when the PC is off — so the assistant never fully goes down.
> Status: ✅ Built and in daily use.

**Estado:** ✅ Construido

## Qué es

Mi asistente personal con arquitectura de dos capas: un **bot de Telegram** que corre en mi PC (conectado a mis flujos de n8n y herramientas locales) y un **Worker de Cloudflare** que responde lo esencial cuando la PC está apagada. El resultado: siempre hay alguien al otro lado del chat, aunque la capa completa dependa de mi hardware.

## El problema que resuelve

Mis automatizaciones vivían en mi PC, y cada vez que la PC se dormía o un contenedor caía, el asistente moría con ella. Necesitaba una capa siempre encendida para lo básico y una capa potente para lo pesado, sin pagar un servidor.

## Arquitectura y stack

- **Telegram Bot API** como interfaz única
- **Cloudflare Workers** (capa gratuita) como respaldo siempre activo: responde consultas básicas sin tocar mi PC
- **n8n + servicios locales** en mi PC para las tareas pesadas (fábrica de contenido, revisor ATS, cerebros de investigación)
- Diseño por degradación elegante: si la PC está apagada, el Worker contesta y deja claro el límite; nada finge funcionar

## Paso a paso: cómo se construyó

1. Monté primero el bot local conectado a mis flujos de n8n: comandos para consultar y disparar mis sistemas desde el teléfono.
2. Diagnosticué el problema real: la disponibilidad. Cada caída de la PC era una caída total del asistente.
3. Creé el Worker en Cloudflare con las respuestas y consultas que no necesitan mi PC.
4. Definí el reparto: el Worker atiende primero lo básico; lo que requiere mis sistemas locales se deriva al bot cuando la PC está en línea.
5. Probé el comportamiento en los dos estados (PC encendida/apagada) y ajusté los mensajes para que el límite fuera transparente, no un error silencioso.

## Estado real

✅ Construido y en uso diario. El Worker es la pieza más estable del sistema; la capa local sigue dependiendo de que mi PC y sus contenedores estén en pie.

## Qué demuestra de mis habilidades

- Arquitectura híbrida local/nube con degradación elegante
- Cloudflare Workers y Telegram Bot API en un sistema real de uso diario
- Diseño honesto de límites: el sistema dice qué puede y qué no puede hacer en cada estado
