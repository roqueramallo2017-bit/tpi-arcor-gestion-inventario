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

Desarrollé esta entrega con la asistencia de Claude (Anthropic) como herramienta de apoyo. En las Entregas 1 a 3 también usé ChatGPT (OpenAI) para revisar la redacción.

### Cómo trabajé

1. **Analicé la consigna.** Le pedí a la IA que me ayudara a desglosar la consigna de la Entrega 4 y la plantilla de la cátedra, para tener claro qué se evaluaba (BPMN, Git, tablero y control) antes de empezar.
2. **Partí de mi propio proyecto.** Como pide la consigna, la entrega cierra las anteriores, así que la base son las decisiones que fui tomando durante la cursada: el caso Grupo Arcor, la mejora del módulo de Inventario, mis metas, mi organigrama y mi diccionario de datos. Sobre esa base elaboré, con asistencia de la IA, el diagrama BPMN, las historias de usuario y los indicadores de control.
3. **Apliqué las correcciones de la tutora**, también con asistencia de la IA: completé la carátula, corregí las fortalezas del FODA, agregué los cruces FO/DO/FA/DA y precisé la declaración de IA.
4. **Gestioné el proyecto en GitHub.** Creé el repositorio, trabajé con cuatro ramas, hice los commits, abrí e integré los Pull Requests, cargué los issues y organicé el tablero. Usé la IA como guía para los pasos.
5. **Coordiné la revisión de pares.** Le pedí a un compañero que revisara el PR #8 (BPMN) y lo integré después de su revisión.
6. **Revisé y estudié el contenido** para poder explicarlo y defenderlo en el coloquio.

### Prompts utilizados

| # | Prompt (resumen) | Por qué lo formulé así |
|---|---|---|
| 1 | Le pedí que analizara la consigna de la Entrega 4 y la plantilla de la cátedra y me dijera qué exigía cada punto. | Antes de redactar quería tener claro qué se evaluaba (BPMN, Git, tablero, control) para no dejar nada afuera. |
| 2 | Le compartí mis Entregas 1, 2 y 3 y las devoluciones de la tutora, y le indiqué que trabajáramos sobre mis entidades, metas y áreas para resolver las observaciones. | Quería que la Entrega 4 fuera la continuación de mi propio proyecto y no un ejemplo genérico de inventario, y resolver lo observado: la carátula, las fortalezas del FODA, los cruces FO/DO/FA/DA y la declaración de IA. |
| 3 | Le pedí una guía paso a paso para trabajar con GitHub. | Quería aplicar bien el flujo de ramas, Pull Requests y tablero que pide la consigna. |

### Corrección propia

La consigna pedía vincular historias de usuario "previamente definidas", pero en mis entregas anteriores no estaban escritas en formato formal. Las formalicé en esta entrega a partir de los requisitos que ya había planteado.
