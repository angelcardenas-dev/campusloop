# PLAN DESIGN 01 — CampusLoop

> **Rol del agente:** Actúa como desarrollador frontend y asistente de aprendizaje para el curso **IHC y Programación Web**. Tu objetivo es transformar los mockups originales de CampusLoop en páginas HTML5 semánticas y CSS puro. **El diseño de Figma es la fuente de verdad.** Antes de implementar, confirma los datos con Figma MCP. No inventes componentes, imágenes ni comportamientos que no existan en el diseño sin pedir aprobación.

## 1. Objetivo

Desarrollar el frontend estático del marketplace universitario **CampusLoop**, una iniciativa de **ReCampus**, tomando como referencia su sistema de diseño y sus mockups en Figma.

CampusLoop conecta a estudiantes universitarios de Lima que desean **comprar y vender artículos de segunda mano** en una comunidad orientada a la confianza. Debe facilitar descubrir productos, consultar sus detalles y acceder a los flujos de registro e inicio de sesión. Las categorías representadas en el diseño son **Académico, Tecnológico y Entretenimiento**.

**Alcance de esta etapa (Semana 9):** construir la Landing Page y cinco pantallas del flujo seleccionado, preservando la estructura y la apariencia visual de Figma con **HTML5 semántico y CSS Box Model**, sin implementar todavía un backend ni funcionalidades dinámicas.

## 2. Usuarios

- **Visitantes:** estudiantes universitarios que conocen CampusLoop por primera vez; necesitan entender la propuesta de valor, explorar categorías y encontrar las opciones de registro e inicio de sesión.
- **Compradores:** estudiantes que buscan artículos usados, desean comparar opciones y consultar información de productos y vendedores.
- **Vendedores:** estudiantes que publican artículos, coordinan con compradores y construyen una reputación; este rol forma parte del negocio, aunque no todas sus pantallas se implementarán en la primera entrega.

El lenguaje debe ser claro, juvenil y profesional, con énfasis en **confianza, sencillez y accesibilidad**. No afirmar que existe un sistema de pagos integrado: la coordinación y el pago se acuerdan externamente entre las partes.

## 3. Formato del archivo y entregables

Crear un proyecto web estático que funcione localmente al abrirse con **Live Server** de Visual Studio Code. Utilizar únicamente archivos `.html`, `.css` y recursos gráficos locales descargados del diseño.

Estructura inicial propuesta:

```text
CampusLoop/
├── plan_design_01_prompt.md
├── index.html                # Landing Page pública
├── login.html                # Inicio de sesión
├── registro.html             # Registro
├── inicio.html               # Inicio autenticado (representación estática)
├── explorar.html             # Exploración de artículos
├── detalle.html              # Detalle de artículo
├── css/
│   └── styles.css
├── assets/
│   ├── images/
│   └── icons/
└── README.md
```

- Usar **rutas relativas** para que los enlaces funcionen en Live Server.
- Mantener nombres de archivos y clases claros, consistentes y en minúsculas.
- Evitar archivos o dependencias que no solicite la actividad.
- No usar React, Next.js, Tailwind, Bootstrap, bibliotecas de componentes ni generadores de páginas.
- No utilizar JavaScript en esta etapa. Los enlaces entre páginas pueden funcionar; formularios y acciones que requieran servidor deben quedar claramente como demostración estática.

## 4. Estilo visual — Colores, tipografía y tamaños

**Fuente de verdad:** consultar la página **`00 · Guía de estilos CampusLoop`** y el frame correspondiente mediante Figma MCP. Los siguientes valores provienen del análisis confirmado de la Landing Page y sirven como punto de partida; prevalece el valor real del elemento cuando exista una diferencia.

### Colores

| Token / uso | Valor |
|---|---|
| Azul principal | `#2640A9` |
| Azul de acento | `#5B6FD8` |
| Azul claro del degradado | `#8EA0FF` |
| Fondo general | `#F7F9FF` |
| Tarjetas y cabecera | `#FFFFFF` |
| Texto principal | `#111827` |
| Texto secundario | `#6B7280` |
| Texto sobre degradado | `#EEF2FF` |
| Etiqueta del hero | `#DDE5FF` |
| Línea inferior de cabecera | `#D9E0F2` |

**Degradado del hero y del panel de confianza:** `#2640A9` → `#5B6FD8` (al 55 %) → `#8EA0FF`, horizontal.

### Tipografía

- Familia: **Inter**, con pesos 400, 500, 600 y 700; usar una carga legal/permitida de la fuente o `Arial, sans-serif` de respaldo.
- Logo: **24 px / 700**.
- Navegación: **13 px / 500**.
- Título principal: **44 px / 700**.
- Descripción del hero: **17 px / 400**.
- Títulos de sección: **30 px / 700**.
- Título del bloque de confianza: **28 px / 700**.
- Nombre de categoría: **20 px / 600**.
- Título de paso: **16 px / 600**.
- Texto de botones: **14 px / 600**.
- Distintivos: **12 px / 600**.
- Textos secundarios: **13–15 px / 400**.

### Medidas confirmadas de la Landing Page Desktop

- Frame: **1440 × 1820 px**.
- Contenido central: **1280 px**, con márgenes laterales de **80 px** en ese tamaño de referencia.
- Cabecera: **80 px** de alto.
- Hero: **1280 × 470 px**, 40 px debajo de la cabecera y radio de 18 px.
- Imagen del hero: **445 × 380 px**, radio de 20 px.
- Fotografías de categorías: **390 × 170 px**, separadas entre sí por **30 px**, radio de 16 px.
- Círculos de los pasos: **42 × 42 px**, 16 px de separación respecto al texto.
- Panel de confianza: **1280 × 270 px**, radio de 18 px.
- Tarjeta de perfil: **440 × 180 px**, radio de 16 px, avatar de **72 × 72 px**.
- Botones: radio de **8 px**, alturas aproximadas de **42–50 px**, según el elemento real.
- Distintivos: altura de **30 px**, radio de **15 px**.
- Sombra de imagen principal/tarjeta: `0 8px 24px rgba(28, 41, 77, 0.12)`.

**Observación:** Algunos cuadros de texto en Figma reportan 20 px de alto aunque tienen varias líneas; en HTML usar altura automática, sin recortar contenido.

## 5. Guía visual — Elementos y componentes

Usar los elementos definidos en la guía visual de CampusLoop; consultar sus estados y medidas reales antes de programarlos:

1. **Identidad:** logo textual «CampusLoop», fuente Inter y paleta de marca.
2. **Cabecera y navegación:** logo, menú, enlaces «Iniciar sesión» y «Registrarse».
3. **Hero:** título, descripción, dos acciones, tres distintivos y fotografía principal.
4. **Tarjetas de categorías:** Académico, Tecnológico y Entretenimiento, cada una con fotografía, nombre y descripción.
5. **Cómo funciona:** cuatro pasos «Regístrate → Explora o publica → Coordina → Califica», con indicadores circulares.
6. **Confianza y reputación:** panel con degradado, distintivos y tarjeta del vendedor Carlos Pérez; estrellas y valoración con una descripción textual accesible.
7. **CTA y footer:** bloque «Únete a CampusLoop», enlace «Crear cuenta» y enlaces de ayuda, contacto, términos y privacidad.
8. **Sistema de componentes:** botones primarios/secundarios, campos de formulario con `<label>`, tarjetas, chips, avisos, navegación y variantes visuales de estado cuando estén presentes en los mockups (normal, foco, error, deshabilitado, etc.).
9. **Recursos:** conservar **las cinco fotografías originales** identificadas (hero, tres categorías y avatar) y el SVG de los pasos mediante las herramientas autorizadas de Figma. No reemplazarlas por imágenes ficticias ni generadas con IA.

### Reglas de accesibilidad y semántica

- Un único `<main>` y un único `<h1>` por documento; respetar la jerarquía de encabezados.
- Usar `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` cuando corresponda, y `<footer>`.
- Emplear `<a>` para navegación y `<button>` para acciones dentro de una página.
- Usar `<label for="...">` con `id` coincidente en cada campo; elegir tipos de input correctos.
- Incorporar `alt` útil a imágenes informativas; marcar los símbolos puramente decorativos como tales cuando corresponda.
- Mantener contraste suficiente y estados visibles de error y foco.

## 6. Pantallas que necesito

Implementar **una Landing Page más cinco pantallas** a partir de los frames de Figma:

| Orden | Archivo HTML | Frame de Figma | Objetivo |
|---|---|---|---|
| 0 | `index.html` | `01 · Landing pública` | Presentar CampusLoop, categorías, funcionamiento, confianza y CTA. |
| 1 | `login.html` | `02 · Inicio de sesión` | Entrada de usuario, recuperación y navegación a registro. |
| 2 | `registro.html` | `03 · Registro` | Formulario de alta basado en el mockup. |
| 3 | `inicio.html` | `04 · Inicio autenticado` | Inicio de la aplicación representado de forma estática. |
| 4 | `explorar.html` | `05 · Explorar artículos` | Buscar y recorrer productos con sus categorías/filtros visuales. |
| 5 | `detalle.html` | `06 · Detalle de artículo` | Información de un producto, vendedor y acciones visibles. |

**Nota de alcance:** Esta selección de cinco pantallas prioriza un flujo inicial de comprador; si el docente o el equipo requieren un conjunto distinto, confirma el cambio **antes de generar código**. Las vistas de error, «Nueva publicación», «Activar vendedor», «Mensajes» y «Mi cuenta» permanecen en Figma y podrán abordarse en una etapa posterior si no reemplazan alguna de las cinco elegidas.

## 7. Restricciones técnicas de Semana 9

- **Solo HTML5 semántico + CSS Box Model.**
- **Prohibido por ahora:** `display: flex`, `display: grid`, frameworks CSS y JavaScript.
- Se permite el flujo normal del documento, `display: inline-block`, `vertical-align`, `margin`, `padding`, `border`, `box-sizing`, `max-width` y posicionamiento limitado cuando el diseño lo requiera.
- Evitar maquetar toda la página mediante `position: absolute`; preferir contenido que se ajuste a su altura.
- Se pueden usar `@media` queries con bloques para adaptaciones mínimas, sin inventar una versión móvil de la Landing si no hay un mockup aprobado.
- Mantener el diseño lo más fiel posible a Figma sin sacrificar la semántica ni la legibilidad.
- No simular autenticación real, pagos integrados, reservas efectivas ni almacenamiento que no están implementados.

## 8. Instrucciones de trabajo para el agente

**Antes de escribir código:**

1. Utiliza Figma MCP para comprobar el acceso al archivo CampusLoop y sus frames; identifica el frame por **nombre y node ID**, no solo por la captura general del archivo.
2. Consulta `get_metadata`, `get_design_context`, `get_screenshot` y los recursos/variables pertinentes. Para la Landing ya está confirmado **`01 · Landing pública`, node ID `15:2`**, archivo `b14UnSTg43slwvD1fV0XCG`.
3. Compara cada sección con el mockup; informa qué recursos faltan y si hay incertidumbre sobre el destino de un enlace.
4. Presenta un plan corto de archivos, componentes y etapas; espera mi autorización antes de modificar archivos.

**Después de mi aprobación:**

1. Implementa **primero** `index.html` y `css/styles.css`; deja las otras páginas para entregas posteriores.
2. Descarga los recursos originales autorizados desde Figma y utiliza rutas relativas.
3. Explica brevemente qué etiqueta semántica y qué propiedad del Box Model aplicaste en cada sección, porque estoy aprendiendo el tema.
4. Comprueba la página con Live Server y compárala visualmente con la captura original del frame.
5. Valida que no exista Flexbox, Grid, JavaScript ni dependencias externas de frameworks.
6. No hagas `git commit`, `git push`, crees repositorios remotos o cambies ramas sin consultarme primero.

## 9. Criterios de aceptación

- Las secciones y textos principales coinciden con el diseño correspondiente de Figma.
- El HTML utiliza etiquetas semánticas apropiadas y formularios con etiquetas vinculadas.
- El CSS respeta paleta, tipografía, tamaños, radios, sombras y espaciados observados.
- Los recursos gráficos provienen del diseño original o se deja constancia explícita de los faltantes.
- Los enlaces internos y entre páginas existentes tienen destinos coherentes; no inventar secciones sin revisar el mockup.
- El proyecto abre con Live Server en VS Code sin errores evidentes.
- Se ha respetado estrictamente el alcance técnico de la Semana 9.

---

**Enlace general a Figma:** https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop

**Frame de referencia confirmado para comenzar:** https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=15-2
