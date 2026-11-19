# Detection Engineering con Sigma y MITRE ATT&CK

> A detection-as-code project: portable Sigma rules for my Wazuh lab, mapped to MITRE ATT&CK, validated in CI and tested against Atomic Red Team executions — with a coverage matrix that shows exactly which techniques I can and cannot detect.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Los SIEM detectan «lo que trae de fábrica» y nadie sabe qué cobertura real hay contra las técnicas que usan los atacantes. La ingeniería de detección lo resuelve tratando las reglas como código: versionadas, probadas y medidas contra ATT&CK.

## Arquitectura y stack

- Sigma (reglas portables) + sigma-cli / pySigma
- Wazuh como SIEM destino
- Atomic Red Team para validar detecciones
- GitHub Actions: validación de sintaxis y pruebas en cada commit
- Matriz de cobertura ATT&CK (Navigator)

## Paso a paso de construcción

1. Seleccionar 15 técnicas ATT&CK ejecutables en mi lab (las del Lab SOC y 10 más).
2. Escribir cada detección como regla Sigma con nivel, fuentes de log y falsos positivos conocidos documentados.
3. Convertir las reglas Sigma al formato de Wazuh y desplegarlas en el lab.
4. Montar CI: cada regla pasa validación de sintaxis y un test con logs de ejemplo antes de aceptarse.
5. Ejecutar cada técnica con Atomic Red Team y registrar: detectada / parcial / no detectada.
6. Publicar la matriz de cobertura en ATT&CK Navigator y el informe de huecos con su plan de cierre.

## Entregable / evidencia final

Repositorio de reglas Sigma versionado + matriz ATT&CK Navigator exportada + informe de cobertura con huecos y prioridades.

## Qué demuestra de mis habilidades

Detection engineering, Sigma, MITRE ATT&CK, Wazuh, CI para seguridad
