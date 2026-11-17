# Lab de IAM Espejo (Entra ID + Okta)

> A mirror IAM lab in progress: a Microsoft 365 E5 developer tenant (Entra ID) and an Okta Developer account run side by side — users, groups, MFA, Conditional Access vs Okta sign-on policies, SSO and admin roles — as my path to SC-300 and Okta Certified Professional.
> Status: 🔄 In progress.

**Estado:** 🔄 En curso

## Qué es

Un laboratorio de gestión de identidades y accesos (IAM) en dos plataformas en paralelo: un tenant de **Microsoft 365 E5** (programa de desarrolladores) con **Entra ID**, y una cuenta **Okta Developer**. Cada capacidad se practica en ambos lados para comparar cómo resuelven lo mismo dos ecosistemas distintos.

## El problema que resuelve

IAM es una de las puertas de entrada menos saturadas a ciberseguridad, y las vacantes piden experiencia demostrable con Entra ID u Okta. Este laboratorio es mi forma de construir esa experiencia de forma práctica y documentada, en ruta hacia las certificaciones SC-300 (Microsoft) y Okta Certified Professional.

## Arquitectura y stack

- **Microsoft Entra ID** (tenant E5 Developer): usuarios, grupos, MFA, acceso condicional, PIM, app de SSO
- **Okta Developer**: usuarios, grupos, políticas de inicio de sesión, app de SSO, roles de administrador
- Documentación comparativa lado a lado (qué equivale a qué en cada plataforma)

## Paso a paso: cómo se está construyendo

1. Elegí IAM como especialidad de arranque (antes que SOC/pentesting saturados) y definí la ruta: SC-300 primero, Okta Certified Professional en paralelo, SC-100 más adelante.
2. Creé el tenant Microsoft 365 E5 del programa de desarrolladores y la cuenta de Okta Developer.
3. Monté la estructura base en ambos: usuarios y grupos de prueba equivalentes.
4. Práctica guiada por pares: MFA en Entra ID ↔ MFA en Okta; acceso condicional ↔ políticas de sign-on de Okta.
5. En curso: aplicación SSO en ambos lados y roles privilegiados (PIM en Entra ID vs roles admin en Okta).
6. Cada práctica se documenta con capturas y notas para convertir el lab en evidencia presentable.

## Estado real

🔄 En curso: tenants creados y prácticas base realizadas; SSO y roles privilegiados en progreso. Es la base del [Lab IAM Avanzado](../labs/lab-iam-avanzado/) que ejecutaré después.

## Qué demuestra de mis habilidades

- Fundamentos de IAM en las dos plataformas que más piden las vacantes
- Aprendizaje comparado y documentado, orientado a certificación (SC-300 / Okta)
