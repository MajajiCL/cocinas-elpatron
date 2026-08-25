# Cocinas El Patrón — landing

Sitio estático para **Fabricación de Cocinas El Patrón**, Heroica Caborca,
Sonora, México. Cocinas integrales en madera sólida.

## Cómo se levanta

No hay build. Es un solo `index.html` con sus imágenes.

```bash
python -m http.server 3090
```

## Cómo se despliega

GitHub Pages sirve la rama `main` desde la raíz. Cada push publica.

## Decisiones que conviene no deshacer

- **Sin GSAP ni Lenis.** Los revelados son `IntersectionObserver` y una
  transición CSS: doce líneas contra 120 KB de librerías. El sitio se ve
  desde Caborca con datos móviles y ese peso lo paga el cliente.
- **Sin galería ni carrusel.** Solo hay tres fotografías reales y son de la
  misma cocina. Un carrusel de tres fotos iguales delata falta de material;
  cada foto aparece una vez, grande y con pie de ficha. La escasez se lee
  como curaduría.
- **Sin imágenes generadas ni de banco.** El cliente vende artesanía real y
  su web anterior estaba llena de fotos de stock y sobras del demo de la
  plantilla — incluido un suéter y una gorra. Ese fue el problema, no la
  solución.
- **La paleta sale de su sello**, no de nuestro gusto: marino `#0C243C`,
  crema `#F5F0E4`, dorado `#A08250`.
- **El título dice "Cocinas integrales Caborca"** porque es la búsqueda real
  de su zona. No cambiarlo por algo más bonito.

## Lo que falta y depende del cliente

- Fotos de más cocinas terminadas — hoy hay una sola.
- Fotos del taller y del proceso: la madera en bruto, el corte, el armado.
  Es su diferenciador hecho imagen.
- Confirmar las cifras de 20 años y 500 clientes antes de dejarlas fijas.
