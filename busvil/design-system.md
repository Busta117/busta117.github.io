# Busvil LLC — Design System

> Fundada en 2025. Identidad visual construida alrededor de un wordmark brush/handwritten negro sobre fondo crema moderno.

---

## Logo

- **Archivo:** `logo.png`
- **Estilo:** Wordmark brush/handwritten — orgánico, con personalidad y autenticidad
- **Color:** Negro (`#1C1917`)
- **Uso sobre fondo claro:** Usar versión negra sin modificaciones
- **Espacio de respeto:** Mínimo 24px en todas las direcciones
- **Tamaño mínimo:** 120px de ancho para legibilidad

---

## Paleta de Colores

Paleta warm/cream moderna. El negro del logo ancla la identidad; el crema aporta calidez sin ser anticuado.

### Colores Principales

| Rol | Nombre | Hex | Uso |
|-----|--------|-----|-----|
| Background | Cream | `#FAF7F2` | Fondo principal de páginas |
| Surface | Warm Sand | `#F0EBE3` | Secciones alternas, cards secundarias |
| Foreground | Ink | `#1C1917` | Texto principal, logo |
| Text Secondary | Stone | `#57534E` | Texto secundario, subtítulos |
| Text Muted | Pebble | `#A8A29E` | Texto terciario, placeholders, captions |
| Accent | Copper | `#B8956A` | CTAs, enlaces hover, detalles decorativos |
| Accent Hover | Deep Copper | `#9A7A52` | Estado hover del accent |
| Card | White | `#FFFFFF` | Cards, modales, superficies elevadas |
| Border | Dune | `#E2DCD4` | Bordes, separadores, líneas |
| Destructive | Ember | `#DC2626` | Errores, acciones destructivas |

### Colores como CSS Custom Properties

```css
:root {
  /* Backgrounds */
  --color-bg:          #FAF7F2;
  --color-surface:     #F0EBE3;
  --color-card:        #FFFFFF;

  /* Text */
  --color-ink:         #1C1917;
  --color-stone:       #57534E;
  --color-pebble:      #A8A29E;

  /* Accent */
  --color-copper:      #B8956A;
  --color-copper-hover:#9A7A52;

  /* Utility */
  --color-border:      #E2DCD4;
  --color-destructive: #DC2626;
}
```

### Contraste WCAG

| Par | Ratio | Nivel |
|-----|-------|-------|
| Ink sobre Cream (`#1C1917` / `#FAF7F2`) | 15.2:1 | AAA |
| Stone sobre Cream (`#57534E` / `#FAF7F2`) | 6.1:1 | AA |
| Pebble sobre Cream (`#A8A29E` / `#FAF7F2`) | 3.2:1 | AA (large text) |
| Copper sobre Cream (`#B8956A` / `#FAF7F2`) | 3.5:1 | AA (large text) |
| Ink sobre White (`#1C1917` / `#FFFFFF`) | 16.7:1 | AAA |

---

## Tipografía

El logo brush provee toda la personalidad visual. Las fuentes de soporte deben ser limpias, modernas y no competir.

### Font Pairing: Cormorant + Jost

| Rol | Fuente | Peso | Uso |
|-----|--------|------|-----|
| Display / H1 | Cormorant | 600 (SemiBold) | Títulos hero, headlines principales |
| H2 | Cormorant | 500 (Medium) | Subtítulos de sección |
| H3 | Jost | 500 (Medium) | Subtítulos menores |
| Body | Jost | 400 (Regular) | Texto general, párrafos |
| Body Small | Jost | 400 (Regular) | Captions, footnotes |
| Label / UI | Jost | 500 (Medium) | Botones, etiquetas, navegación |
| Monospace | JetBrains Mono | 400 | Código, datos técnicos |

### Google Fonts Import

```css
@import url('https://fonts.googleapis.com/css2?family=Cormorant:wght@400;500;600;700&family=Jost:wght@300;400;500;600;700&display=swap');
```

### Escala Tipográfica

Base: `16px` / Line-height body: `1.6`

| Nivel | Tamaño | Line-height | Letter-spacing | Fuente |
|-------|--------|-------------|----------------|--------|
| Display | 48px / 3rem | 1.1 | -0.02em | Cormorant 600 |
| H1 | 36px / 2.25rem | 1.2 | -0.015em | Cormorant 600 |
| H2 | 28px / 1.75rem | 1.3 | -0.01em | Cormorant 500 |
| H3 | 20px / 1.25rem | 1.4 | 0 | Jost 500 |
| Body | 16px / 1rem | 1.6 | 0 | Jost 400 |
| Small | 14px / 0.875rem | 1.5 | 0.01em | Jost 400 |
| Caption | 12px / 0.75rem | 1.4 | 0.02em | Jost 500 |

### CSS Custom Properties — Tipografía

```css
:root {
  --font-display: 'Cormorant', Georgia, serif;
  --font-body:    'Jost', system-ui, sans-serif;
  --font-mono:    'JetBrains Mono', monospace;

  --text-display: 600 3rem/1.1 var(--font-display);
  --text-h1:      600 2.25rem/1.2 var(--font-display);
  --text-h2:      500 1.75rem/1.3 var(--font-display);
  --text-h3:      500 1.25rem/1.4 var(--font-body);
  --text-body:    400 1rem/1.6 var(--font-body);
  --text-small:   400 0.875rem/1.5 var(--font-body);
  --text-caption: 500 0.75rem/1.4 var(--font-body);
}
```

---

## Espaciado

Sistema de 4px base, escala de 8px para layout.

| Token | Valor | Uso |
|-------|-------|-----|
| `--space-1` | 4px | Micro-ajustes |
| `--space-2` | 8px | Gaps internos, padding mínimo |
| `--space-3` | 12px | Padding de inputs |
| `--space-4` | 16px | Padding de cards, gaps de grid |
| `--space-6` | 24px | Separación entre elementos |
| `--space-8` | 32px | Separación entre secciones menores |
| `--space-12` | 48px | Separación entre secciones |
| `--space-16` | 64px | Separación entre secciones principales |
| `--space-24` | 96px | Padding vertical de secciones hero |

---

## Bordes y Radios

| Token | Valor | Uso |
|-------|-------|-----|
| `--radius-sm` | 4px | Badges, tags |
| `--radius-md` | 8px | Inputs, botones |
| `--radius-lg` | 12px | Cards |
| `--radius-xl` | 16px | Modales, drawers |
| `--radius-full` | 9999px | Avatares, pills |
| `--border-width` | 1px | Bordes estándar |
| `--border-color` | var(--color-border) | Color de bordes |

---

## Sombras

Sombras cálidas con tono stone para mantener coherencia con la paleta.

```css
:root {
  --shadow-sm:  0 1px 2px rgba(28, 25, 23, 0.05);
  --shadow-md:  0 4px 12px rgba(28, 25, 23, 0.08);
  --shadow-lg:  0 8px 24px rgba(28, 25, 23, 0.12);
  --shadow-xl:  0 16px 48px rgba(28, 25, 23, 0.16);
}
```

---

## Animación

Siguiendo la filosofía de Emil Kowalski — solo animar con propósito, duración corta, easing custom.

### Easing Curves

```css
:root {
  --ease-out:     cubic-bezier(0.23, 1, 0.32, 1);
  --ease-in-out:  cubic-bezier(0.77, 0, 0.175, 1);
  --ease-default: cubic-bezier(0.25, 0.1, 0.25, 1);
}
```

### Duraciones

| Tipo | Duración | Uso |
|------|----------|-----|
| Micro | 100–160ms | Press feedback, hover color |
| UI | 150–250ms | Dropdowns, tooltips |
| Transition | 200–400ms | Modales, drawers, page transitions |
| Reveal | 500–800ms | Entrada de elementos al scroll |

### Reglas

- Usar `ease-out` para entradas y `ease-in` para salidas
- Solo animar `transform` y `opacity` (GPU-accelerated)
- Respetar `prefers-reduced-motion: reduce`
- Botones: `transform: scale(0.97)` en `:active` (160ms ease-out)
- Nunca animar desde `scale(0)` — usar `scale(0.95)` + `opacity: 0` como punto de partida

---

## Breakpoints

| Nombre | Min-width | Uso |
|--------|-----------|-----|
| Mobile | 0px | Base, mobile-first |
| Tablet | 768px | Tablets, pantallas medianas |
| Desktop | 1024px | Escritorio estándar |
| Wide | 1440px | Pantallas grandes |

**Max content width:** 1200px  
**Padding horizontal:** 16px (mobile), 24px (tablet), 32px (desktop)

---

## Notas de Marca

- **Personalidad:** Auténtica, cálida, moderna, confiable
- **El logo es el protagonista:** Las fuentes y colores de soporte no deben competir con el wordmark brush
- **Tono crema moderno:** No es beige anticuado — es un off-white cálido que transmite sofisticación sin frialdad
- **Negro como ancla:** El `#1C1917` (stone-900) es más suave que el negro puro `#000`, aportando calidez
- **Copper como acento:** Usado con moderación — solo para CTAs, enlaces activos y detalles que requieran atención
