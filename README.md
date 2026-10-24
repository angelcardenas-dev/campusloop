# CampusLoop

Marketplace universitario para estudiantes de Lima. Proyecto del curso IHC y Programación Web.

## Alcance actual

Están implementados la **Landing pública V2**, el **Inicio de sesión V2**, el **Registro V2**, el **Inicio autenticado V2** y **Explorar artículos V2**, en Desktop y Mobile. El diseño vigente es:

- [Landing Desktop · 278:2735](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2735): 1440 × 1640 px.
- [Landing Mobile · 278:2816](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2816): 390 × 2714 px.
- [Login Desktop · 278:2880](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2880): 1440 × 890 px.
- [Login Mobile · 278:2921](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2921): 390 × 746 px.
- [Registro Desktop · 278:2946](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2946): 1440 × 1125 px.
- [Registro Mobile · 278:3001](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3001): 390 × 1249 px.
- [Inicio Desktop · 278:3030](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3030): 1440 × 1375 px.
- [Inicio Mobile · 278:3115](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3115): 390 × 844 px, con contenido desplazable.
- [Explorar Desktop · 278:3154](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3154): 1440 × 1286 px.
- [Explorar Mobile · 278:3437](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3437): 390 × 844 px, con contenido desplazable.
- [Guía visual V2 · 14:33](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=14-33).
- [Biblioteca V2](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2733).

Las otras seis pantallas principales, sus estados y flujos permanecen en Figma; todavía no tienen páginas HTML. Sus imágenes e íconos están preparados en assets: no se han descartado por no aparecer en las páginas actuales.

## Tecnologías y límites del curso

HTML5 semántico y CSS puro, sin compilación ni dependencias de ejecución. Se usan flujo normal, Box Model, inline-block, vertical-align, márgenes, padding, bordes y media queries. No se utilizan JavaScript, Flexbox, Grid ni frameworks.

El menú Mobile de la Landing utiliza anclas y la pseudoclase CSS :target. Los enlaces internos recorren secciones existentes; Inicio de sesión lleva a login.html y Registrarse / Crear cuenta llevan a registro.html. Las acciones hacia pantallas aún no implementadas conservan el aspecto del diseño, están marcadas con aria-disabled y no apuntan a archivos inexistentes. No se simulan autenticación, creación de cuentas, mensajes, pagos ni reservas.

## Organización

```text
CampusLoop/
├── .gitignore
├── README.md
├── index.html
├── login.html
├── registro.html
├── inicio.html                   # Comprador sin perfil vendedor activo
├── inicio-vendedor.html          # Variante estática: vendedor activo
├── inicio-nuevo.html             # Variante estática: usuario nuevo
├── explorar.html                 # Catálogo estático de ocho artículos
├── explorar-vacio.html           # Variante estática: sin resultados
├── explorar-error.html           # Variante estática: error de carga
├── explorar-filtros.html         # Panel de filtros Mobile, sin envío
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
3. Hacer clic derecho en index.html y seleccionar **Open with Live Server**. Usar **Iniciar sesión** o **Registrarse** para recorrer las pantallas, o abrir login.html / registro.html directamente con la extensión.
4. Revisar a 1440 y 390 px de ancho, con zoom del navegador al 100 %.

Para revisar Inicio, abrir inicio.html con Live Server. Las variantes se abren directamente desde inicio-vendedor.html e inicio-nuevo.html. No se enlazan desde Ingresar: todavía no existe autenticación real.

Para revisar Explorar, abrir explorar.html o usar los enlaces Explorar de Inicio y el botón Explorar artículos de la Landing. Las variantes vacía y de error se abren directamente desde explorar-vacio.html y explorar-error.html; no son resultados reales de una búsqueda. En Mobile, Filtros abre explorar-filtros.html y Cerrar filtros regresa al catálogo.

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
- Recuperar contraseña sigue pendiente, identificado mediante title y una descripción accesible. Crear cuenta abre registro.html. Recordarme solo cambia la casilla; no guarda preferencias ni crea sesiones.

## Cómo está construido el Registro

- Reutiliza la composición auth- del Login: dos paneles con inline-block en Desktop y una tarjeta con fotografía en Mobile, sin navegación pública ni autenticada.
- form contiene seis campos etiquetados: nombre, universidad, campus, correo, contraseña y confirmación. Usa autocomplete apropiado y relaciona la ayuda de contraseña con su control mediante aria-describedby.
- La universidad y el campus se representan como campos de texto, tal como aparecen en los frames finales; no se agrega un catálogo ni un selector dependiente.
- Solo se añaden estilos auth-hint, auth-terms y auth-info para la ayuda, la aceptación de términos y la información de cuenta de estudiante. Las reglas anteriores de Landing y Login permanecen intactas.
- Crear cuenta es type="button" sin acción; el formulario usa method="post", sin controles name ni botones submit. No envía datos, valida contraseñas, verifica correo ni crea cuentas. La casilla de términos no registra consentimiento.
- Desde Registro se puede volver a index.html o a login.html. Todos los accesos de registro de Landing y Login llevan a registro.html.

## Cómo está construido el Inicio autenticado

Las tres vistas representan estados de ejemplo independientes; no cambian roles ni crean sesiones:

| Archivo | Estado | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [inicio.html](inicio.html) | Comprador sin perfil vendedor; 1 reserva, 3 mensajes y 5 compras | [278:3030](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3030) | [278:3115](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3115) |
| [inicio-vendedor.html](inicio-vendedor.html) | Perfil vendedor activo; 0 publicaciones, 2 mensajes y 5 compras | [290:536](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=290-536) | [291:487](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=291-487) |
| [inicio-nuevo.html](inicio-nuevo.html) | Sin actividad ni entrega; indicadores en cero | [290:654](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=290-654) | [291:619](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=291-619) |

- header y nav organizan los cuatro apartados autenticados: Inicio, Explorar, Publicar y Reservas. Mi cuenta se representa exclusivamente en el avatar.
- main contiene bienvenida, resumen, actividad y recomendaciones. Las tarjetas de producto son article; aside presenta la entrega Confirmada, sin confundirla con una operación Completada. La actividad utiliza una lista y time.
- Las clases home- aíslan los estilos. Se reutilizan Inter, variables, brand, button y panel. Las columnas, indicadores y tarjetas usan inline-block, vertical-align y font-size: 0 para controlar los espacios entre bloques.
- border-box, padding, bordes, márgenes y min-height mantienen las medidas y permiten que los textos crezcan si es necesario. Las imágenes usan object-fit: cover como los rellenos FILL de Figma.
- En Mobile solo se desplaza home-viewport; la cabecera de 72 px y la navegación inferior de 80 px quedan fuera del área desplazable. calc reserva sus alturas. Se conserva el desplazamiento por rueda, gesto y teclado sin superponer la barra al contenido.
- Se reutilizan el avatar de María, cinco fotografías de productos y siete SVG existentes. No se descargaron ni duplicaron recursos.
- Las acciones pendientes no tienen href y se identifican con title, aria-disabled y descripción accesible. La búsqueda es de solo lectura. No se simulan mensajes, reservas, publicaciones, notificaciones ni acceso real a Mi cuenta.
- Los nombres, precios y fechas son datos estáticos del diseño. La entrega del 23/10/2026 se conserva como ejemplo de Figma; no se calcula una próxima entrega real.

## Cómo está construido Explorar

| Archivo | Variante | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [explorar.html](explorar.html) | Catálogo de ocho artículos | [278:3154](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3154) | [278:3437](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3437) |
| [explorar-vacio.html](explorar-vacio.html) | Sin resultados | [296:756](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=296-756) | [297:768](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-768) |
| [explorar-error.html](explorar-error.html) | Error de carga | [296:850](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=296-850) | [297:826](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-826) |
| [explorar-filtros.html](explorar-filtros.html) | Panel de filtros Mobile | No existe variante Desktop independiente | [297:1193](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-1193) |

- Reutiliza la cabecera y navegación home-, las tarjetas home-product, button, panel, auth-field, auth-control y auth-info. Explorar queda activo; Mi cuenta conserva su acceso desde el avatar. Las reglas explore- se añaden al final de styles.css y no alteran las pantallas anteriores.
- main contiene la presentación y una sección de resultados con ocho article. aside agrupa los filtros Desktop en un form con fieldset y legend. Cada control tiene label o nombre accesible.
- inline-block y vertical-align colocan el filtro de 240 px junto a los resultados, con cuatro tarjetas por fila en Desktop y dos en Mobile. border-box, calc, padding, márgenes y min-height reproducen las medidas del diseño. No se usan Flexbox ni Grid.
- Se reutilizan ocho fotografías de productos, el avatar de María, siete SVG e Inter locales. Los precios, vendedores, campus y estados Disponible, Reservado y Vendido reproducen los datos de Figma. No se descargaron recursos nuevos.
- En Mobile, la cabecera y la barra inferior permanecen en el flujo normal, fuera de home-viewport. El área central se desplaza y deja accesibles las últimas tarjetas y sus botones.
- Los filtros ofrecen casillas, selectores y precios numéricos nativos. Limpiar filtros solo restablece los controles locales; no cambia el estado vacío ni el catálogo. Aplicar filtros es type="button" sin acción, con aria-disabled. El formulario no tiene controles name ni botones submit y no envía datos.
- El panel Mobile es una página estática independiente, como el frame de referencia sin cabecera ni barra inferior. Cerrar filtros vuelve al catálogo; todavía no se conservan las selecciones entre páginas.
- La búsqueda y el ordenamiento no cambian los artículos. Más recientes es la única opción definida en el diseño. Reintentar no hace peticiones. La frase de Figma «Tu búsqueda se conserva» es texto del estado de ejemplo; esta etapa no almacena búsquedas ni garantiza persistencia.
- Ver detalle, Publicar, Reservas, Notificaciones y Mi cuenta siguen pendientes, con aria-disabled, title y descripción accesible, sin enlaces a archivos inexistentes. Inicio y Explorar sí navegan entre páginas implementadas. No se conectó Login con Inicio ni se simulan sesiones.

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

Revisión de Registro del 24/10/2026: Live Server y Chrome a 1440 × 1125 y 390 × 1249 px; recursos locales cargados, campos alineados y sin desplazamiento horizontal en los seis anchos probados. Navegación entre las tres páginas, teclado, foco y acceso a acciones mediante desplazamiento comprobados. Pulsar Crear cuenta o Enter en cualquiera de los seis campos no genera peticiones. Las capturas de Landing y Login antes/después coinciden píxel por píxel. Capturas, comparación y resultados guardados fuera del repositorio en Evidencias_Figma_V2/Documentacion/Implementacion_Registro_2026-10-24.

Revisión de Inicio del 24/10/2026: tres estados probados con Live Server y Chrome a 1440 y 390 px, además de 1280 y 320 px. Las medidas coinciden con los seis frames. Se comprobaron recursos, teclado, foco y acceso a los últimos botones mediante desplazamiento. Las capturas de Landing, Login y Registro permanecen idénticas a las anteriores; sus archivos HTML no se modificaron. Las evidencias están en Evidencias_Figma_V2/Documentacion/Implementacion_Inicio. No se ha probado en dispositivos físicos ni otros motores de navegador.

Revisión de Explorar del 24/10/2026: catálogo, vacío y error probados con Live Server y Chrome a 1440, 1280, 1024, 768, 390 y 320 px; panel Mobile a 390 y 320 px. Sin desplazamiento horizontal, errores de recursos ni uso de scripts. Se comprobaron Inter, etiquetas, foco de teclado, apertura/cierre del panel, restablecimiento nativo de filtros y acceso al último botón sin superposición de la barra inferior. Se compararon las siete vistas con capturas actuales de Figma. Las capturas de las seis páginas previas permanecen idénticas; solo se habilitaron sus enlaces relacionados con Explorar. Las evidencias se guardan en Evidencias_Figma_V2/Documentacion/Implementacion_Explorar. La revisión interactiva se realizó en Chrome; otros motores y dispositivos físicos siguen pendientes.

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

La rama de trabajo de esta implementación es feature/explorar. No se han realizado commits ni pushes de esta revisión.
