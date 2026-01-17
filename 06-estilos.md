---
layout: default
title: Personalización visual
nav_order: 7
---

# Personalización visual

## Logo, favicon y CSS

Este repo carga un CSS adicional desde `head_custom.html` fileciteturn1file0L1-L2.

- CSS: `assets/css/custom.css`
- Favicon: `assets/img/favicon.ico`
- Logo: `assets/img/logotipo.png`

Además, el script en `head_custom.html` inserta el logo antes del texto del título fileciteturn1file0L4-L12.

---

## Footer personalizado

El footer del sitio se define en `_includes/footer_custom.html`. En tu versión actual incluye:

- Autor y crédito.
- Licencia CC BY 4.0.
- Enlace a “Uso de IA”. fileciteturn1file1L7-L14

---

## Sustituir por tu CSS institucional

Si ya tienes un `custom.css` con colores/logotipo institucional, solo reemplaza:

- `assets/css/custom.css`
- `assets/img/logotipo.png`
- `assets/img/favicon.ico`

Mantén los nombres para no tener que cambiar rutas.
