# Historias de Usuario – Módulo de Gestión de Inventario

Las tres historias de usuario salen de las necesidades que identifiqué en las entregas anteriores:
la alerta de stock mínimo para Compras (Entrega 1 y diccionario de datos de la Entrega 3), el estado
de calidad de cada lote (Entrega 3) y la consulta de disponibilidad para Producción (Entrega 1).
Cada una se carga como *issue* en GitHub y se sigue en el tablero de GitHub Projects con los estados
**Por hacer → En progreso → Listo**.

---

## HU-01 · Alerta de reposición por stock mínimo

**Como** responsable de Compras y Abastecimiento,
**quiero** recibir una alerta automática cuando el stock total de una materia prima quede por debajo de su stock mínimo,
**para** emitir la orden de compra a tiempo y evitar que se frene la producción.

**Criterios de aceptación**
- Cuando un movimiento de SALIDA o AJUSTE deja el stock total del producto por debajo de `stock_minimo`, el sistema genera la alerta en el momento.
- La alerta muestra el producto, el stock actual, el stock mínimo y el proveedor habitual con su `plazo_entrega_dias`.
- Solo se suman los lotes en estado APROBADO para calcular el stock disponible.
- Compras puede marcar la alerta como "atendida" cuando emite la orden de compra (queda registrada la fecha y el usuario).

**Relación con el BPMN:** tareas *Verificar stock disponible*, compuerta *¿Stock por debajo del mínimo?*, *Generar alerta de reposición* y *Revisar alerta y seleccionar proveedor*.

---

## HU-02 · Registro del resultado de calidad por lote

**Como** analista de Control de Calidad,
**quiero** registrar el resultado de la inspección de cada lote recibido (APROBADO, OBSERVADO o RECHAZADO),
**para** que solo los lotes aprobados puedan consumirse o despacharse.

**Criterios de aceptación**
- Todo lote nuevo ingresa con estado OBSERVADO y no se puede usar hasta que Calidad lo revise.
- Al pasar a APROBADO, la cantidad del lote se suma al stock disponible.
- Al pasar a RECHAZADO, el sistema solo permite un movimiento de AJUSTE para darlo de baja y avisa a Compras.
- Cada cambio de estado guarda el usuario responsable y la fecha y hora.

**Relación con el BPMN:** *Registrar lote OBSERVADO y movimiento ENTRADA*, *Inspeccionar lote*, compuerta *¿Resultado de la inspección?* y sus dos salidas.

---

## HU-03 · Consulta de disponibilidad para Producción

**Como** supervisor de Producción,
**quiero** consultar la disponibilidad de cada materia prima por lote, depósito y vencimiento,
**para** planificar las órdenes de producción sin quedarme sin insumos a mitad de camino.

**Criterios de aceptación**
- La consulta responde en 3 segundos o menos (Meta 1 de la Entrega 2).
- Muestra stock total y el detalle por lote: depósito, fecha de vencimiento y estado de calidad.
- Ordena los lotes por fecha de vencimiento más próxima, para usar primero los que vencen antes.
- Se puede filtrar por producto y por depósito.

**Relación con el BPMN:** *Solicitar materia prima para la orden* y *Verificar stock disponible*.
