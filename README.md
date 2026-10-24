# CampusLoop

Marketplace universitario para estudiantes de Lima. Proyecto del curso IHC y Programación Web.

## Alcance actual

Están implementados la **Landing pública V2** y el **Inicio de sesión V2**, en Desktop y Mobile. El diseño vigente es:

- [Landing Desktop · 278:2735](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2735): 1440 × 1640 px.
- [Landing Mobile · 278:2816](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2816): 390 × 2714 px.
- [Login Desktop · 278:2880](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2880): 1440 × 890 px.
- [Login Mobile · 278:2921](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2921): 390 × 746 px.
- [Guía visual V2 · 14:33](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=14-33).
- [Biblioteca V2](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2733).

Las otras nueve pantallas principales, sus estados y flujos permanecen en Figma; todavía no tienen páginas HTML. Sus imágenes e íconos están preparados en assets: no se han descartado por no aparecer en las páginas actuales.

## Tecnologías y límites del curso

HTML5 semántico y CSS puro, sin compilación ni dependencias de ejecución. Se usan flujo normal, Box Model, inline-block, vertical-align, márgenes, padding, bordes y media queries. No se utilizan JavaScript, Flexbox, Grid ni frameworks.

El menú Mobile de la Landing utiliza anclas y la pseudoclase CSS :target. Los enlaces internos recorren secciones existentes; Inicio de sesión lleva a login.html. Las acciones hacia pantallas aún no implementadas conservan el aspecto del diseño, están marcadas con aria-disabled y no apuntan a archivos inexistentes. No se simulan autenticación, mensajes, pagos ni reservas.

## Organización

```text
CampusLoop/
├── .gitignore
├── README.md
├── index.html
├── login.html
├── css/
│   └── styles.css
└── assets/
    ├── manifest.json
    ├── fonts/
    │   ├── inter-variable.woff2
    │   └── license.txt
    ├── icons/                    # SVG nativos y tamaños usados por V2
    └── images/
        ├── estudiantes-campus.jpg
        ├── estudiantes-biblioteca.jpg
        ├── avatares/             # Carlos, María y Ana
        ├── fondos/               # Fondo de autenticación utilizado en V2
        └── productos/            # Fotografías y vistas de galería
```

assets/manifest.json es el catálogo técnico vigente: relaciona cada recurso con sus capas, componentes y pantallas V2, dimensiones y hashes. No contiene enlaces temporales de descarga. Las 17 imágenes originales se verificaron contra los hashes de los rellenos de Figma. Los 26 SVG corresponden a componentes y variantes de tamaño/color; las instancias equivalentes comparten archivo. Algunos íconos solo existen en la biblioteca compartida y se identifican como shared-library.

Inter se sirve localmente. Su licencia SIL Open Font License se conserva en assets/fonts/license.txt. Los pesos inspeccionados son 400, 500, 600 y 700. No se sustituyen fotografías por capturas completas del mockup.

## Abrir con Live Server

1. Abrir esta carpeta en Visual Studio Code.
2. Habilitar la extensión Live Server de Ritwick Dey.
3. Hacer clic derecho en index.html y seleccionar **Open with Live Server**. Usar **Iniciar sesión** para abrir login.html, o abrir ese archivo directamente con la extensión.
4. Revisar a 1440 y 390 px de ancho, con zoom del navegador al 100 %.

No hace falta npm install ni un proceso de compilación. También puede abrirse index.html directamente: todas las rutas son relativas y locales. La recarga de Live Server puede inyectar un script de la extensión; ese script no forma parte del proyecto.

## Cómo está construida la Landing

- header y nav organizan identidad, navegación y acceso. main contiene cinco section y footer agrupa enlaces informativos.
- Las categorías y la ficha de Carlos son article; los pasos se expresan con ol.
- box-sizing: border-box incluye padding y borde en las medidas.
- inline-block y vertical-align distribuyen las columnas. font-size: 0 elimina espacios entre estos bloques; cada texto recupera su tamaño.
- Las media queries apilan el hero, categorías, pasos y confianza en Mobile.
- Las fotografías usan object-fit: cover, como los rellenos FILL de Figma; los SVG conservan sus dimensiones exportadas.
- Los colores de V2 están centralizados en las variables CSS de :root. Los fondos de la Landing son planos; no se conservan los degradados ni las fotografías de categorías de la versión anterior.
- El posicionamiento se limita a accesibilidad y al menú desplegable; las secciones permanecen en el flujo normal.

## Cómo está construido el Login

- main contiene el panel de presentación y la tarjeta de autenticación, sin el encabezado ni la navegación pública de la Landing.
- Las columnas Desktop usan inline-block y vertical-align: top. En Mobile se muestra una sola tarjeta y la fotografía pasa a su interior.
- Las clases auth- aíslan los estilos del Login. Se reutilizan Inter, las variables de color, brand y button, junto con la fotografía de la biblioteca, el fondo de ondas y el SVG de CampusLoop existentes.
- form organiza los controles con label, type="email", type="password" y autocomplete. Los espacios se definen con márgenes y padding; border-box incluye el borde en el ancho de los campos.
- Ingresar es un botón type="button" sin acción. El formulario declara method="post", no contiene controles con name ni botones de envío. No se transmiten credenciales al pulsar el botón o Enter.
- Recuperar contraseña y Crear cuenta son opciones pendientes, identificadas mediante title y una descripción accesible. No enlazan a páginas inexistentes. Recordarme solo cambia la casilla; no guarda preferencias ni crea sesiones.

## Comprobaciones realizadas

Revisión del 23/10/2026:

- Live Server y Chrome, con ejecución de scripts de página deshabilitada.
- Recursos locales cargados, Inter disponible, anclas internas y menú Mobile con :target comprobados.
- Sin desplazamiento horizontal a 1440, 1280, 1024, 768, 390 y 320 px.
- Secciones principales y encuadres comparados con las Landing V2.
- Sin referencias a archivos retirados, dependencias de frameworks ni código JavaScript en HTML.
- Capturas y métricas de validación archivadas fuera del repositorio.
- Login probado a 1440 × 890 y 390 × 746 px y en anchos intermedios: sin desplazamiento horizontal, con campos etiquetados y foco visible, sin peticiones de autenticación al pulsar Ingresar o Enter.
- Navegación Landing → Login → Landing comprobada en Desktop y Mobile. Las capturas de la Landing antes y después de actualizar sus enlaces coinciden píxel por píxel.

Las diferencias de suavizado de texto entre Figma y el navegador pueden producir pequeñas variaciones de píxeles. Las acciones de las demás pantallas siguen pendientes de implementación.

## Evidencias y material académico

Ubicación externa:

```text
D:\Ciclo 5\IHC y Programacion WEB\CampusLoop\
├── Evidencias_Figma_V2/
│   ├── Desktop/
│   ├── Mobile/
│   ├── Estados_y_Flujos/
│   ├── Documentacion/
│   └── Inventario_Recursos/
└── Respaldo_Tecnico/
    └── Antes_limpieza_2026-10-23/
```

La documentación de auditoría, inventario de los 169 frames, resultados y capturas se conserva allí. El plan de diseño anterior y los recursos conceptuales descartados se archivaron en el respaldo técnico. No son instrucciones vigentes.

La rama de trabajo de esta implementación es feature/login. No se han realizado commits ni pushes de esta revisión.
