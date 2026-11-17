# Lab SOC — Wazuh + Sysmon + MITRE ATT&CK con Atomic Red Team

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Convertir mi lab Wazuh existente en un lab de detección "de verdad": instrumentar la VM víctima con **Sysmon**, escribir reglas de detección en Wazuh **mapeadas a técnicas de MITRE ATT&CK** y validarlas ejecutando esas mismas técnicas con **Atomic Red Team** desde la VM Kali.

## Habilidad de vacante que prueba

"Experiencia SOC: creación de reglas de detección, conocimiento de MITRE ATT&CK, Wazuh/SIEM" — el núcleo de los roles de Analista SOC / Analista Jr SOC.

## Prerrequisitos

- Lab existente: VM Kali (atacante) + VM víctima con agente Wazuh reportando
- Configuración Sysmon (tipo SwiftOnSecurity u Olaf Hartong) para la víctima Windows
- Atomic Red Team instalado en el entorno de ataque
- Mi flujo de triaje con n8n/Ollama (opcional, para la fase final)

## Paso a paso

1. Instalar Sysmon en la VM víctima con una configuración conocida y verificar que los eventos llegan a Wazuh.
2. Elegir 5 técnicas ATT&CK ejecutables en el lab (ej.: T1059.001 PowerShell, T1003.001 LSASS credential dumping en entorno controlado, T1547.001 Run keys, T1071.001 C2 web, T1489 o equivalente seguro para el lab).
3. Para cada técnica: ejecutarla primero **sin regla propia** y registrar qué detecta Wazuh "de fábrica" y qué se le escapa.
4. Escribir/ajustar la regla de detección en Wazuh para cada técnica, con el ID de técnica ATT&CK en la descripción de la regla.
5. Re-ejecutar cada técnica con Atomic Red Team y verificar que la alerta correcta se genera (y que llega con el nivel adecuado).
6. Generar actividad benigna parecida (administración legítima con PowerShell) y comprobar que la regla no se convierte en fuente de falsos positivos — o documentar el ajuste fino necesario.
7. (Opcional) Pasar las alertas del ejercicio por mi clasificador de triaje y registrar su veredicto.

## Entregable / evidencia final

- Matriz de detección: técnica ATT&CK × (detectada de fábrica / con mi regla / no detectada), con la regla escrita para cada caso
- Exportación de las reglas personalizadas de Wazuh y capturas de las alertas generadas
- Mini-informe: qué técnicas costaron más y qué falsos positivos aparecieron

## Tiempo estimado

5–7 horas (en 2–3 sesiones)
