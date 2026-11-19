# Línea Base de Seguridad de Entra ID con ScubaGear y Maester

> A Microsoft Entra ID security baseline project: my E5 developer tenant is assessed with CISA's ScubaGear and the Maester test framework, misconfigurations are fixed control by control, and the tenant ends with a repeatable, automated security test suite.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Entra ID concentra la identidad de la empresa y sus configuraciones inseguras (MFA parcial, apps consentidas, roles permanentes) son la puerta de entrada más común. Herramientas como ScubaGear (CISA) y Maester permiten auditar el tenant de forma repetible, no a ojo.

## Arquitectura y stack

- Tenant Microsoft 365 E5 Developer (Entra ID)
- ScubaGear (CISA) — evaluación de línea base
- Maester — tests de seguridad automatizados para Entra ID
- Acceso condicional, PIM, protección de identidad
- Informe de desviaciones y correcciones

## Paso a paso de construcción

1. Ejecutar ScubaGear sobre el tenant y registrar todas las desviaciones de la línea base.
2. Instalar Maester y correr su batería de tests inicial; guardar la línea base de fallos.
3. Corregir por bloques: MFA y acceso condicional, consentimiento de apps, roles privilegiados con PIM, políticas de contraseñas/autenticación.
4. Re-ejecutar ScubaGear y Maester tras cada bloque y documentar qué test pasa a verde.
5. Dejar la batería programada como chequeo periódico del tenant.
6. Publicar la guía: «línea base Entra ID para pymes» con los controles y su porqué.

## Entregable / evidencia final

Reportes ScubaGear/Maester antes y después + guía de línea base reutilizable + batería de tests versionada.

## Qué demuestra de mis habilidades

Entra ID, ScubaGear, Maester, Conditional Access, PIM, IAM hardening
