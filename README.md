# Sunsu Cleaning Service

Sitio web de [sunsucleaningservices.com](https://sunsucleaningservices.com) — servicios de limpieza profesional en Quito y sus valles.

Astro (salida estática) + Tailwind CSS v4. Una sola página con secciones ancladas.

## Comandos

| Comando           | Acción                                        |
| :---------------- | :-------------------------------------------- |
| `npm install`     | Instala dependencias                          |
| `npm run dev`     | Servidor local en `localhost:4321`            |
| `npm run build`   | Compila el sitio en `./dist/`                 |
| `npm run preview` | Previsualiza el build antes de desplegar      |

Node 22 (ver `.nvmrc`).

## Estructura

```text
public/            # Assets servidos tal cual + _headers y robots.txt
src/
  components/      # Secciones de la página (Hero, Services, Gallery…)
  data/            # Contenido editable: servicios, FAQ, testimonios, site.ts
  layouts/         # Layout.astro — <head>, SEO y JSON-LD
  pages/index.astro
  styles/global.css
```

Para cambiar textos, teléfono de WhatsApp o servicios, edita los archivos de `src/data/` — no hace falta tocar los componentes.

## Despliegue

Cloudflare Pages, proyecto `sunsu-cleaning-services`, conectado a este repo.

- Rama de producción: `main` (cada push despliega automáticamente)
- Comando de build: `npm run build`
- Directorio de salida: `dist`
- Dominios: `sunsucleaningservices.com` (principal) y `www.` (redirige al apex con una Redirect Rule de la zona)

Las cabeceras de seguridad y de caché se definen en `public/_headers`.
