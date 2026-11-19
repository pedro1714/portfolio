# Postura de Seguridad en AWS con Prowler (CIS Benchmarks)

> An AWS cloud security assessment on a free-tier account: Prowler scans against the CIS AWS Foundations Benchmark, findings are triaged by real risk, the account is hardened control by control, and a re-scan proves the before/after.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

La mayoría de brechas en la nube son errores de configuración, no exploits. Saber auditar una cuenta AWS contra CIS y corregirla es una de las habilidades cloud-security más pedidas — y demostrable con informes antes/después.

## Arquitectura y stack

- Cuenta AWS (capa gratuita) creada para el lab
- Prowler (auditoría CIS AWS Foundations)
- IAM con MFA y políticas de mínimo privilegio
- CloudTrail + GuardDuty + Security Hub (conceptos y activación)
- Informe de remediación priorizado

## Paso a paso de construcción

1. Crear la cuenta del lab y dejar deliberadamente 6–8 malas configuraciones típicas (S3 público, MFA ausente, llaves en root, grupos abiertos).
2. Ejecutar Prowler completo y clasificar hallazgos por riesgo real (exposición + explotabilidad).
3. Corregir control a control: IAM, S3, red, logging y monitoreo.
4. Activar CloudTrail y revisar qué eventos quedan registrados tras las correcciones.
5. Re-escanear con Prowler y documentar el antes/después por control.
6. Escribir la checklist reutilizable de «cuenta AWS segura desde cero».

## Entregable / evidencia final

Informes Prowler antes/después + checklist de hardening reutilizable + tabla de controles CIS corregidos.

## Qué demuestra de mis habilidades

AWS security, Prowler, CIS Benchmarks, IAM, cloud hardening
