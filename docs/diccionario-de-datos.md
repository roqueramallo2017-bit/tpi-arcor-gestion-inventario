# Diccionario de datos (resumen de la Entrega 3)

Versión resumida. El detalle completo, con longitudes y valores permitidos, está en
[`entregas/Entrega3_estructura_y_datos.pdf`](entregas/Entrega3_estructura_y_datos.pdf).

| Entidad | Campos principales | Claves |
|---|---|---|
| **Producto** | codigo_sku, nombre, tipo_producto (MATERIA_PRIMA / INSUMO / TERMINADO), unidad_medida, stock_minimo, stock_maximo, activo | PK id_producto |
| **Depósito** | nombre, ubicacion, tipo_deposito, requiere_frio, activo | PK id_deposito |
| **Proveedor** | razon_social, cuit, email_contacto, plazo_entrega_dias, activo | PK id_proveedor |
| **Lote** | numero_lote, fecha_ingreso, fecha_vencimiento, cantidad_actual, estado_calidad (APROBADO / OBSERVADO / RECHAZADO) | PK id_lote · FK id_producto, id_deposito, id_proveedor |
| **Movimiento de Inventario** | tipo_movimiento (ENTRADA / SALIDA / TRANSFERENCIA / AJUSTE), cantidad, fecha_hora, area_origen, usuario_responsable, observacion | PK id_movimiento · FK id_lote, id_deposito_origen, id_deposito_destino |

**Relaciones:** un Producto tiene muchos Lotes; cada Lote está en un Depósito y puede venir de un Proveedor;
cada Lote tiene muchos Movimientos. El stock total de un producto es la suma de `cantidad_actual` de sus lotes APROBADO.

**Cómo lo usa el BPMN:** la compuerta *¿Stock por debajo del mínimo?* compara esa suma con `Producto.stock_minimo`;
la tarea *Registrar lote OBSERVADO* crea un Lote y un Movimiento de ENTRADA; la inspección de calidad cambia
`Lote.estado_calidad`.
