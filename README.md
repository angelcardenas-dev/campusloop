# CampusLoop

Marketplace universitario para estudiantes de Lima. Proyecto del curso IHC y Programación Web.

## Alcance actual

Están implementados la **Landing pública V2**, el **Inicio de sesión V2**, el **Registro V2**, el **Inicio autenticado V2**, **Explorar artículos V2**, **Detalle de artículo V2**, **Perfil público del vendedor V2**, **Activar perfil vendedor V2**, **Nueva publicación V2** y la **Etapa 1 de Reservas y mensajes V2**, en Desktop y Mobile. Todas son representaciones estáticas. El diseño vigente es:

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
- [Detalle Desktop · 278:3486](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3486): 1440 × 1474 px.
- [Detalle Mobile · 278:3554](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3554): 390 × 844 px, con contenido desplazable.
- [Perfil de Carlos Desktop · 278:3597](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3597): 1440 × 1235 px.
- [Perfil de Carlos Mobile · 278:3669](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3669): 390 × 844 px, con contenido desplazable.
- [Guía visual V2 · 14:33](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=14-33).
- [Biblioteca V2](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-2733).

Mi cuenta y las siguientes etapas de Reservas (propuestas de entrega, finalización y calificaciones) permanecen pendientes de implementación. La Etapa 1 incluye listado, consulta, vacío y error; no realiza operaciones reales. Sus referencias están en la tabla de Reservas. Los recursos compartidos para las próximas pantallas se conservan en assets.

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
├── detalle.html                  # MacBook Air M1: Disponible
├── detalle-reservado.html        # Mismo artículo: variante estática Reservado
├── detalle-vendido.html          # Mismo artículo: variante estática Vendido
├── perfil-vendedor.html          # Perfil público de Carlos Pérez
├── perfil-vendedor-nuevo.html    # Referencia estática: María López, sin reputación previa
├── activar-vendedor.html                  # Principiante, estado inicial
├── activar-vendedor-experiencia.html      # Experiencia previa, evidencia pendiente
├── activar-vendedor-error.html            # Error de aceptación de normas
├── activar-vendedor-listo.html            # Principiante con normas aceptadas
├── activar-vendedor-evidencia-error.html  # Error: faltan evidencia y normas
├── activar-vendedor-experiencia-lista.html # Ejemplo con adjunto privado y normas
├── activar-vendedor-borrador.html         # Modal estático con regreso al origen
├── activar-vendedor-pendiente.html        # Ejemplo de solicitud en revisión
├── activar-vendedor-activo.html           # Ejemplo de aprobación, sin reputación
├── publicar.html                         # Nueva publicación, formulario inicial
├── publicar-error.html                   # Validación visual de título, precio y fotos
├── publicar-listo.html                   # Ejemplo prellenado: Apuntes de Cálculo
├── publicar-borrador.html                # Confirmación estática de borrador
├── publicar-exito.html                   # Ejemplo visual de publicación exitosa
├── publicar-ia.html                      # Sugerencias opcionales de ejemplo
├── reservas.html                         # Listado Mobile y tres paneles Desktop
├── reservas-consulta.html                # Conversación de consulta de la MacBook
├── reservas-vacio.html                   # Sin interacciones, ejemplo estático
├── reservas-error.html                   # Error de carga, sin reintento real
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

Para revisar Detalle, usar Ver detalle en la tarjeta de la MacBook Air M1 de explorar.html. Las otras siete tarjetas conservan su detalle pendiente. detalle-reservado.html y detalle-vendido.html se abren directamente con Live Server; son referencias estáticas del mismo producto, no el resultado de pulsar Reservar.

Para revisar el perfil de Carlos, usar Ver perfil desde cualquiera de las tres variantes de Detalle o abrir perfil-vendedor.html. La variante de vendedor nuevo, perfil-vendedor-nuevo.html, se abre directamente con Live Server: representa a María López según Figma y no cambia de usuario ni de sesión.

Para revisar Activar perfil vendedor, usar el botón con ese nombre desde inicio.html o inicio-nuevo.html, o abrir activar-vendedor.html con Live Server. Las dos opciones de experiencia navegan entre ejemplos estáticos; no conservan lo escrito. Las variantes de error, listas, pendiente y activa se abren desde los enlaces de la tabla de Activación. Enviar solicitud no navega a una confirmación ni envía datos.

Para revisar Nueva publicación, abrir publicar.html con Live Server o usar Publicar / Publicar artículo desde inicio-vendedor.html o activar-vendedor-activo.html. En las vistas de comprador, Publicar abre activar-vendedor.html. Las variantes de error, lista y éxito se abren desde la tabla de Publicación; el botón Publicar artículo no crea ni simula una publicación. Guardar borrador y Ver sugerencias recorren ejemplos estáticos, sin conservar lo escrito.

Para revisar Reservas, abrir reservas.html con Live Server o usar Reservas en la cabecera o barra inferior de las páginas autenticadas. En Mobile, la primera interacción abre reservas-consulta.html y Volver a Reservas regresa al listado. En Desktop ambas páginas reutilizan la misma composición de tres paneles. Abrir reservas-vacio.html y reservas-error.html directamente para revisar sus estados de ejemplo; no dependen de una carga ni una búsqueda real. Comprobar a 1440 y 390 px, desplazándose hasta Enviar y Ver detalle de la reserva en la consulta Mobile.

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
- Ver detalle de la MacBook Air M1 abre detalle.html. Los detalles de los otros siete artículos, Notificaciones y Mi cuenta siguen pendientes, con aria-disabled, title y descripción accesible, sin enlaces a archivos inexistentes. Inicio, Explorar y Reservas sí navegan entre páginas implementadas. No se conectó Login con Inicio ni se simulan sesiones.

## Cómo está construido Detalle

Las tres páginas representan la MacBook Air M1 256 GB de Carlos Pérez, estudiante de la PUCP, con precio S/ 2,400. No son detalles genéricos para los demás productos.

| Archivo | Estado del artículo | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [detalle.html](detalle.html) | Disponible | [278:3486](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3486) | [278:3554](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3554) |
| [detalle-reservado.html](detalle-reservado.html) | Reservado | [296:943](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=296-943) | [297:883](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-883) |
| [detalle-vendido.html](detalle-vendido.html) | Vendido | [296:1052](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=296-1052) | [297:1006](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-1006) |

- Reutiliza home-header, home-bottom con Explorar activo, home-product, button, panel, home-badge, seller-rating, stars y auth-info. Solo añade reglas detail-; los estilos anteriores permanecen íntegros.
- main contiene la ruta de regreso, un article del producto y una section de relacionados. figure reúne la fotografía principal y tres miniaturas; section organiza Descripción e Incluye; aside identifica al vendedor y la información de coordinación segura. time expresa la fecha de publicación y ul los accesorios incluidos.
- En Desktop, inline-block y vertical-align alinean galería de 500 px, información de 444 px y vendedor de 288 px, separados por 24 px. calc adapta las dos primeras columnas al ancho disponible. En Mobile se apilan, con fotografía de 358 × 272 px a 390 px de pantalla.
- border-box, padding, márgenes, radios y min-height mantienen el Box Model. El contenido fluye y puede crecer en anchos menores. La cabecera y la barra inferior reutilizan el área central desplazable de Inicio sin ocultar las últimas acciones.
- Se reutilizan nueve imágenes existentes: galería de tres fotografías de la MacBook, avatares de María y Carlos y las cuatro fotografías de relacionados. Los ocho SVG usados incluyen las estrellas doradas y la navegación compartida. No se descargaron ni duplicaron recursos.
- La galería es estática: las tres miniaturas se muestran como imágenes, sin cambio interactivo de la foto principal. El salto opcional wbr en calificaciones reproduce el ajuste de la reputación de Figma sin cambiar su texto.
- En Disponible, Reservar artículo es un botón type="button" sin acción, marcado como pendiente. En Reservado y Vendido se muestra Artículo reservado / Artículo vendido con disabled y el estilo V2 correspondiente. No hay transición entre los estados al pulsar un control.
- Ver perfil abre perfil-vendedor.html desde las tres variantes de Detalle. Contactar vendedor mantiene el aspecto de Figma, con title, aria-disabled y descripción accesible, sin destinos inexistentes. Los cuatro relacionados conservan Ver detalle pendiente porque aún no existe un detalle propio para ellos.
- El enlace de la ruta, Inicio y Explorar sí funcionan. No se crean reservas, consultas, compras, sesiones ni solicitudes a servidores. El estado del producto es distinto de los estados de una interacción; Reservado no indica una compra completada.

## Cómo está construido el Perfil público del vendedor

| Archivo | Datos de ejemplo | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [perfil-vendedor.html](perfil-vendedor.html) | Carlos Pérez; 4.8, 32 calificaciones, 32 operaciones completadas y tres artículos | [278:3597](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3597) | [278:3669](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3669) |
| [perfil-vendedor-nuevo.html](perfil-vendedor-nuevo.html) | María López; perfil activo, sin publicaciones, calificaciones ni operaciones completadas | [296:1161](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=296-1161) | [297:1129](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=297-1129) |

- header y nav reutilizan la navegación autenticada, con Explorar seleccionado. main organiza identidad, privacidad, publicaciones y calificaciones recibidas. section agrupa identidad y artículos; cada producto y la calificación son article; aside contiene la información de privacidad y las calificaciones. blockquote y time representan el comentario y la fecha de la operación.
- Las clases nuevas seller-public- evitan conflictos con seller-card, seller-avatar y las demás clases seller- de la Landing. Se reutilizan home-header, home-bottom, home-product, button, panel, home-badge, seller-rating, stars y auth-info; no se cambian sus reglas existentes.
- Box Model, border-box, padding y márgenes reproducen las tarjetas. inline-block y vertical-align colocan avatar e información, y los artículos junto a las calificaciones en Desktop. calc permite adaptar el ancho de publicaciones. En Mobile se apilan los bloques y las tarjetas pasan de tres a dos columnas.
- Las cinco imágenes únicas usadas son los avatares de Carlos y María, MacBook Air M1, iPad Air y Física Universitaria. Se reutilizan ocho SVG e Inter locales, sin descargas ni copias adicionales. La variante nueva usa únicamente el avatar de María y los íconos de navegación.
- El fondo blanco de 80 px de la cabecera se extiende a todo el ancho mediante el fondo compartido de home-page; el contenido sigue centrado a un máximo de 1440 px. En Mobile, la cabecera de 72 px y la barra inferior de 80 px quedan fuera del contenido desplazable.
- Las tres acciones Ver perfil de Detalle conducen al perfil de Carlos. La MacBook del perfil regresa a detalle.html; los detalles de iPad y Física permanecen pendientes. Inicio y Explorar navegan a sus páginas existentes.
- Contactar vendedor y Ver calificaciones son representaciones estáticas, con title, aria-disabled y descripción accesible. No abren conversaciones ni un historial simulado. Las estrellas muestran las calificaciones del diseño; no son controles editables.
- La calificación de María se identifica como recibida por Carlos en su papel de vendedor. No se mezclan historiales de comprador. Comprador y vendedor podrán calificar de forma independiente una vez que ambos confirmen la finalización de la operación; esta entrega no implementa ese sistema ni ofrece un formulario anticipado.
- Un perfil activo no genera reputación: la variante de María conserva Aún sin calificaciones y Sin operaciones completadas todavía. Las evidencias de experiencia previa son privadas y no se muestran ni se enlazan.

## Cómo está construido Activar perfil vendedor

Son nueve representaciones estáticas de los frames finales V2. No se crea una segunda cuenta, no se envían solicitudes, no se activan perfiles y no se asigna reputación.

| Archivo | Variante | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [activar-vendedor.html](activar-vendedor.html) | Principiante inicial | [278:3813](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3813) | [278:3884](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3884) |
| [activar-vendedor-experiencia.html](activar-vendedor-experiencia.html) | Con experiencia previa | [298:2037](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2037) | [299:1135](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1135) |
| [activar-vendedor-error.html](activar-vendedor-error.html) | Error: normas sin aceptar | [306:2693](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-2693) | [307:3300](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3300) |
| [activar-vendedor-listo.html](activar-vendedor-listo.html) | Principiante listo | [306:2756](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-2756) | [307:3376](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3376) |
| [activar-vendedor-evidencia-error.html](activar-vendedor-evidencia-error.html) | Error: falta evidencia y normas | [306:2816](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-2816) | [307:3449](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3449) |
| [activar-vendedor-experiencia-lista.html](activar-vendedor-experiencia-lista.html) | Experiencia lista, adjunto de ejemplo | [306:2898](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-2898) | [307:3544](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3544) |
| [activar-vendedor-pendiente.html](activar-vendedor-pendiente.html) | Solicitud pendiente de revisión | [298:2116](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2116) | [299:1227](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1227) |
| [activar-vendedor-activo.html](activar-vendedor-activo.html) | Perfil activo, sin ventas ni calificaciones | [298:2161](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2161) | [299:1285](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1285) |
| [activar-vendedor-borrador.html](activar-vendedor-borrador.html) | Borrador guardado (modal) | [306:3148](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-3148) | [307:3798](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3798) |

- Reutiliza home-header, home-bottom, home-viewport, button, panel, auth-field, auth-control, auth-remember, auth-info, home-badge, Inter y las variables V2. Las reglas nuevas activate- están aisladas al final de styles.css; no cambian los estilos anteriores.
- header y nav conservan Inicio, Explorar, Publicar y Reservas, con Publicar seleccionado dentro de este módulo. Mi cuenta sigue en el avatar. main reúne la presentación y dos columnas: aside explica el proceso mediante ol, y form agrupa los campos con label. Las confirmaciones usan section y aside; el borrador se presenta como una vista independiente del modal.
- inline-block y vertical-align alinean la explicación de 456 px con el formulario de 792 px, separados por 32 px a 1440 px. border-box, padding de 24 px, márgenes de 16 px y controles de 48 px reproducen el Box Model de Figma. En Mobile se apilan en el flujo normal. El área home-viewport se desplaza entre la cabecera de 72 px y la barra de 80 px sin ocultar las últimas acciones.
- Las opciones Primera vez / Tengo experiencia son enlaces entre las dos vistas de ejemplo, como las acciones del diseño. No cambian roles ni ejecutan validación. Las casillas son controles nativos; los estados de error y las variantes listas se muestran independientemente, no se calculan al editar.
- El principiante solo muestra universidad/campus y aceptación de normas, sin solicitar evidencia. Con experiencia se muestran categorías, antigüedad, descripción, evidencia y referencias. La descripción usa textarea; se permite ajustar su altura y crece a 320 px para mantener legible el texto de ejemplo. Las evidencias se identifican como privadas, sin enlaces públicos ni un archivo real adjunto.
- Se reutilizan el avatar de María, ocho SVG existentes e Inter local. El avatar se verificó contra el hash del relleno de los 16 frames con cabecera. No se descargaron recursos ni se añadió una fotografía decorativa.
- Enviar solicitud es type="button" sin acción y con aria-disabled. Los formularios usan method="post", carecen de controles name y tienen un submit oculto deshabilitado para bloquear el envío implícito con Enter, incluso en la variante de un solo campo. No seleccionan ni suben archivos. El botón de evidencia es una representación pendiente.
- Guardar borrador abre el ejemplo del modal y lleva un fragmento que identifica la variante de origen. :target muestra su enlace de regreso correspondiente entre las seis variantes. **Solo se conserva la variante visual; no se conservan los datos editados ni existe almacenamiento o recuperación entre sesiones.** No se conectan guardado, solicitud pendiente y perfil activo como si fueran operaciones reales.
- Salir por ahora conduce provisionalmente a inicio.html, donde el comprador sigue sin perfil vendedor activo. El título del enlace y la nota visible indican este destino. Su destino definitivo será Mi cuenta cuando se implemente. Volver a Mi cuenta en la vista pendiente permanece identificado como no disponible, sin enlace roto; Inicio y Explorar permiten salir del módulo.
- El modal y las dos confirmaciones incluyen una nota visible que aclara que son ejemplos sin guardado, envío o aprobación real. Es una aclaración deliberada añadida fuera de la tarjeta de Figma, cuya composición y dimensiones se conservan. El estado Activo no muestra ventas ni calificaciones; Publicar artículo abre publicar.html como acceso estático de vendedor activo.
- En la entrega de Activación se habilitaron los dos botones Activar perfil vendedor de Inicio comprador y nuevo. La integración posterior de Publicar se documenta en la sección siguiente; Login y Registro permanecen intactos.

## Cómo está construida Nueva publicación

El nombre del frame V2 es Publicar artículo. Se implementan seis vistas, cada una con su referencia Desktop y Mobile, sin crear publicaciones reales:

| Archivo | Variante | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [publicar.html](publicar.html) | Formulario inicial | [278:3711](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3711) | [278:3774](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3774) |
| [publicar-error.html](publicar-error.html) | Validación visual de errores | [298:2205](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2205) | [299:1342](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1342) |
| [publicar-listo.html](publicar-listo.html) | Listo para publicar: datos de ejemplo | [306:2601](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-2601) | [307:3195](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3195) |
| [publicar-borrador.html](publicar-borrador.html) | Borrador guardado, sin almacenamiento | [298:2298](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2298) | [299:1448](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1448) |
| [publicar-exito.html](publicar-exito.html) | Publicación exitosa, solo referencia visual | [298:2331](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=298-2331) | [299:1494](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=299-1494) |
| [publicar-ia.html](publicar-ia.html) | Sugerencias opcionales, sin IA real | [306:3164](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=306-3164) | [307:3814](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=307-3814) |

- Reutiliza home-header, home-bottom con Publicar seleccionado, home-viewport, auth-field, auth-control, auth-info, explore-select, button y panel. La carga visual reutiliza activate-upload y el modal usa la composición existente de activate-draft. Las reglas publish- se añaden al final del CSS sin modificar las anteriores.
- header y nav conservan los cuatro apartados autenticados, notificaciones y avatar. main contiene la presentación y el formulario; cuatro section organizan fotos, información, descripción y ubicación. Cada control tiene label; figure y figcaption representan la fotografía prellenada y aside el asistente opcional y los avisos.
- inline-block y vertical-align alinean el formulario de 872 px y el asistente de 384 px con separación de 24 px a 1440 px. border-box incluye bordes y padding de 24 px; los bloques interiores usan márgenes de 24 px y controles de 48 px. En Mobile se apilan formulario y asistente, y las dos acciones pasan a bloques separados. La cabecera y la barra inferior quedan fuera del contenido desplazable.
- Se reutilizan el avatar de María, la fotografía original de Apuntes de Cálculo, ocho SVG e Inter. Los hashes de las fotografías coinciden con sus rellenos de Figma; sus encuadres usan object-fit: cover. No se descargaron ni duplicaron recursos. V2 / Recursos solo contiene el fondo de autenticación, que no se utiliza en estas pantallas.
- Categoría, condición, campus y disponibilidad usan selectores nativos con las opciones observadas en los frames: la categoría de ejemplo Académico · Apuntes, Como nuevo / Buen estado, PUCP · San Miguel y Coordinar con el comprador. No representan un catálogo completo ni selectores dependientes. El precio usa type=number, decimales y etiqueta S/. La descripción es textarea con límite nativo de 1000 caracteres, sin contador dinámico.
- La variante de error conserva el aviso general y los estados rojos de título y precio con aria-invalid y ayudas asociadas. Es un estado fijo de ejemplo: escribir no elimina sus errores ni ejecuta validación. La variante lista muestra una fotografía y los datos aprobados de Apuntes de Cálculo — Ciclo 2026-2, S/ 25, Buen estado.
- Publicar artículo es type=button, aria-disabled y no navega al éxito. El formulario declara method=post, no tiene campos name y contiene un submit oculto deshabilitado para impedir también los envíos con Enter. Subir fotos no selecciona ni transmite archivos. No hay creación de artículos, almacenamiento, pagos ni servicios externos.
- Guardar borrador abre una confirmación de ejemplo. Continuar editando regresa a la variante indicada por el fragmento del enlace: inicial, error o lista. Solo recupera la composición y los datos de ejemplo; **no se conserva lo escrito ni existe un borrador persistente**. La confirmación de éxito se abre directamente para revisión y no afirma una publicación real; Ver mis publicaciones permanece pendiente, sin enlace roto.
- Ver sugerencias abre el modal estático de Figma. Cancelar regresa al ejemplo de origen; Aplicar sugerencias abre publicar-listo.html y no genera contenido ni modifica los campos anteriores. Una nota visible aclara que son sugerencias de ejemplo. El modal se representa como página independiente, sin simular una superposición dinámica.
- Borrador, éxito y sugerencias tienen una nota aclaratoria fuera de sus tarjetas para distinguir ejemplos de operaciones reales. Se conservan las dimensiones originales de las tarjetas. Los controles nativos conservan teclado y foco; el textarea permite redimensionar su altura.
- Los accesos Publicar de inicio-vendedor.html y activar-vendedor-activo.html llevan a publicar.html. Los de Inicio comprador/nuevo, Explorar, Detalle y los perfiles públicos llevan a Activación. El vendedor mostrado en un perfil público no determina los permisos del visitante. Las otras variantes de Activación mantienen su composición y no saltan directamente a publicar; la pendiente conserva su estado.
- Inicio desde Publicar vuelve a inicio-vendedor.html. Las otras páginas conservan su usuario de ejemplo: no arrastran roles al navegar ni detectan sesiones. El acceso directo a publicar.html no está protegido; el control real de permisos requiere autenticación y backend futuros. Activar no exige experiencia a todos ni asigna reputación.

## Cómo está construido Reservas y mensajes — Etapa 1

| Archivo | Variante | Figma Desktop | Figma Mobile |
| --- | --- | --- | --- |
| [reservas.html](reservas.html) | Reservas inicial; listado Mobile | [278:3929](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3929) | [278:4006](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-4006) |
| [reservas-consulta.html](reservas-consulta.html) | Consulta con Carlos Pérez | Reutiliza la conversación de [278:3929](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=278-3929); no hay un frame Desktop independiente para esta entrega | [303:1433](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=303-1433) |
| [reservas-vacio.html](reservas-vacio.html) | Sin interacciones | [302:2468](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=302-2468) | [303:2208](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=303-2208) |
| [reservas-error.html](reservas-error.html) | Error de carga | [302:2499](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=302-2499) | [303:2252](https://www.figma.com/design/b14UnSTg43slwvD1fV0XCG/CampusLoop?node-id=303-2252) |

- header y nav reutilizan la cabecera y barra inferior home-, con Reservas activo. main agrupa la presentación y las interacciones; section organiza listado y conversación, article identifica cada interacción, producto y mensaje, y aside presenta el estado y la seguridad. time expresa las fechas y horas del diseño. form contiene un campo Mensaje con label asociado y nombre accesible.
- Las clases reservation- se añaden al final de styles.css sin cambiar las reglas anteriores. Se reutilizan panel, button, home-badge, auth-field, auth-control, auth-info, Inter y las variables V2. inline-block y vertical-align colocan los paneles de 280, 568 y 384 px separados por 24 px a 1440 px. calc adapta la columna central; border-box, padding, bordes y márgenes reproducen las medidas.
- En Mobile se separan listado y conversación. La cabecera de 72 px y barra inferior de 80 px quedan fuera de home-viewport; el contenido central se desplaza sin ocultar las últimas acciones. Vacío y error usan tarjetas compactas centradas, de 720 px máximos en Desktop y ancho disponible en Mobile.
- Se reutilizan la MacBook y los avatares de María, Carlos y Ana, ocho SVG locales e Inter. El avatar de Sofía es el círculo sin fotografía del frame, representado con CSS. No se descargaron ni duplicaron recursos.
- CL-1024 corresponde a la consulta sobre MacBook Air M1 256 GB de Carlos Pérez, PUCP · San Miguel, S/ 2,400. Consulta no equivale a Reserva ni a compra realizada. Confirmado describe una entrega acordada por ambos; Completada requiere finalización por ambos. Esta etapa solo explica los estados: no permite cambiarlos ni valorar operaciones.
- Solo la interacción de la MacBook abre su conversación. Las de iPad, calculadora y libro permanecen pendientes, sin abrir datos de otro producto. El acceso Ver reserva de Inicio sigue pendiente porque corresponde a la entrega Confirmada del iPad. Reservar artículo y Contactar vendedor de las páginas anteriores no se conectan a operaciones ni a esta consulta preexistente.
- Enviar, Reservar artículo, Ver detalle de la reserva y Reintentar son acciones pendientes, identificadas mediante aria-disabled, title y descripciones accesibles. Enviar y Reintentar no envían mensajes ni hacen peticiones. El formulario usa method=post, sin controles name, con Enviar type=button y un submit oculto deshabilitado que impide el envío implícito con Enter. Escribir solo modifica el campo local mientras la página permanece abierta; no hay almacenamiento ni persistencia.
- Explorar artículos del estado vacío abre explorar.html; Ir a Inicio del error abre inicio.html. Se habilitaron únicamente los enlaces de navegación Reservas y sus descripciones en las 24 páginas autenticadas que los contienen. No hay detección de roles ni sesiones: cada página conserva su usuario estático de ejemplo.
- No se implementan todavía propuestas de entrega, confirmación de finalización, calificaciones, envío/recepción de mensajes, carga de datos, autenticación ni creación de reservas. Mi cuenta y Notificaciones siguen pendientes. Los estados vacío y error se revisan por URL directa; ninguna acción los genera automáticamente.

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

Revisión de Detalle del 24/10/2026: tres estados probados con Live Server y Chrome a 1440, 1280, 1024, 768, 390 y 320 px. Las medidas de referencia coinciden con Figma: Desktop 1440 × 1474 y contenido Mobile de 2563 px dentro del frame de 390 × 844. Se comprobaron recursos, Inter, límites de texto, ausencia de desbordamiento horizontal, teclado, foco, desplazamiento y navegación Explorar → Detalle → Explorar. Solo la MacBook enlaza a detalle.html. Las veinte capturas de las diez páginas anteriores permanecen idénticas. Capturas, comparaciones e inventario de recursos se guardan en Evidencias_Figma_V2/Documentacion/Implementacion_Detalle. Otros navegadores y dispositivos físicos siguen pendientes.

Revisión de Perfil público del 26/10/2026: los dos perfiles probados con Live Server y Chrome a 1440, 1280, 390 y 320 px, además de 1920 px. Sin desplazamiento horizontal, textos fuera de sus cajas ni errores de carga. Inter, avatares, imágenes, SVG, enlaces desde las tres variantes de Detalle, teclado, foco y acceso al último botón mediante scroll comprobados. La franja blanca de la cabecera a 1920 px se verificó también fuera del contenedor centrado. Las 26 capturas de las 13 páginas anteriores permanecen idénticas. Las evidencias están en Evidencias_Figma_V2/Documentacion/Implementacion_Perfil_Vendedor. La comparación visual Mobile de Figma cubre el encuadre exportable; el contenido inferior se contrastó con sus capas y medidas. Quedan pendientes dispositivos físicos, otros navegadores y la revisión del usuario.

Revisión de Activar perfil vendedor del 26/10/2026: nueve vistas verificadas con Live Server y Chrome a 1440, 390, 320, 768, 1024, 1280 y 1920 px. Sin desplazamiento horizontal, errores de recursos ni textos fuera de sus cajas. Las medidas de las ocho composiciones principales coinciden con sus capas de Figma a 1440 y 390 px; el modal conserva su tarjeta de 480 × 278 px Desktop y 358 × 302 px Mobile. Se verificaron etiquetas, Inter, foco, teclado, acceso a las acciones por scroll, los seis regresos del borrador y Salir por ahora hacia Inicio. Enviar solicitud y Enter no generan peticiones; la selección/subida de evidencia no está implementada. Las 30 capturas de las quince páginas anteriores permanecen idénticas. Se compararon las nueve vistas Desktop y los nueve encuadres Mobile con Figma; el contenido Mobile inferior se contrastó con textos, jerarquía y medidas de capas, porque la exportación del frame está recortada al viewport. Las capturas, comparaciones y auditoría están fuera del repositorio en Evidencias_Figma_V2/Documentacion/Implementacion_Activar_Vendedor. Quedan pendientes la revisión visual del usuario, dispositivos físicos, otros motores y todas las funciones de backend.

Revisión de Nueva publicación del 26/10/2026: seis vistas probadas con Live Server y Chrome a 1440, 1280, 1920, 320, 390, 768 y 1024 px. Las medidas principales coinciden con las doce referencias V2 a 1440 y 390 px. Sin desbordamiento horizontal, textos fuera de sus cajas ni errores de recursos. Se verificaron etiquetas, Inter, foco, navegación por teclado, scroll y acceso a las últimas acciones sobre la barra inferior. Los enlaces distinguen vendedor activo y comprador; borrador y sugerencias regresan a sus ejemplos de origen. Publicar, Subir fotos y Enter no generan peticiones. Las 48 capturas de las 24 páginas anteriores permanecen idénticas. Se compararon las seis vistas Desktop y los seis encuadres Mobile; el contenido Mobile inferior se contrastó con capas y medidas de Figma y se capturó completo desde HTML. Las evidencias están en Evidencias_Figma_V2/Documentacion/Implementacion_Publicar. Quedan pendientes la revisión visual del usuario, dispositivos físicos, otros navegadores y las funciones reales descritas arriba.

Revisión de Reservas y mensajes — Etapa 1 del 27/10/2026: cuatro páginas probadas con Live Server y Chrome a 320, 390, 768, 1024, 1280, 1440 y 1920 px. Sin desplazamiento horizontal, textos fuera de sus cajas ni errores de recursos. Se comprobaron Inter, etiquetas, foco de teclado, desplazamiento Mobile, los 48 enlaces de navegación desde 24 páginas y los regresos del listado, consulta, vacío y error. Enter, Enviar, Reservar artículo y Reintentar no generan peticiones ni cambian el estado Consulta. Las 60 capturas de las 30 páginas anteriores coinciden exactamente con las referencias anteriores a los cambios. Las posiciones y medidas principales de las ocho vistas Desktop/Mobile coinciden con las capas de Figma. Se ajustaron los colores del aviso de seguridad, los estados informativos y la descripción del estado vacío al contraste del diseño. En la consulta Mobile el primer mensaje conserva dos líneas y la misma altura, pero Chrome coloca «M1» en la segunda línea mientras Figma lo muestra en la primera; se conserva Inter local y sus medidas sin forzar un corte artificial. Las capturas Mobile de Figma cubren el viewport; el contenido inferior se contrastó con capas y medidas y se capturó completo desde HTML. Evidencias: Evidencias_Figma_V2/Documentacion/Implementacion_Reservas_Mensajes_Etapa_1. Quedan pendientes la revisión visual del usuario, otros navegadores, dispositivos físicos y las funcionalidades fuera de esta etapa.

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

La rama de trabajo de esta implementación es feature/reservas-mensajes. No se han realizado commits, pushes, merges ni Pull Requests de esta revisión.
