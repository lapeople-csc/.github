<!--
Plantilla por defecto de lapeople-csc: aplica a todo repo que NO tenga su
propio .github/pull_request_template.md. Este repo es PÚBLICO: no pongas aquí
enlaces internos ni datos sensibles.
Borra las secciones que no apliquen; no las dejes vacías.
-->

## Qué cambia y por qué

<!-- Una o dos frases: el problema y la solución. Lo demás lo cuenta el diff. -->

**Tarea:** <!-- [nombre](enlace de ClickUp) #id -->

## Cómo probarlo

<!--
Pasos para que el revisor (o QA) vea el cambio funcionando. Si es UI, agrega
capturas o un video corto. Si basta con las pruebas automáticas, dilo.
1. ...
-->

## Flag

- [ ] No aplica: no agrega comportamiento nuevo visible (fix, refactor, infra, docs)
- [ ] Va detrás del flag `release.<modulo>.<feature>` y entra **apagado** en producción
  - [ ] Probado con el flag apagado (lo actual sigue igual)
  - [ ] Probado con el flag encendido
  - Dueño: @usuario · Expira: AAAA-MM-DD · Ticket para quitarlo: enlace

## Riesgo de despliegue

- [ ] **Migraciones:** no hay / son compatibles con el código que corre hoy (expand). Las que borran (contract) van en un PR aparte, cuando ya nada las usa.
- [ ] **Variables de entorno:** no hay nuevas / ya están en los Environments `test` y `production` de GitHub
- [ ] **Dependencias:** no cambian / cambian y revisé el changelog de las que suben de versión mayor
- [ ] **Pasos manuales:** no hay / están descritos abajo (orden, quién y cuándo)
- [ ] **Vuelta atrás:** se revierte desplegando la imagen anterior / explico abajo por qué no

<!-- Pasos manuales o notas de despliegue: -->

## Versión

<!-- Se decide aquí, no al desplegar. release-MAYOR.MENOR.PARCHE (tres partes). -->

- [ ] Mayor: rompe un contrato con alguien de fuera del repo (API, integración)
- [ ] Menor: funcionalidad nueva (aunque salga apagada detrás de un flag)
- [ ] Parche: corrección, refactor, dependencias, infra

## Antes de pedir revisión

- [ ] El título explica el cambio (se usa en el historial y en las notas del release)
- [ ] `validate / validate` en verde (lint, pruebas y Trivy)
- [ ] Agregué o ajusté pruebas para lo que cambia
- [ ] Sin secretos, llaves ni datos reales de clientes en el código, los commits o las capturas
- [ ] Hice yo mismo una primera revisión del diff
