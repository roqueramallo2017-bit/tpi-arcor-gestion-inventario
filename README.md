# Mejora del Módulo de Gestión de Inventario – Grupo Arcor

**Trabajo Práctico Integrador (TPI)**, Organización Empresarial
Tecnicatura Universitaria en Programación a Distancia, Universidad Tecnológica Nacional (UTN)

| | |
|---|---|
| **Integrante** | Roque Ramallo Carmona |
| **Docente titular** | Prof. Carolina Bruno |
| **Docente tutora** | Prof. Laureana Gangge |
| **Tablero del proyecto** | [GitHub Projects – Backlog TPI Arcor](https://github.com/users/roqueramallo2017-bit/projects/1) |

---

## Descripción del sistema

Grupo Arcor trabaja con miles de materias primas, insumos y productos terminados repartidos en distintos depósitos.
Hoy, si la información de stock no está actualizada, Producción se puede quedar sin insumos, Compras se entera tarde
y Calidad no puede seguir con facilidad qué lote salió y cuándo.

El proyecto propone mejorar el **módulo de Gestión de Inventario** para:

- **centralizar** el stock de materias primas, insumos y productos terminados, por lote y por depósito;
- registrar cada **movimiento** (entrada, salida, transferencia y ajuste) con su responsable;
- generar **alertas automáticas** de reposición cuando un producto queda por debajo del stock mínimo;
- asegurar la **trazabilidad por lote**: solo se usan los lotes que Control de Calidad aprobó.

## Contenido del repositorio

| Carpeta / archivo | Qué contiene |
|---|---|
| [`docs/entregas/`](docs/entregas) | Entregas 1, 2 y 3 del TPI (TGS, FODA + Gantt, organigrama + diccionario de datos) |
| [`docs/bpmn/`](docs/bpmn) | Modelo BPMN del proceso de reposición y recepción (`.bpmn` editable + imágenes) |
| [`docs/historias-de-usuario.md`](docs/historias-de-usuario.md) | HU-01, HU-02 y HU-03 con criterios de aceptación |
| [`docs/indicadores-de-control.md`](docs/indicadores-de-control.md) | Indicadores, estándares de desempeño y acciones correctivas |
| [`docs/diccionario-de-datos.md`](docs/diccionario-de-datos.md) | Resumen de las entidades del sistema |

## Forma de trabajo con Git y GitHub

- La rama `main` tiene solo versiones revisadas. Nada se sube directo: todo entra por **Pull Request**.
- Uso una rama por tema: `docs/entregas-anteriores`, `feature/bpmn-proceso-inventario` y `docs/historias-e-indicadores`.
- Los commits siguen el formato `tipo: descripción en presente` (por ejemplo, `docs: agrega historias de usuario HU-01 a HU-03`).
- Cada historia de usuario es un *issue* del tablero, y los PR la cierran con `Closes #n`.

---

## Declaración de Uso de IA

<!-- REVISAR: esta sección tiene que reflejar lo que realmente hiciste. Ajustala con tus palabras antes de subirla. -->

**Herramientas utilizadas:** Claude (Anthropic) en esta entrega; en las Entregas 1 a 3 usé también ChatGPT (OpenAI) para revisar la redacción.

**Para qué la usé:** para ordenar la estructura de la entrega final, generar el borrador del diagrama BPMN a partir de mi
diccionario de datos, redactar borradores de historias de usuario e indicadores, y armar la guía de comandos de Git.
No la usé para elegir el caso ni la mejora propuesta: esas decisiones son de la Entrega 1.

### Prompts utilizados y por qué

| # | Prompt (resumen) | Por qué lo formulé así |
|---|---|---|
| 1 | Le pasé la consigna de la Entrega 4 y la plantilla de la cátedra, y le pedí ayuda para resolverla. | Primero quería que identificara qué piezas exigía la consigna (BPMN, Git, tablero, control) antes de redactar nada. |
| 2 | Le adjunté mis Entregas 1, 2 y 3 y las devoluciones de la tutora para que la entrega final fuera coherente con ellas y corrigiera lo observado. | Para que el BPMN y los indicadores usaran mis propias entidades (Lote, Movimiento, stock_minimo) y mis metas, y no un ejemplo genérico de inventario. |
| 3 | <!-- REVISAR: agregá aquí los pedidos de cambios que hagas sobre los borradores --> | |

### Correcciones humanas sobre lo que generó la IA

<!-- REVISAR: dejá solo lo que efectivamente hiciste y agregá tus propias correcciones. -->
- Comparé cada tarea del BPMN con el diccionario de datos de la Entrega 3 (estados APROBADO/OBSERVADO/RECHAZADO, tipos de movimiento) para que usen los mismos nombres.
- Controlé que los indicadores técnicos coincidan con las metas de la Entrega 2 (3 s, 100.000 registros, 99 %, 12 semanas) y no con valores inventados.
- Las historias de usuario se basan en los requisitos de las entregas anteriores. Revisé que cada una tenga un usuario real del organigrama (Compras, Calidad, Producción).
- Ajusté la redacción a mi forma de escribir y verifiqué que puedo explicar cada compuerta del BPMN en el coloquio.

**Responsabilidad:** revisé todo el contenido y me hago responsable de su veracidad y coherencia conceptual.
