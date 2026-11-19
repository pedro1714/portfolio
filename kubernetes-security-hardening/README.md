# Seguridad en Kubernetes: Hardening de mi Clúster k3d

> A Kubernetes security project on my k3d cluster: Pod Security Standards enforced, NetworkPolicies isolating namespaces, Falco detecting runtime anomalies, and Trivy scanning every image — with deliberate attacks to prove each control works.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Kubernetes inseguro por defecto es un clásico: contenedores privilegiados, red plana e imágenes con CVEs críticos. Este proyecto aplica las cuatro capas de defensa estándar (admisión, red, runtime e imágenes) y las prueba atacándolas.

## Arquitectura y stack

- k3d (mi clúster local) + kubectl
- Pod Security Standards (restricted)
- NetworkPolicies por namespace
- Falco (detección en runtime)
- Trivy (escaneo de imágenes) + políticas de admisión

## Paso a paso de construcción

1. Desplegar una app de prueba en 2 namespaces comunicados (línea base insegura).
2. Aplicar Pod Security Standards «restricted» y documentar qué despliegues se rompen y por qué.
3. Aislar con NetworkPolicies: denegar todo por defecto y abrir solo los flujos necesarios.
4. Bloquear imágenes con CVEs críticos usando los reportes de Trivy como puerta de admisión.
5. Instalar Falco y provocar eventos: shell en contenedor, lectura de /etc/shadow, proceso inesperado.
6. Atacar el resultado final (contenedor privilegiado, escape de namespace, imagen vulnerable) y registrar qué capa detiene cada intento.

## Entregable / evidencia final

Manifiestos versionados de cada control + matriz ataque × capa que lo detuvo + alertas reales de Falco.

## Qué demuestra de mis habilidades

Kubernetes security, Falco, Trivy, NetworkPolicies, Pod Security Standards
