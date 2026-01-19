---
layout: default
title: Imágenes y video
nav_order: 6
---

# Imágenes y video

## Imágenes

Guárdalas en `assets/img/` y enlázalas así:

```md
![Texto alternativo](assets/img/mi-imagen.png)
```

Recomendaciones:

- Prefiere `.png` para diagramas/íconos.
- Prefiere `.jpg` para fotos.
- Nombres cortos: `placa-esp32.jpg`.

---

## Video (YouTube/Vimeo)

Inserta un iframe dentro de un contenedor responsivo.

```html
<div class="responsive-embed">
  <iframe
    src="https://www.youtube.com/embed/ID_DEL_VIDEO"
    title="YouTube video player"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>
```
## Video (YouTube/Vimeo)

Inserta un video mp4.
```html
<video controls width="640">
  <source src="{{ '/assets/img/cuadrado.mp4' | relative_url }}" type="video/mp4">
  Tu navegador no soporta video HTML5.
</video>
```

> Nota: El CSS para `.responsive-embed` ya viene en `assets/css/custom.css`.

---

## PDF / Datasheets

Guárdalos en `assets/files/` (crea la carpeta) y enlázalos así:

```md
[Descargar datasheet](assets/files/datasheet.pdf)
```
