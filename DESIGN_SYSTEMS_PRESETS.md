# 🎨 BIBLIOTECA MAESTRA DE PRESETS Y SISTEMAS DE DISEÑO (DESIGN.MD)
**Extraído y sintetizado desde Refero Styles, Draftly Space y 21st.dev**
*Para uso directo de Claude Code, Antigravity y MajajiCL en proyectos web de clase mundial*

---

## 🏛️ ARQUETIPO 1: "Renaissance Gallery on Putty Paper"
*Referencia: `styles.refero.design` (Inspirado en Structured & Henrybuilt)*
*Ideal para: Ebanistería fina, arquitectura de lujo, monografías, marcas de tradición y alta gama.*

```yaml
archetype: "Renaissance Gallery on Putty Paper"
mood: "Monástico, solemne, autoritario, de grado de inversión"
contrast: "Lienzo de algodón crudo alternado con salas negras de museo"
rules:
  radius: "0px (estricto ángulo recto de 90° en todo elemento)"
  shadows: "CERO sombras, CERO degradados, CERO esquinas redondeadas"
  borders: "Líneas de 1px cortando de lado a lado como pliegos editoriales"
  typography: "La letra es la arquitectura (titulares monumentales hasta 180px con tracking negativo)"
```

### Tokens CSS & Paleta de Color
```css
:root {
  /* Lienzo y Salas */
  --bg-paper: #F5F0E4;          /* Crema Lino cálido (Lienzo claro) */
  --bg-paper-light: #FAF6EE;    /* Marfil puro */
  --bg-dark: #0C243C;           /* Azul Noble / Sala oscura (o Negro Ónice #0A0A0C) */
  --bg-dark-surface: #143452;   /* Azul Petróleo para filetes en sala oscura */

  /* Tinta y Tipografía */
  --text-ink: #0C243C;          /* Tinta principal sobre claro */
  --text-ink-muted: #6E6656;    /* Gris tierra secundario */
  --text-light: #FAF6EE;        /* Tinta clara sobre sala oscura */
  --text-light-muted: rgba(245, 240, 228, 0.65);

  /* Acentos de Alta Ebanistería */
  --accent-gold: #A08250;       /* Dorado heráldico y versalitas */
  --accent-gold-light: #C4A264; /* Dorado luminoso en sala oscura */
  --border-hairline: #E2D8C3;   /* Filete de 1px sobre claro */

  /* Fuentes */
  --font-hero: "Playfair Display", Georgia, serif;
  --font-seal: "Cinzel", Georgia, serif;
  --font-body: "Inter", system-ui, -apple-system, sans-serif;
}
```

---

## ⚡ ARQUETIPO 2: "Swiss Modernist & Dark Bento"
*Referencia: `21st.dev` & `Draftly Space` (Inspirado en Linear, Raycast, Vercel)*
*Ideal para: SaaS, plataformas tecnológicas, CRM de WhatsApp, dashboards y landing pages interactivas.*

```yaml
archetype: "Swiss Modernist & Dark Bento"
mood: "Precisión quirúrgica, densidad de datos elegante, micro-iluminación"
rules:
  radius: "12px a 16px en tarjetas Bento"
  shadows: "Sombra difusa 0 20px 40px rgba(0,0,0,0.6) + borde interior 1px rgba(255,255,255,0.08)"
  grid: "Bento Grid asimétrico 3 columnas con featured cards y sparklines"
  typography: "Inter / Geist / JetBrains Mono con números tabulares"
```

### Tokens CSS & Paleta de Color
```css
:root {
  --bg-void: #08090A;           /* Negro profundo de fondo */
  --bg-surface: #121417;        /* Superficie de tarjeta Bento */
  --bg-surface-hover: #181B20;  /* Estado hover con elevación sutil */

  --border-subtle: rgba(255, 255, 255, 0.08); /* Borde milimétrico */
  --border-glow: rgba(94, 106, 210, 0.4);      /* Resplandor de foco */

  --text-primary: #FFFFFF;
  --text-secondary: #8A8F98;
  --text-accent: #5E6AD2;       /* Violeta Linear o Naranja Eléctrico #FF7800 */

  --font-sans: "Inter", system-ui, sans-serif;
  --font-mono: "JetBrains Mono", monospace;
}
```

---

## 🌿 ARQUETIPO 3: "Monastic Tactile Minimalism"
*Referencia: `styles.refero.design` (Inspirado en Boffi, The Row, Aesop)*
*Ideal para: Marcas de diseño interior, spas, cosmética de autor, estudios de arquitectura.*

```yaml
archetype: "Monastic Tactile Minimalism"
mood: "Silencioso, orgánico, espacioso, anti-comercial"
rules:
  whitespace: "70% del viewport libre de texto"
  images: "Fotografía a sangre (full-bleed) de 90vh con transiciones de opacidad lentas (1.2s)"
  interaction: "Text links discretos con subrayado al hover; cero botones llamativos"
```

### Tokens CSS
```css
:root {
  --bg-sand: #EDE8E1;           /* Arena cálida */
  --bg-charcoal: #1C1B1A;       /* Carbón mineral */
  --text-body: #2B2927;
  --accent-bronze: #7B6F63;
  --font-editorial: "Cormorant Garamond", serif;
}
```

---

## 🛠️ RECETAS DE COMPONENTES INTERACTIVOS (21st.dev & GSAP)

### 1. Scroll con Inercia Lenis + GSAP (El estándar de fluidez)
```javascript
// Añadir en el head:
// <script src="https://cdn.jsdelivr.net/npm/lenis@1.1.18/dist/lenis.min.js"></script>
// <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
// <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/ScrollTrigger.min.js"></script>

const lenis = new Lenis({
  duration: 1.2,
  easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
  smoothWheel: true
});

lenis.on('scroll', ScrollTrigger.update);
gsap.ticker.add((time) => { lenis.raf(time * 1000); });
gsap.ticker.lagSmoothing(0);
```

### 2. Titular Monumental con Split-Text por Letra (Sin romper palabras)
```javascript
function animarTitularMonumental(selector) {
  const tit = document.querySelector(selector);
  if (!tit) return;
  
  const palabras = tit.textContent.trim().split(/\s+/);
  tit.innerHTML = palabras.map(p => 
    `<span class="palabra" style="display:inline-block; white-space:nowrap;">` +
      p.split('').map(l => `<span class="letra" style="display:inline-block; will-change:transform,opacity;">${l}</span>`).join('') +
    `</span>`
  ).join(' ');

  gsap.from(`${selector} .letra`, {
    yPercent: 120,
    opacity: 0,
    duration: 1.1,
    stagger: 0.03,
    ease: "expo.out",
    scrollTrigger: { trigger: selector, start: "top 85%" }
  });
}
```

### 3. Comparador Interactivo Antes / Después (Año 0 vs Año 10)
```html
<div class="comparador-madera" style="position:relative; width:100%; height:480px; overflow:hidden; border:1px solid var(--border-hairline);">
  <div class="capa capa-aglomerado" style="position:absolute; inset:0; background:#1a1a1a; color:#fff; padding:40px;">
    <span class="folio">Año 5 · Tablero Aglomerado (MDF)</span>
    <h3 style="margin-top:16px;">El vapor hincha el aserrín prensado; las bisagras se aflojan y se bota.</h3>
  </div>
  <div class="capa capa-solida" style="position:absolute; inset:0; width:50%; background:var(--bg-paper); color:var(--text-ink); padding:40px; border-right:2px solid var(--accent-gold); overflow:hidden;">
    <span class="folio" style="color:var(--accent-gold);">Año 10 · Madera Sólida El Patrón</span>
    <h3 style="margin-top:16px;">La veta madura con el tiempo; se lija, se rebarniza y renace.</h3>
  </div>
</div>
```

---

## 💡 Cómo aplicar estos Presets en tu flujo de trabajo

1. **Para *Cocinas El Patrón*:** Usa el **Arquetipo 1** (*Renaissance Gallery on Putty Paper*) combinado con el arquetipo de *Henrybuilt*.
2. **Para *AAC Web / CRM*:** Usa el **Arquetipo 2** (*Swiss Modernist & Dark Bento*) con bordes sutiles y métricas en tiempo real.
3. **Para pedirle a Claude Code:** Solo tienes que indicarle: *"Aplica el Arquetipo 1 del archivo `DESIGN_SYSTEMS_PRESETS.md` para maquetar la sección X"*.
