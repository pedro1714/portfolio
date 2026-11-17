# Lab Hardening de Windows Server / Active Directory — GPO, LAPS y Tiering

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Montar un dominio de práctica y endurecerlo como se hace en una empresa: aplicar una **línea base de seguridad por GPO**, desplegar **LAPS** para las contraseñas de administradores locales y organizar las cuentas administrativas por **niveles (tiering)** para que una credencial robada no valga para todo.

## Habilidad de vacante que prueba

"Administración y hardening de Windows Server / Active Directory, GPO, LAPS" — requisito frecuente en roles de soporte avanzado, infraestructura y seguridad en el sector financiero.

## Prerrequisitos

- VMware Workstation con capacidad para 2 VMs más (64 GB RAM disponibles)
- ISO de Windows Server (versión de evaluación) y una VM Windows cliente
- Mi PC como anfitrión; red interna del laboratorio aislada

## Paso a paso

1. Instalar Windows Server, promoverlo a controlador de dominio (`lab.local`) y unir la VM cliente al dominio.
2. Crear la estructura de OUs: usuarios, equipos, servidores y cuentas administrativas por nivel.
3. Aplicar una línea base de GPO: política de contraseñas y bloqueo, auditoría de inicios de sesión, desactivación de protocolos débiles (SMBv1, LLMNR) y restricción de software no firmado.
4. Verificar la aplicación con `gpresult` desde el cliente y corregir un fallo deliberado de aplicación de GPO (diagnóstico guiado).
5. Desplegar **LAPS**: extender el esquema, delegar permisos de lectura solo al grupo correcto y comprobar que cada equipo tiene una contraseña de admin local única y rotada.
6. Implementar **tiering**: cuentas separadas para Nivel 0 (dominio), Nivel 1 (servidores) y Nivel 2 (estaciones), con GPO que impidan iniciar sesión "hacia abajo" (un admin de dominio no inicia en una estación común).
7. Prueba de control: intentar reutilizar una credencial de Nivel 2 en el servidor y documentar el bloqueo.

## Entregable / evidencia final

- Exportación de las GPO aplicadas (informes HTML de GPMC) y capturas de `gpresult`
- Captura de LAPS mostrando contraseñas distintas por equipo y el permiso delegado correcto
- Diagrama simple del tiering aplicado + captura de la prueba de reutilización bloqueada
- Checklist de hardening reutilizable redactado por mí

## Tiempo estimado

4–6 horas (en 2 sesiones)
