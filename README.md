# uiux-design-prototype

Proyecto de prototipado frontend construido **únicamente con HTML y CSS**, pensado para visualizarse y navegarse directamente en el navegador (incluso mediante `file://`, sin servidores ni herramientas de compilación).

La especificación funcional, roles y flujos principales se encuentran en [product-spec.md](./product-spec.md).

## Estructura del proyecto

```text
uiux-design-prototype/
├── index.html                      # Hub / Mapa del proyecto
├── product-spec.md                 # Especificación del producto, roles y flujos
├── README.md
│
├── styles/                         # CSS compartido y modular
│   ├── reset.css                   # Normalización básica y box-sizing
│   ├── tokens.css                  # Variables CSS (:root): colores, fuentes, espaciados, radios
│   ├── layout.css                  # Grids, contenedores, header, sidebar, responsive
│   ├── components.css              # Botones, cards, badges de créditos, formularios
│   └── wireframe.css               # Tema de baja fidelidad (escala de grises y placeholders)
│
├── assets/
│   ├── icons/                      # Iconos SVG ligeros
│   ├── images/                     # Avatares, ilustraciones o imágenes de prueba
│   └── references/                 # Capturas o moodboard de inspiración visual
│
├── 01-design-system/               # Referencias de estilos y librería visual
│   ├── styleguide.html             # Paleta, tipografía, espaciados y tonos
│   └── components-kit.html         # Catálogo de componentes reutilizables
│
├── 02-wireframes/                  # Baja fidelidad (estructura y jerarquía)
│   ├── shared/                     # Login, registro, perfil, billetera de créditos, chat
│   ├── flujo-1-solicitar/          # Flujo 1: Solicitar ayuda (Seeker)
│   ├── flujo-2-ofrecer/            # Flujo 2: Ofrecer mis habilidades (Giver)
│   └── flujo-3-finalizar/          # Flujo 3: Finalizar y valorar intercambio (Ambos)
│
└── 03-prototypes/                  # Media / Alta fidelidad (con tokens y componentes)
    ├── shared/
    ├── flujo-1-solicitar/
    ├── flujo-2-ofrecer/
    └── flujo-3-finalizar/
```

## Convenciones

- **Rutas relativas:** Usar siempre rutas relativas (ej. `../../styles/tokens.css`) en lugar de rutas absolutas (`/styles/...`) para que los archivos funcionen al abrirse directamente con `file://`.
- **Nomenclatura de vistas:** Numeración con dos dígitos en `kebab-case` siguiendo el orden de cada flujo en `product-spec.md` (ej. `01-explorar.html`, `02-buscar.html`, ...).
- **Visor por flujo:** Cada carpeta de flujo en `02-wireframes/` debe incluir su propio `visor.html` que muestre **únicamente** las pantallas de ese flujo, permitiendo avanzar paso a paso (`← Anterior` / `Siguiente →`) en una sola pestaña.
- **Interactividad sin JavaScript:**
  - Navegación entre pasos con enlaces `<a href="...">`.
  - Acordeones y desplegables con `<details>` y `<summary>`.
  - Modales o confirmaciones con el pseudo-selector `:target`.
  - Pestañas o cambio de estado con `input[type="radio"]` + `:checked`.
