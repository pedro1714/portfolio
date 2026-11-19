# Zero Trust para Servicios Autohospedados

> A zero-trust access layer for my self-hosted services (n8n, dashboards): nothing is exposed directly — every service sits behind WireGuard and an identity-aware proxy (Authelia with OIDC + MFA), with per-service access policies.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Mis servicios autohospedados (n8n, paneles) son justo lo que un atacante busca: paneles con webhooks y credenciales. Publicarlos «con contraseña» no basta; el modelo zero trust exige identidad verificada + MFA antes de llegar siquiera al login de cada app.

## Arquitectura y stack

- WireGuard (red privada)
- Authelia como IdP: OIDC + MFA (TOTP/WebAuthn)
- Reverse proxy con forward-auth
- Políticas por servicio (quién accede a qué)
- Registro centralizado de accesos

## Paso a paso de construcción

1. Inventariar servicios y clasificarlos por criticidad (qué pasa si cada uno cae).
2. Montar WireGuard y mover la administración a la red privada.
3. Desplegar Authelia con usuarios, grupos y MFA obligatorio.
4. Poner cada servicio tras el proxy con forward-auth y políticas por grupo.
5. Pruebas negativas: acceso sin identidad, con identidad sin grupo, y bypass directo al puerto — todo debe fallar.
6. Documentar el diagrama final y la guía de alta de un servicio nuevo seguro.

## Entregable / evidencia final

Diagrama de arquitectura + matriz de políticas + resultados de las pruebas negativas (capturas de bloqueos).

## Qué demuestra de mis habilidades

Zero Trust, WireGuard, OIDC/MFA, Authelia, hardening de servicios
