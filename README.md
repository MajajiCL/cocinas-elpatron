# Cocinas El Patrón — landing

Sitio estático para **Fabricación de Cocinas El Patrón**, Heroica Caborca,
Sonora, México. Cocinas integrales en madera.

## Cómo se levanta

No hay build. Es un solo `index.html` con sus imágenes.

```bash
python -m http.server 3090
```

## Cómo se despliega

GitHub Pages sirve la rama `main` desde la raíz. Cada push publica.

---

## Por qué esta versión (v7) se ve distinta a las seis anteriores

Las versiones 1 a 6 se rehicieron cambiando paleta, tipografía y retícula, y
ninguna convenció. **El problema no era el diseño: era que había tres
fotografías y las tres eran de la misma cocina.** Ninguna retícula arregla la
falta de material.

En esta versión hay obra que mostrar: 124 renders finales de cocina salieron
del archivo de Visualissa MX, de los cuales se seleccionaron a mano 18 por luz
y encuadre.

### La referencia, y qué se copió de ella

Se estudiaron henrybuilt.com (la única de las tres que permite inspección;
bulthaup y eggersmann devuelven 403), más bulthaup, SieMatic y Poggenpohl por
material publicado. Lo que las tres comparten y aquí se aplica:

1. **Una sola familia tipográfica**, grotesca, sin serif decorativa. La
   jerarquía sale del tamaño, el peso y el tracking. Henrybuilt entero es
   Helvetica Neue Light. Aquí es Archivo.
2. **El titular del hero no es gigante ni centrado.** Va abajo a la izquierda,
   con el rótulo de ubicación en versalitas encima. La foto habla; el texto
   sólo la nombra.
3. **Imágenes a sangre**: sin marco, sin sombra, sin esquina redondeada. Una
   esquina redondeada convierte una cocina en tarjeta de aplicación.
4. **Retícula asimétrica** (60/40, 40/60, 33/67), nunca tres columnas iguales.
   La toma general se alterna con el macro del material.

### El argumento de venta que faltaba

El taller entrega **el proyecto en 3D antes de fabricar**. Es un servicio que
efectivamente presta y que casi nadie ofrece en Caborca, y resuelve la objeción
real del cliente: comprometer dinero sin saber cómo va a quedar. Ahora es el
eje de la página, no un detalle.

## Decisiones que conviene no deshacer

- **Sin GSAP ni Lenis.** Los revelados son `IntersectionObserver` y una
  transición CSS: doce líneas contra 120 KB de librerías. El sitio se ve desde
  Caborca con datos móviles y ese peso lo paga el cliente.
- **La paleta sale de su sello**, no de nuestro gusto: marino `#0C243C`, crema
  `#F5F0E4`, dorado `#A08250`. Los neutros se derivan del marino con sesgo
  cálido; no hay un solo gris de sistema.
- **El hero lleva dos degradados, no uno.** Medido con canvas: bajo el titular
  había puntos de encimera clara con contraste **1.44** contra la crema —
  ilegible, cuando AA pide 3.0 para texto grande. El vertical solo no alcanzaba
  sin apagar la cocina entera, así que se sumó uno lateral que protege la
  columna del texto y deja limpia la parte derecha de la foto.
- **`section[id] { scroll-margin-top: 74px }`**: la barra es fija y sin eso los
  enlaces del menú dejan el titular debajo de la barra.
- **`h2 + p { margin-top }` va en el CSS global**, no en cada bloque, para que
  no se olvide en la próxima sección que se agregue.
- **El título dice "Cocinas Integrales en Caborca"** porque es la búsqueda real
  de su zona. No cambiarlo por algo más bonito.

## Sobre las imágenes — leer antes de tocarlas

- `img/obra/*` son **renders del proyecto 3D**, no fotografías de obra
  terminada, y la página los presenta así: la sección se titula "Proyectos" y
  el pie dice *"Imágenes del proyecto 3D entregado al cliente"*. **No cambiar
  ese pie por "nuestros trabajos"**: sería presentar un render como una foto.
- Salen del archivo de **Visualissa MX**, que son proyectos de otros clientes
  del estudio. Mateo autorizó su uso. Si El Patrón consigue renders de sus
  propios proyectos, sustituirlos es lo correcto.
- `img/cocina-general.jpg` **sí es una fotografía real** de una cocina
  instalada en Caborca, y por eso va sola y grande en su propia sección. Las
  otras tres fotos del mismo trabajo no se usan: tres fotos de la misma cocina
  en carrusel delatan que no hay más material.
- `img/mat-taller.jpg` y `img/mat-veta.jpg` **quedaron fuera**: tienen aspecto
  de imagen generada o de banco, que es exactamente el problema que tenía la
  web anterior del cliente.
- Los macros de veta se recortan de los renders sobre zonas **con madera**. El
  primer intento recortó el centro de la imagen y salieron encimeras y una
  pared de azulejo.

## Lo que falta y depende del cliente

- Fotos reales de más cocinas instaladas. Hoy hay una sola.
- Fotos del taller y del proceso: la madera en bruto, el corte, el armado. Es
  su diferenciador hecho imagen, y las que había eran de banco.
- Confirmar las cifras de 20 años y el plazo de 4 a 6 semanas antes de dejarlas
  fijas.
- El dominio: el canonical apunta a `cocinaselpatron.mx`, que hay que
  registrar o corregir antes de publicar.
