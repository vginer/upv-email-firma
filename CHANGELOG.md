# Registro de cambios

Cambios relevantes de este repositorio. Sigue la idea de
[Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/) y el
[versionado semántico](https://semver.org/lang/es/): el número menor sube con
cambios que no obligan a rehacer nada; el mayor se reservará para cambios de
estructura.

El archivo `.htm` lleva además su propia marca de fecha en los comentarios, en
la línea `ULTIMO CAMBIO`. Esa es la que vale si alguien se lleva el archivo
suelto, fuera del repositorio.

---

## [1.1] – 2026.08.19

### Cambiado

- La firma ya no lleva `margin-left:7.1pt` en sus dos tablas. Era una
  compensación heredada del exportador de Word y desplazaba el bloque 9 px a la
  derecha respecto al texto del mensaje. Ahora queda a ras. No afecta a ninguna
  medida interna.
- Añadida al `.htm` una línea `ULTIMO CAMBIO` fechada, dentro del bloque de
  comentarios.

### Corregido

- **La regla para cuando la columna izquierda es la más alta.** La versión 1.0
  decía que había que repartir el sobrante entre los dos huecos de la columna
  derecha en proporción 0,375 / 0,625. Es falso. Midiendo los quince modelos
  del PDF normativo se ve que el hueco entre los iconos y el grafo se mantiene
  siempre entre 25 y 30 px, y que todo el sobrante va al hueco entre el
  logotipo y los iconos, que va de 15,4 px (logotipo de 50 px de alto) a
  43,4 px (logotipo de 19,6 px). Corregido en el README y en el `.htm`.
- **El recuento de marcas `[CAMBIAR]`**: son nueve, no diez. La décima que
  figuraba era la línea «Universitat Politècnica de València», que precisamente
  no se cambia.
- La numeración de esa misma lista en el README, que salía descolocada porque
  dos elementos compartían línea y Markdown renumeraba por su cuenta.

### Añadido

- Apartado **«Si prefieres no poner el logotipo de tu unidad»**, con lo que hay
  que quitar del HTML, lo que hace la norma en ese caso —iconos arriba, grafo
  abajo, y el hueco entre ambos es el que crece: 24,8 px en las firmas base,
  55,6 px en los campus de Alcoy y Gandia, 66,5 px en unidades internas— y cómo
  recalcularlo.
- Apartado **«Cómo se hizo»**, con el crédito a la asistencia de Claude (Opus 5)
  en la reconstrucción y la depuración.
- Tabla con las medidas de seis modelos del PDF que llevan logotipo, como
  respaldo de la regla del reparto vertical.

### Quitado

- Las pastillas «probado en» y «ancho», que sobrecargaban la cabecera del
  README.

---

## [1.0] – 2026.08.17

Primera publicación. Firma correspondiente al modelo «firma base sin foto»
(360 px) combinado con la plantilla de personal de escuelas, facultades,
unidades docentes y de investigación, reconstruida para sobrevivir al editor de
firmas del nuevo Outlook y a los saneadores de HTML de Gmail, Yahoo y los
clientes de iOS.

Decisiones que vienen de esa primera versión, por si ayudan a entender el
archivo:

- Maquetación con tablas y todo el CSS en línea: al pegar en el editor de
  firmas solo sobrevive el fragmento, sin `<head>`, `<style>` ni atributos del
  `<body>`.
- La línea de color es el fondo de una celda, no un borde: un `bgcolor`
  sobrevive a cualquier saneado.
- Los separadores llevan dentro un `&nbsp;` con `font-size` y `line-height`
  iguales a la altura del hueco, porque una celda vacía con solo `height`
  colapsa en Yahoo.
- Logotipo de la unidad en gris `#808080`, para que no desaparezca cuando el
  destinatario lee con el tema oscuro.
- Imágenes al tamaño exacto de presentación, porque el editor de firmas del
  nuevo Outlook no permite redimensionarlas.
