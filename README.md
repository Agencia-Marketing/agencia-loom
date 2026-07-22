# Plantilla 2 — Neo-Brutalist Agency

Landing page neo-brutalista para agencia de marketing digital. Rediseño visual radical de Plantilla 1 — mismo contenido, estética industrial de alto contraste.

## Stack

- **[Astro](https://astro.build)** v5 — Static site generator
- **[Tailwind CSS](https://tailwindcss.com)** v3 — Utility-first CSS
- **[PostCSS](https://postcss.org)** + Autoprefixer
- **[Cloudflare Pages](https://pages.cloudflare.com)** — Hosting
- **Barlow Condensed + JetBrains Mono** — Tipografías neo-brutalist
- **Material Symbols** — Iconografía

## Estética

- Fondo negro profundo (`#0A0A0A`) con acento neon lime (`#AAFF00`)
- Zero `border-radius` en todo el sitio
- Sombras duras con offset (sin blur): `4px 4px 0 #AAFF00`
- Tipografía masiva Barlow Condensed (900 weight) + JetBrains Mono para labels
- Grid visible, bordes estructurales 2px
- Acento secundario neon naranja-rojo (`#FF3C00`)

## Empezar

```bash
npm install
npm run dev       # → localhost:4321
npm run build     # → dist/
npm run preview
```

## Personalizar

### Colores (cambiar en 2 lugares)

**1. `src/styles/global.css` → bloque `:root`:**
```css
:root {
  --color-accent:    #AAFF00;  /* Color principal neon */
  --color-secondary: #FF3C00;  /* Acento secundario */
  --color-bg:        #0A0A0A;  /* Fondo */
  --color-text:      #F0F0F0;  /* Texto */
}
```

**2. `tailwind.config.mjs` → `theme.extend.colors`:**
```js
colors: {
  accent: "#AAFF00",
  secondary: "#FF3C00",
  bg: "#0A0A0A",
}
```

### Tipografía
En `src/layouts/Layout.astro`, reemplazar el link de Google Fonts y las familias en CSS.

## Servicios (9 páginas)

| Ruta | Servicio |
|---|---|
| `/servicios/desarrollo-web` | Desarrollo Web |
| `/servicios/agentes-ia` | Agentes de IA |
| `/servicios/diseno-grafico` | Diseño Gráfico |
| `/servicios/redes-sociales` | Gestión de Redes |
| `/servicios/campanas-publicitarias` | Campañas de Ads |
| `/servicios/videomarketing` | Videomarketing |
| `/servicios/embudos-venta` | Embudos de Venta |
| `/servicios/creadores-ugc` | Creadores UGC |
| `/servicios/creacion-contenido` | Creación de Contenido |

## Deploy

```bash
git push  # → Cloudflare Pages build automático
```
