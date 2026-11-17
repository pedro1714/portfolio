# Lab IAM Avanzado — Acceso condicional + PIM en Entra ID · SSO + SCIM en Okta

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Llevar mi [lab espejo de IAM](../../lab-iam-espejo/) al nivel que piden las vacantes serias: políticas de **acceso condicional** basadas en riesgo y **PIM** (Privileged Identity Management) en Entra ID, y en Okta una aplicación con **SSO (OIDC/SAML)** y **aprovisionamiento automático con SCIM**.

## Habilidad de vacante que prueba

"Experiencia con Entra ID: Conditional Access, PIM" y "Okta: SSO y SCIM provisioning" — requisitos textuales de roles de Analista IAM / IT Operations & IAM.

## Prerrequisitos

- Tenant Microsoft 365 E5 Developer (Entra ID) y cuenta Okta Developer ya creados (lab espejo)
- Usuarios y grupos de prueba existentes en ambos lados
- Navegador con acceso a ambos portales de administración

## Paso a paso

### Parte A — Entra ID
1. Crear dos usuarios de prueba: uno "empleado estándar" y uno "administrador".
2. Crear una política de acceso condicional: exigir MFA cuando el inicio de sesión sea desde una ubicación no confiable (probar con/sin la condición y documentar el resultado).
3. Crear una segunda política en modo *report-only*, revisar su informe de impacto y luego activarla.
4. Configurar PIM: hacer elegible (no permanente) el rol de administrador para el usuario admin, con activación que requiera justificación y límite de horas.
5. Activar el rol desde PIM con justificación y comprobar que expira solo.
6. Registrar cada paso con capturas: política creada, aviso de MFA, activación PIM y expiración.

### Parte B — Okta
7. Registrar una aplicación web de prueba (OIDC) en Okta y completar un inicio de sesión SSO con un usuario de prueba.
8. Habilitar aprovisionamiento SCIM hacia una aplicación que lo soporte (o un destino SCIM de prueba): alta de usuario en Okta → usuario creado automáticamente en la app; baja → usuario desactivado.
9. Probar el ciclo completo: crear, modificar y desactivar un usuario y verificar la sincronización en cada caso.
10. Documentar la equivalencia: acceso condicional ↔ políticas de Okta; PIM ↔ roles administrativos de Okta.

## Entregable / evidencia final

- Documento comparativo con capturas de: las 2 políticas de acceso condicional funcionando, la activación/expiración de PIM, el login SSO y el ciclo SCIM (alta/cambio/baja sincronizados)
- Tabla de equivalencias Entra ID ↔ Okta redactada por mí

## Tiempo estimado

4–6 horas (en 2 sesiones)
