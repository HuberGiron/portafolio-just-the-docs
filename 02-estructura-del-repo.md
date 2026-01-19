---
layout: default
title: Estructura del repositorio
nav_order: 3
---

# Estructura del repositorio

Una estructura base (la de este repo) suele verse así:

```text
.
├─ _config.yml
├─ README.md
├─ index.md
├─ 01-publicar-en-github-pages.md
├─ 02-estructura-del-repo.md
├─ ... (más páginas .md)
├─ _includes/
│  ├─ head_custom.html
│  └─ footer_custom.html
├─ assets/
│  ├─ css/
│  │  └─ custom.css
│  └─ img/
│     ├─ logotipo.png
│     └─ ...
└─ 
```

## Qué hace cada cosa

- **`_config.yml`**: configuración del sitio (título, búsqueda, baseurl, plugins, etc.).
- **`index.md`**: la página de inicio (home).
- **`*.md`**: páginas de contenido.
- **`_includes/`**: inyecciones de HTML (header, footer, scripts).
- **`assets/`**: CSS, imágenes, favicons, PDFs, etc.

---

## Convenciones recomendadas

- Nombres en minúsculas y con guiones: `mi-pagina.md`.
- Una página = un tema.
- Mantén **pocos niveles** de anidación (2 niveles suele ser suficiente).
- Usa `assets/img/` para imágenes y `assets/files/` para PDFs.

---

## Front matter

Just the Docs usa “front matter” en YAML al inicio de cada `.md`:

```yml
---
layout: default
title: Mi página
nav_order: 10
---
```

- `title` aparece en el menú.
- `nav_order` controla el orden.
- `layout: default` funciona bien para la mayoría de páginas.

---

## Siguiente sección
[Estructura del repositorio](02-estructura-del-repo.md)