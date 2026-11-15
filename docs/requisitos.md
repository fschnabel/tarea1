# Fase A - Revisión de requisitos

## 1. Requisitos

- RF-01: El descuento se calculará en un máximo de 200 ms por solicitud, bajo condiciones de ejecución definidas.
- RF-02: Se definirán los clientes VIP y recibirán un descuento adicional de $10.
- RF-03: El descuento se limitará al precio, salvo promociones autorizadas con reglas explícitas.
- RF-04: El precio final se mostrará con dos decimales y una política de redondeo definida.


## 2. Historial de observaciones

## 2.1. Requisitos originales

- R-01: El descuento debe calcularse rápidamente.
- R-02: Los clientes importantes obtendrán un descuento especial.
- R-03: El descuento no puede superar el precio, excepto en promociones.
- R-04: Se debe mostrar el resultado correcto.

## 2.2. Identificación de problemas

| ID | Problema | Impacto | Propuesta | Artefacto | Estado |
|---|---|---|---|---|---|
| R-01 | Claridad, completitud y verificabilidad: el término "rápidamente" no define un tiempo medible ni condiciones de ejecución. | Rendimiento subjetivo; imposibilidad de comprobar objetivamente el cumplimiento. | RF-01: establecer un tiempo máximo de 200 ms por solicitud, bajo condiciones definidas. | docs/requisitos.md | Pendiente de validación |
| R-02 | Claridad, completitud y verificabilidad: no se define qué es un "cliente importante" ni el descuento especial. | Aplicación incorrecta de beneficios y posibles diferencias en el cálculo. | RF-02: definir clientes VIP y aplicar un descuento adicional de $10. | docs/requisitos.md | Pendiente de validación |
| R-03 | Claridad, consistencia por confirmar, completitud y verificabilidad: no se especifican las promociones excepcionales ni sus límites. | Descuentos superiores al precio, totales negativos y posibles pérdidas económicas. | RF-03: limitar el descuento al precio, salvo promociones autorizadas con reglas explícitas. | docs/requisitos.md y src/descuentos.js | Pendiente de reglas de negocio |
| R-04 | Claridad, completitud y verificabilidad: "resultado correcto" no define precisión, formato ni redondeo. | Resultados monetarios inconsistentes y dificultad para comprobar los cálculos. | RF-04: mostrar el precio final con dos decimales y una política de redondeo definida. | docs/requisitos.md y src/descuentos.js | Pendiente de validación |
