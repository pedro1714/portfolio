# Sistema de Órdenes para Ecommerce (Shopify → n8n → Tablero)

> A designed system for a real pet-products store: a Shopify order webhook feeds n8n and a status board (New → Designing → Awaiting review → Correction requested → Approved → Sent), with cross-notifications so no design order — 100+ a day — gets lost. Proposal already presented to the store; pilot designed.
> Status: 💡 Planned — proposal presented and pilot designed; not yet implemented.

**Estado:** 💡 Planeado (propuesta presentada a la tienda; piloto diseñado)

## Qué es (la idea)

Un sistema de seguimiento de órdenes de diseño para una tienda real de productos para mascotas en Shopify: cada orden nueva entra por webhook a n8n y aparece en un tablero por estados — **Nueva → Diseñando → Esperando revisión → Corrección pedida (con motivo) → Aprobada → Enviada** — con avisos automáticos cuando una corrección está lista, enlace a Canva por orden y un resumen diario.

## El problema que resuelve

La tienda recibe más de 100 órdenes al día y las correcciones se pierden porque nadie avisa cuando están listas: el diseñador no sabe qué sigue, la tienda no sabe qué está trabado. El sistema convierte ese caos de mensajes sueltos en un flujo visible con responsables y estados.

## Arquitectura planeada

- **Shopify**: webhook de órdenes nuevas
- **n8n**: ingesta, clasificación (con prioridad "blankets primero") y notificaciones
- **Tablero** por estados (versión piloto: hoja compartida con las mismas columnas y estados del sistema final)
- Avisos cruzados diseñador ↔ tienda y resumen diario a las 8:00 a. m.

## Paso a paso planeado

1. Piloto de 1 semana con alcance limitado: órdenes nuevas del día, prioridad blankets, entrada manual en la hoja compartida.
2. Tres rutinas automáticas: resumen 8:00 a. m., caza de órdenes trabadas (>4 h sin movimiento) y aviso de "corrección lista".
3. Medición con línea base: órdenes perdidas y tiempo de detección antes vs durante el piloto.
4. Reporte de cierre del piloto y, si funciona, automatización completa con el webhook de Shopify.

## Estado real

💡 Planeado con trabajo real detrás: la propuesta formal ya fue presentada a la tienda y el plan del piloto está diseñado (alcance, estados, rutinas y criterios de éxito). La implementación espera el sí de la tienda.

## Qué demuestra de mis habilidades

- Análisis de procesos de negocio y diseño de sistemas de seguimiento
- Integración Shopify + n8n orientada a un problema operativo medible
