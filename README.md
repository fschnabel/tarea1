# Tarea 1: análisis y revisión de descuentos

Proyecto de revisión de requisitos y análisis estático de un módulo JavaScript
que calcula descuentos.

## Estructura

- `src/descuentos.js`: función de cálculo `calcularDescuento(precio, porcentaje, esVip)`.
- `docs/requisitos.md`: requisitos actuales, requisitos originales e historial de observaciones.
- `docs/checklist.md`: checklist de revisión estática.
- `evidencias/lint-inicial.txt`: resultado de ESLint antes de las correcciones.
- `evidencias/lint-final.txt`: resultado de ESLint después de las correcciones.
- `evidencias/revision-por-pares.md`: registro de roles y hallazgos de ESLint y revisión humana.
- `eslint.config.mjs`: configuración de ESLint.
- `package.json` y `package-lock.json`: scripts y dependencias del proyecto.

## Requisitos previos

- Node.js y npm.

## Instalación y verificación

Desde la raíz del repositorio:

```bash
npm install
npm run lint
```

El script `lint` ejecuta ESLint sobre el proyecto. La evidencia final registra
una ejecución exitosa sin errores ni advertencias. El repositorio no tiene
pruebas automatizadas configuradas actualmente.

## Historial de commits

Los siguientes commits forman parte del historial publicado del repositorio:

| Commit | Descripción |
|---|---|
| [`b388f07`](https://github.com/fschnabel/tarea1/commit/b388f07) | Se suben los archivos iniciales antes de la aplicación de la tarea 1. |
| [`3311007`](https://github.com/fschnabel/tarea1/commit/3311007) | Se agregan los requisitos originales. |
| [`26694ae`](https://github.com/fschnabel/tarea1/commit/26694ae) | Se analizan los requisitos y se documentan problemas y propuestas de corrección. |
| [`51e6982`](https://github.com/fschnabel/tarea1/commit/51e6982) | Se ejecuta ESLint y se evidencia el estado inicial del código. |
| [`f69b606`](https://github.com/fschnabel/tarea1/commit/f69b606) | Se aplican correcciones de ESLint y se comparan los hallazgos de herramienta y revisión humana. |

## Pull requests y acta de revisión

Las tres pull requests del flujo están fusionadas en `main`:

| Pull request | Propósito | Comentario/resultado registrado |
|---|---|---|
| [#1 Revisión de requisitos](https://github.com/fschnabel/tarea1/pull/1) | Análisis de requisitos y documentación de propuestas. | Se da conformidad a las propuestas para continuar el desarrollo. |
| [#2 Evidencia inicial de ESLint](https://github.com/fschnabel/tarea1/pull/2) | Registrar los errores encontrados en la revisión inicial de ESLint. | Se acepta la observación para proseguir con las correcciones. |
| [#3 Correcciones y revisión](https://github.com/fschnabel/tarea1/pull/3) | Corregir los errores de ESLint y contrastarlos con la revisión humana. | Se confirma que ESLint quedó corregido y que las observaciones humanas quedan pendientes de validación. |

Como acta equivalente de los comentarios técnicos de revisión:

1. **ESLint:** se encontraron y corrigieron usos de `var`, comparación no
   estricta y condicionales sin llaves. La evidencia final de `npm run lint`
   no reporta errores.
2. **Revisión humana:** se registraron pendientes sobre límites de descuento y
   promociones, validación de entradas y redondeo monetario. No se modificó esa
   lógica porque requiere aclarar reglas de negocio.

El detalle de hallazgos, severidad, evidencia, acción y estado está en
[`evidencias/revision-por-pares.md`](evidencias/revision-por-pares.md). El
comentario de cierre de la revisión está disponible en
[la conversación de la pull request #3](https://github.com/fschnabel/tarea1/pull/3#issuecomment-6899236337).
