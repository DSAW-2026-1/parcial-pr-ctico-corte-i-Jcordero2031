## Parcial Desarrollo Web – Historial de Prompts

En este archivo vas a documentar la conversación con la IA. (cada prompt fue antes de ser enviado preguntado a la IA para mejorar la semantica basica y pudiera entender de manera mas detallada lo que tenia que hacer)  

---

### Prompt 1 – Estructura

**Prompt 1 enviado Crudo:**
```text
Crea la estructura HTML básica para un div de 400x300px con 4 esquinas, cada esquina tiene un cuadrado y un circulo Solo HTML, sin CSS.
```
**Prompt 1 enviado Corregido:**

```text
Eres un desarrollador frontend experto. Tu tarea en este prompt es ÚNICAMENTE definir la estructura HTML semántica y correcta para recrear la siguiente imagen:

DESCRIPCIÓN DE LA IMAGEN:
Un contenedor rectangular de 400px de ancho por 300px de alto con fondo azul oscuro. En cada una de las 4 esquinas del contenedor hay un par de figuras geométricas: un cuadrado y un círculo. El orden del par varía según la esquina:
- Esquina superior izquierda: cuadrado cian + círculo rosa (de izquierda a derecha)
- Esquina superior derecha: círculo rosa + cuadrado cian (de izquierda a derecha)
- Esquina inferior izquierda: círculo rosa + cuadrado cian (de izquierda a derecha)
- Esquina inferior derecha: cuadrado cian + círculo rosa (de izquierda a derecha)

INSTRUCCIONES PARA EL HTML:
1. Crea un archivo HTML básico con su estructura mínima: DOCTYPE, html, head y body.
2. Dentro del body, crea un único div contenedor principal con una clase descriptiva como "container" o "board".
3. Dentro del contenedor principal, crea exactamente 4 divs hijos, uno por cada esquina. Nómbralos con clases como "corner corner-top-left", "corner corner-top-right", etc.
4. Dentro de cada div de esquina, coloca exactamente 2 elementos: un div con clase "square" y otro div con clase "circle", en el orden correcto según la esquina descrita arriba.
5. NO uses etiquetas semánticas complejas como article, section, figure o svg. Usa únicamente divs con clases descriptivas.
6. NO escribas ningún CSS todavía. Solo el HTML limpio y bien indentado.
7. Agrega comentarios HTML breves para identificar cada esquina.

El resultado debe ser un HTML legible, bien estructurado y listo para recibir estilos en un siguiente paso. Muéstrame el código completo.
```

### Prompt 2 – Estilos base

**Prompt 2 Crudo**

```text
Agrega CSS básico: contenedor 400x300px fondo #0a0a8e, cuadrados 50x50px color #4fc3c3, círculos 50x50px color #e84393 con border-radius 50%. Sin posicionamiento.
```

**Prompt 2 corregido:**

```text
Eres un desarrollador frontend experto en CSS participando en una CSS Battle. Ya tienes el HTML estructurado de una imagen que consiste en un contenedor de 400px × 300px con fondo azul oscuro, que contiene 4 esquinas, cada una con un cuadrado cian y un círculo rosa. Ahora debes escribir ÚNICAMENTE los estilos base en CSS, sin posicionar todavía los elementos en pantalla.

INSTRUCCIONES PARA LOS ESTILOS BASE:

1. RESET BÁSICO: Aplica un reset simple usando el selector universal (*) para que margin, padding sean 0 y box-sizing sea border-box. No uses librerías externas de reset.

2. CONTENEDOR PRINCIPAL (.container o el nombre que usaste):
   - Ancho exacto: 400px
   - Alto exacto: 300px
   - Color de fondo: azul oscuro, usa el valor hexadecimal #0a0a8e o el más cercano que coincida visualmente con un azul marino intenso.

3. CUADRADOS (.square):
   - Ancho y alto: 50px × 50px
   - Color de fondo: cian/turquesa, usa aproximadamente #4fc3c3 o un valor cercano visualmente.
   - Sin bordes redondeados.

4. CÍRCULOS (.circle):
   - Ancho y alto: 50px × 50px
   - Color de fondo: rosa/magenta, usa aproximadamente #e84393 o un valor cercano visualmente.
   - Para hacerlo círculo usa border-radius: 50%. No uses otras propiedades complejas.

5. No uses aún ninguna propiedad de posicionamiento como position, top, left, flex o grid. Eso viene en el siguiente paso.

6. Mantén el CSS simple, con selectores de clase básicos. No uses selectores complejos como nth-child avanzados todavía.

Muéstrame solo el bloque de CSS completo, sin modificar el HTML previo.
```

---

### Prompt 3 – Layout y refinamiento (Flexbox/Grid)

**Prompt 3 Crudo:**
```text
Usa CSS Grid 2x2 en el contenedor y Flexbox en cada esquina para pegar los pares de figuras a sus 4 esquinas con padding 20px y gap 10px.
```

**Prompt 3 Corregido:**

```text
Eres un desarrollador frontend experto en CSS participando en una CSS Battle. Ya tienes el HTML estructurado y los estilos base aplicados (colores y tamaños). Ahora tu tarea final es posicionar todos los elementos exactamente como aparecen en la imagen usando Flexbox o Grid. El resultado final debe combinar el HTML y el CSS completo en un único archivo.

DESCRIPCIÓN DEL LAYOUT A LOGRAR:
El contenedor de 400px × 300px tiene 4 grupos de figuras ubicados en sus 4 esquinas. Cada grupo tiene un cuadrado cian (~50px) y un círculo rosa (~50px) colocados lado a lado horizontalmente. Hay un espacio interno (padding) de aproximadamente 15px desde los bordes del contenedor. Los pares de figuras dentro de cada esquina tienen una separación de unos 5px entre sí.

INSTRUCCIONES DE LAYOUT:

1. CONTENEDOR PRINCIPAL:
   - Usa display: flex en el contenedor principal.
   - Usa flex-wrap: wrap para que los 4 grupos de esquina se distribuyan.
   - Usa justify-content: space-between para separar horizontalmente los grupos izquierdos de los derechos.
   - Usa align-content: space-between para separar verticalmente los grupos superiores de los inferiores.
   - Agrega padding de 15px en todos los lados del contenedor para que las figuras no toquen el borde.

2. GRUPOS DE ESQUINA (.corner):
   - Usa display: flex en cada grupo de esquina.
   - Usa gap de aproximadamente 5px para separar el cuadrado del círculo dentro del grupo.
   - No uses position: absolute ni márgenes manuales complicados para posicionar los grupos.

3. ORDEN DE LAS FIGURAS:
   - Esquina superior izquierda (.corner-top-left): el cuadrado va primero en el HTML, luego el círculo.
   - Esquina superior derecha (.corner-top-right): el círculo va primero en el HTML, luego el cuadrado.
   - Esquina inferior izquierda (.corner-bottom-left): el círculo va primero en el HTML, luego el cuadrado.
   - Esquina inferior derecha (.corner-bottom-right): el cuadrado va primero en el HTML, luego el círculo.

4. AJUSTE FINO:
   - Revisa que el contenedor tenga exactamente 400px × 300px incluyendo el padding (usa box-sizing: border-box).
   - Si las figuras no quedan perfectamente alineadas a las esquinas, ajusta el padding del contenedor o el gap entre figuras, pero sin usar valores mayores a 20px.

5. Entrégame el archivo HTML completo con el CSS dentro de una etiqueta <style> en el <head>. Todo en un solo bloque de código, limpio y listo para copiar y pegar.
```

### Prompt 4 y 5 – Correciones

**Prompt 4 Crudo**
```text
Los 4 grupos de figuras se apilan en una fila en vez de ir uno por esquina. Corrige el layout para que cada par quede en su esquina correcta.
```

**Prompt 4 Corregido:**
```text
Eres un desarrollador frontend experto en CSS. 
Tienes el siguiente código que genera una imagen INCORRECTA y necesitas corregirlo 
para que coincida exactamente con la imagen objetivo.

CÓDIGO ACTUAL (genera resultado incorrecto):
[pega aquí el código completo]

DESCRIPCIÓN DEL RESULTADO INCORRECTO QUE ESTÁ GENERANDO:
- En la parte superior aparecen 3 pares de figuras alineados en una sola fila horizontal.
- En la parte inferior solo aparece 1 par en la esquina inferior izquierda.
- La esquina inferior derecha no aparece o está cortada.
- Los 4 grupos NO están distribuidos uno por esquina como se desea.

DESCRIPCIÓN DEL RESULTADO CORRECTO QUE DEBES LOGRAR:
Un contenedor de 400px × 300px con fondo azul oscuro. Exactamente 4 grupos de figuras, 
uno en cada esquina del contenedor:
- Esquina superior izquierda: cuadrado cian a la izquierda, círculo rosa a la derecha.
- Esquina superior derecha: círculo rosa a la izquierda, cuadrado cian a la derecha.
- Esquina inferior izquierda: círculo rosa a la izquierda, cuadrado cian a la derecha.
- Esquina inferior derecha: cuadrado cian a la izquierda, círculo rosa a la derecha.
Cada par de figuras está pegado a su esquina respectiva con un padding de ~15px desde el borde del contenedor.

PROBLEMA RAÍZ A CORREGIR:
El uso de flex-wrap: wrap junto con justify-content: space-between y align-content: 
space-between no está funcionando porque los 4 divs .corner no tienen un ancho definido, entonces el flexbox los agrupa todos en la primera fila si caben.

INSTRUCCIONES PARA LA CORRECCIÓN (usa solo propiedades simples, nada complejo):

1. ELIMINA flex-wrap: wrap, justify-content: space-between y align-content: 
   space-between del .container.

2. En su lugar, cambia el .container para que use CSS Grid con la siguiente 
   configuración simple:
   - display: grid
   - grid-template-columns: 1fr 1fr  (dos columnas iguales)
   - grid-template-rows: 1fr 1fr     (dos filas iguales)
   - padding: 15px

3. Para que cada grupo .corner se pegue a su esquina dentro de su celda de grid, 
   convierte cada celda en un flex container:
   - Las esquinas superiores: align-items: flex-start
   - Las esquinas inferiores: align-items: flex-end
   - Las esquinas izquierdas: justify-content: flex-start
   - Las esquinas derechas: justify-content: flex-end
   Puedes hacer esto con clases específicas por esquina: 
   .corner-top-left, .corner-top-right, .corner-bottom-left, .corner-bottom-right

4. NO cambies el HTML, los tamaños de las figuras, ni los colores. Solo corrige el CSS 
   del .container y agrega las propiedades de alineación a las clases de cada esquina.

5. Mantén el gap: 5px dentro de cada .corner para la separación entre cuadrado y círculo.

Entrega el archivo HTML completo corregido con el CSS dentro del <style>, listo para copiar y pegar.
```
**Prompt 5 Crudo:**
```text
Verifica que el contenedor sea 400x300px con box-sizing: border-box, grid 2x2, cada esquina con flex y align correcto, colores exactos y orden de figuras correcto en cada esquina.
```

**Prompt 5 Corregido:**
```text
Eres un desarrollador frontend experto en CSS. 
Tienes un código que ya fue parcialmente corregido pero puede tener pequeñas desviaciones visuales respecto a la imagen objetivo. Necesitas hacer un ajuste fino de píxeles.

IMAGEN OBJETIVO — descripción precisa de medidas:
- Contenedor: exactamente 400px de ancho × 300px de alto, fondo #0a0a8e.
- Cada figura (cuadrado y círculo): exactamente 50px × 50px.
- Separación entre el cuadrado y el círculo dentro de un mismo par: ~5px.
- Distancia desde el borde del contenedor hasta las figuras: ~15px en todos los lados.
- Los pares de figuras deben estar visualmente "pegados" a sus respectivas esquinas, sin flotar hacia el centro.
- Las figuras superiores deben estar alineadas en su parte superior con el borde superior del contenedor (respetando el padding).
- Las figuras inferiores deben estar alineadas en su parte inferior con el borde inferior del contenedor (respetando el padding).

CHECKLIST DE VERIFICACIÓN — revisa estos puntos uno por uno en el código:

1. ¿El .container tiene exactamente width: 400px y height: 300px? 
   ¿Tiene box-sizing: border-box para que el padding no aumente el tamaño total?

2. ¿El .container usa display: grid con grid-template-columns: 1fr 1fr y grid-template-rows: 1fr 1fr?

3. ¿Cada .corner tiene display: flex y gap: 5px?

4. ¿La clase .corner-top-left tiene justify-content: flex-start y align-items: flex-start?

5. ¿La clase .corner-top-right tiene justify-content: flex-end y align-items: flex-start?

6. ¿La clase .corner-bottom-left tiene justify-content: flex-start y align-items: flex-end?

7. ¿La clase .corner-bottom-right tiene justify-content: flex-end y align-items: flex-end?

8. ¿Los colores son exactamente: fondo #0a0a8e, cuadrados #4fc3c3, círculos #e84393?

9. ¿El HTML tiene los elementos en el orden correcto dentro de cada esquina?
   - corner-top-left: primero .square, luego .circle
   - corner-top-right: primero .circle, luego .square
   - corner-bottom-left: primero .circle, luego .square
   - corner-bottom-right: primero .square, luego .circle

Corrige todos los puntos que no cumplan y entrega el código HTML completo final con el <style> incluido.
```
