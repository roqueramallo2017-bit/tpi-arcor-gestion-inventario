# Indicadores de control y estándares de desempeño

El control sigue las cuatro etapas vistas en la Unidad 5: **establecer estándares → medir → comparar → corregir**.
Los indicadores técnicos salen de las metas de la Entrega 2; los de proceso salen del BPMN y se pueden
calcular con los datos que ya define el diccionario de datos de la Entrega 3.

## Indicadores técnicos (auditoría del sistema)

| # | Indicador | Cómo se calcula | Estándar | Frecuencia | Responsable |
|---|---|---|---|---|---|
| IT-1 | Tiempo de respuesta de consultas | Percentil 95 del tiempo de las consultas de stock y movimientos | ≤ 3 s | Semanal | Infraestructura y Soporte |
| IT-2 | Disponibilidad del sistema | (Horas operativas − horas caído sin aviso) / horas operativas × 100 | ≥ 99 % | Mensual | Infraestructura y Soporte |
| IT-3 | Capacidad | Prueba de carga con 100.000 registros, verificando que IT-1 se siga cumpliendo | 100.000 registros sin superar 3 s | Antes de implementar y luego cada semestre | Administración de Datos |
| IT-4 | Cumplimiento del cronograma | Avance real / avance planificado en el Gantt | ≥ 0,9 y desvío ≤ 1 semana | Semanal (durante el proyecto) | PMO |
| IT-5 | Trazabilidad de movimientos | Movimientos con lote válido y `usuario_responsable` / total de movimientos × 100 | 100 % | Mensual | Auditoría Interna |

## Indicadores del proceso (BPMN)

| # | Indicador | Cómo se calcula | Estándar | Frecuencia | Responsable |
|---|---|---|---|---|---|
| IP-1 | Exactitud del inventario | Lotes cuyo stock en sistema coincide con el conteo físico / lotes contados × 100 | ≥ 98 % | Mensual (conteo cíclico) | Depósito |
| IP-2 | Quiebres de stock | Órdenes de producción reprogramadas por falta de materia prima en el mes | 0 (máx. 1 por mes) | Mensual | Producción |
| IP-3 | Alertas atendidas a tiempo | Órdenes de compra emitidas dentro de las 24 h de la alerta / alertas generadas × 100 | ≥ 95 % | Semanal | Compras y Abastecimiento |
| IP-4 | Tiempo de liberación de lotes | Horas entre el movimiento de ENTRADA y el cambio a APROBADO o RECHAZADO | ≤ 48 h | Semanal | Control de Calidad |
| IP-5 | Tasa de rechazo por proveedor | Lotes RECHAZADO / lotes recibidos del proveedor × 100 | ≤ 2 % | Trimestral | Compras + Calidad |

## Qué hacer cuando un indicador no cumple (acción correctiva)

- **IT-1 / IT-3:** revisar índices de la base de datos y las consultas más lentas; si no alcanza, ampliar recursos.
- **IP-1:** revisar los movimientos de AJUSTE del período y capacitar al personal de depósito en la carga.
- **IP-3:** revisar si las alertas llegan a la persona correcta y ajustar el `stock_minimo` según el plazo del proveedor.
- **IP-5:** reunión con el proveedor; si se repite, buscar un proveedor alternativo.

Los resultados los prepara el sector **Reportes e Indicadores** (organigrama de la Entrega 3) y se presentan
a la Gerencia de Sistemas y a las gerencias usuarias.
