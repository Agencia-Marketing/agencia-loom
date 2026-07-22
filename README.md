# Loom — Agencia Digital

Sitio web de Loom, agencia de consultoría en marketing y publicidad digital (México y Estados Unidos). Estética neo-brutalista clara: fondo blanco/gris, acento azul, tipografía masiva, sombras duras sin blur.

## Stack

- **[Astro](https://astro.build)** v5 — output `server`
- **[@astrojs/cloudflare](https://docs.astro.build/en/guides/integrations-guide/cloudflare/)** — adapter, deploy a Cloudflare Workers/Pages
- **[Tailwind CSS](https://tailwindcss.com)** v3 — Utility-first CSS
- **[PostCSS](https://postcss.org)** + Autoprefixer
- **Barlow Condensed + Barlow + JetBrains Mono** — Tipografías
- **Material Symbols** — Iconografía

## Estética

- Fondo claro (`#f1f1f1`) con acento azul Loom (`#0063DA`)
- Zero `border-radius` en todo el sitio
- Sombras duras con offset (sin blur): `3px 3px 0 #0063DA`
- Tipografía masiva Barlow Condensed (900 weight, uppercase) + JetBrains Mono para labels
- Grid visible, bordes estructurales 2px

## Empezar

```bash
npm install
npm run dev       # → localhost:4321
npm run build     # → dist/
npm run preview
```

## Estructura

```
src/
  layouts/Layout.astro   # header, footer, fuentes — compartido por todas las páginas
  styles/global.css      # design tokens (:root) y clases .brut-*
  pages/
    index.astro
    nosotros.astro
    contacto.astro
    servicios/*.astro    # 9 páginas de servicio
public/
  img/                   # logo, imágenes de marca
```

## Páginas

| Ruta | Contenido |
|---|---|
| `/` | Home — hero, grid de servicios, por qué elegirnos, CTA |
| `/nosotros` | Historia, stats, equipo |
| `/contacto` | Formulario, datos de contacto, redes sociales |

### Servicios (9 páginas)

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

## Personalizar

### Colores

Definidos como CSS custom properties en `src/styles/global.css` → bloque `:root`:

```css
:root {
  --color-accent: #0063DA;  /* Azul Loom, color principal */
  --color-bg:     #f1f1f1;  /* Fondo */
  --color-text:   #111111;  /* Texto */
}
```

`tailwind.config.mjs` → `theme.extend.colors` también define `accent`/`bg`/`text` para clases utilitarias de Tailwind; mantenerlo alineado con `global.css` al rebrandear.

### Tipografía

En `src/layouts/Layout.astro`, reemplazar el link de Google Fonts y las familias en `global.css`.

## Deploy

```bash
git push  # → Cloudflare Workers build automático
```
