# 🏛️ DOSSIER DE BENCHMARKING MUNDIAL Y SKILLS PARA COCINAS EL PATRÓN
**Dirección de Arte, UX Editorial y Técnicas de Alta Ebanistería**
*Preparado por Antigravity para colaboración con Claude Code & MajajiCL*

---

## 1. Los 4 Grandes Referentes Mundiales de Ebanistería de Lujo

| Referente | Origen | Enfoque Principal | Lo que debemos extraer para *El Patrón* |
| :--- | :--- | :--- | :--- |
| **Plain English Design** | 🇬🇧 Reino Unido / 🇺🇸 NY | *Monasterio del Oficio*. Estética georgiana, proporciones clásicas, colores apagados de cal y lino. | **La dignidad del silencio:** Cero popups, cero banners comerciales. La web se presenta como el catálogo de una galería privada. Tipografía con aire generoso y filetes de 1px. |
| **DeVOL Kitchens** | 🇬🇧 Loughborough, UK | *Artesanía y Narrativa*. Maestros artesanos, herrajes forjados a mano, pátina histórica. | **La humanización de la materia:** Relato de cada proyecto como un encargo único con número de registro y contexto geográfico (exactamente lo que hicimos con *Lámina I, II y III*). |
| **Henrybuilt** | 🇺🇸 Seattle, USA | *Ingeniería en Madera Sólida*. Ebanistería arquitectónica de ultra-precisión. | **La honestidad constructiva:** Explicación técnica de por qué la madera maciza vence al tablero aglomerado (el ensamblado, el comportamiento ante la humedad y la durabilidad a 20+ años). |
| **George Nakashima Woodworkers** | 🇺🇸 New Hope, USA | *La Filosofía del Árbol*. Respeto reverencial a la veta, al grano y a las uniones clásicas. | **El Tratado de Maderas:** La madera no se elige por un catálogo de colores sintéticos; se elige por la especie botánica, dureza y aroma (*Encino, Tzalam, Cedro, Banak, Pino*). |

---

## 2. Las 5 "Skills" y Módulos Interactivos de Clase Mundial

Para elevar [index.html](file:///D:/CLAUDIOPRO/cocinas-elpatron/index.html) al nivel de un sitio premiado en *Awwwards* sin saturarlo ni perder rendimiento:

### A. Selector Táctil de Maderas (Tratado Interactivo)
* **Concepto:** En lugar de una lista estática, cada especie (*01 Encino, 02 Tzalam, 03 Cedro, 04 Banak, 05 Pino*) muestra un micro-zoom a la textura de la veta real al pasar el cursor o pulsar en móvil.
* **Técnica:** Animación de texto con GSAP Flip o desplazamiento de cartela tipográfica a 60 FPS con Lenis.

### B. El Comparador Interactivo: "Año 0 vs. Año 10" (MDF vs. Madera Sólida)
* **Concepto:** Un slider sutil de antes/después o línea temporal interactiva:
  * *Aglomerado (MDF/Melamina):* El vapor hincha el aserrín, los tornillos pierden agarre, se bota a los 5 años.
  * *Madera Sólida El Patrón:* A los 10 años se lija, se rebarniza y se hereda a la siguiente generación.
* **Técnica:** SVG mask reveal o scrub interactivo con `ScrollTrigger`.

### C. Blueprint & Despiece de Ebanistería (Diagrama Técnico Animado)
* **Concepto:** Una sección con dibujo técnico vectorial (líneas doradas de 1px sobre fondo marino) que muestra el ensamble de caja y espiga (*mortise and tenon*) o cola de milano (*dovetail*), demostrando por qué una gaveta de madera sólida soporta 50 kg sin deformarse.

### D. Micro-interacción de Medallón Notarial
* **Concepto:** El sello heráldico 1:1 en el hero responde con una micro-rotación inercial ultra-suave al hacer scroll, como el sello de cera de una carta diplomática.

### E. Microdata Schema de Máxima Autoridad Local (Sonora)
* **Datos estructurados:** `HomeAndConstructionBusiness` con catalogación `hasOfferCatalog`, geolocalización precisa de Caborca y radio de servicio a Nogales, Puerto Peñasco, San Carlos y Sonoyta.

---

## 3. Plan de Acción Conjunto (Antigravity ↔ Claude Code)

1. **Claude Code** puede implementar directamente en `cocinas-elpatron`:
   * El módulo de **Despiece Técnico / Ensambles** en SVG.
   * La optimización del **Tratado de Maderas** interactivo.
2. **Antigravity** queda listo para:
   * Auditar rendimiento, contraste y accesibilidad WCAG AAA.
   * Generar el código exacto de animaciones GSAP o snippets de micro-interacción cuando Claude lo requiera vía `agy.py`.
