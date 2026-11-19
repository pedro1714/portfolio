# Pipeline DevSecOps con GitHub Actions

> A DevSecOps pipeline for a real project of mine: every push runs SAST (Semgrep), secret scanning (gitleaks), dependency and container scanning (Trivy), and produces signed artifacts (cosign) — with a security gate that blocks merges on critical findings.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

La seguridad «al final» llega tarde. Este pipeline mete los controles en el flujo de desarrollo: cada cambio se escanea solo, los hallazgos críticos bloquean, y el artefacto final queda firmado para probar su origen.

## Arquitectura y stack

- GitHub Actions (CI)
- Semgrep (SAST) + gitleaks (secretos)
- Trivy (dependencias e imágenes)
- cosign (firma de artefactos)
- Reglas de protección de rama como puerta de seguridad

## Paso a paso de construcción

1. Elegir un proyecto propio (el Coding Agent Harness) y montar el workflow base de CI.
2. Añadir gitleaks: probar con un secreto falso sembrado y verificar que el pipeline lo bloquea.
3. Añadir Semgrep con reglas de seguridad y corregir el primer hallazgo real que aparezca en mi código.
4. Añadir Trivy para dependencias e imagen del contenedor; definir la política de severidades que bloquean.
5. Firmar el artefacto con cosign y verificar la firma en un paso separado.
6. Documentar la guía: cómo leer cada reporte y qué hacer cuando la puerta bloquea un merge.

## Entregable / evidencia final

Workflow versionado + capturas de cada control bloqueando un caso real + artefacto firmado y verificado.

## Qué demuestra de mis habilidades

DevSecOps, GitHub Actions, Semgrep, gitleaks, Trivy, cosign
