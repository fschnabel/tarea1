# Inspección por pares

## Roles

Los participantes se identifican por su función, ya que no se proporcionaron
nombres:

- **Autor:** implementa el módulo de cálculo de descuentos.
- **Revisor:** contrasta el código con las reglas de ESLint y los requisitos
  documentados.
- **Registrador:** mantiene el registro de hallazgos, acciones, estados y
  evidencias.

## Hallazgos de ESLint

| ID | Severidad | Evidencia | Acción | Estado |
|---|---|---|---|---|
| ESL-01 | Baja | Evidencia inicial en `lint-inicial.txt`: `src/descuentos.js`, línea 2, columna 3; `var descuento`. Regla `no-var`. | Sustituido por `let`, ya que el valor se reasigna para clientes VIP. | Corregido; lint final sin errores. |
| ESL-02 | Baja | Evidencia inicial en `lint-inicial.txt`: `src/descuentos.js`, línea 3, columna 13; `esVip == true`. Regla `eqeqeq`. | Cambiado a comparación estricta `esVip === true`. | Corregido; lint final sin errores. |
| ESL-03 | Baja | Evidencia inicial en `lint-inicial.txt`: `src/descuentos.js`, línea 3, columna 22; condicional sin llaves. Regla `curly`. | Añadidas llaves al bloque `if`. | Corregido; lint final sin errores. |
| ESL-04 | Baja | Evidencia inicial en `lint-inicial.txt`: `src/descuentos.js`, línea 4, columna 25; condicional sin llaves. Regla `curly`. | Añadidas llaves al bloque `if`. | Corregido; lint final sin errores. |
| ESL-05 | Baja | Evidencia inicial en `lint-inicial.txt`: `src/descuentos.js`, línea 5, columna 3; `var total`. Regla `no-var`. | Sustituido por `const`, porque el total no se reasigna. | Corregido; lint final sin errores. |

`no-unused-vars` está habilitada y no produjo hallazgos en el módulo revisado.

## Hallazgos de revisión humana

| ID | Severidad | Evidencia | Acción | Estado |
|---|---|---|---|---|
| HUM-01 | Alta | `src/descuentos.js`: cuando `porcentaje > 100` solo se imprime un mensaje y el cálculo continúa; además, el descuento VIP puede hacer que el descuento total supere el precio. | Definir y aplicar las reglas de límite y las excepciones de promociones. La observación R-03 indica que las reglas de promociones siguen pendientes. | Pendiente de reglas de negocio; no se modificó la lógica. |
| HUM-02 | Media | `calcularDescuento` calcula sin validar rangos ni tipos de `precio`, `porcentaje` o `esVip`. | Acordar valores de entrada válidos y comportamiento ante entradas inválidas antes de agregar validaciones. | Pendiente de especificación; no se modificó la lógica. |
| HUM-03 | Baja | La función devuelve un valor numérico y no define formato ni redondeo monetario; RF-04 deja pendiente la política de redondeo. | Definir política y capa responsable de mostrar el precio con dos decimales. | Pendiente de validación del requisito; no se modificó la lógica. |

## Resultado

Los cinco errores informados por ESLint se corrigieron. Los hallazgos humanos se
registraron por separado y permanecen pendientes cuando requieren decisiones de
negocio o precisión adicional de los requisitos. La evidencia de la ejecución
final está en [lint-final.txt](./lint-final.txt); la ejecución inicial se
conserva en [lint-inicial.txt](./lint-inicial.txt).
