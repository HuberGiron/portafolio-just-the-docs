---
layout: default
title: Estilos y personalización visual
nav_order: 5
---

# Estilos y personalización visual

Esta sección explica **cómo funciona la personalización visual** en este repositorio y qué debes modificar para poner el sitio con tu identidad (logo, colores, footer, etc.) **sin romper la estructura**.

---

## 1) ¿Qué archivos controlan el estilo?

En este repositorio, el estilo y algunos elementos visuales se controlan con **tres piezas**:

1) **CSS** con los colores y ajustes visuales:  
   - `assets/css/custom.css`

2) **Head** (carga el CSS, favicon y agrega el logo en el título):  
   - `_includes/head_custom.html`

3) **Footer** (tu footer “propio”, con licencia y “Last modified”):  
   - `_includes/footer_custom.html`

Estructura típica:

```text
.
├─ _includes/
│  ├─ head_custom.html
│  └─ footer_custom.html
├─ assets/
│  ├─ css/
│  │  └─ custom.css
│  └─ img/
│     ├─ logotipo.png
│     └─ favicon.ico
└─ ...
```

---

## 2) “Lo mínimo” para poner tu identidad

Si solo quieres “poner tu marca” y seguir avanzando con el curso, haz esto:

### Paso A — Cambia el logo
Reemplaza el archivo:

- `assets/img/logotipo.png`

**Regla importante:** conserva **exactamente** el nombre `logotipo.png` para no tener que cambiar rutas.

### Paso B — Cambia el favicon
Reemplaza el archivo:

- `assets/img/favicon.ico`

### Paso C — Ajusta colores (si lo necesitas)
Edita:

- `assets/css/custom.css`

Más abajo tienes una guía de “qué cambiar” sin perderte.

---

## 3) Cómo funciona `head_custom.html` (logo + favicon + CSS)

Este archivo se inserta en el `<head>` del sitio y hace 3 cosas:

- Carga `custom.css`.
- Define el favicon.
- Inserta el logo **antes del texto** del título del sitio (en la barra lateral / encabezado, según el tema).

Código relevante:

```html
<link rel="stylesheet" href="{{ '/assets/css/custom.css' | relative_url }}">
<link rel="icon" href="{{ '/assets/img/favicon.ico' | relative_url }}" sizes="any">

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const titleLink = document.querySelector('.site-title');
    if (!titleLink || titleLink.querySelector('img')) return;

    const img = document.createElement('img');
    img.src = "{{ '/assets/img/logotipo.png' | relative_url }}";
    img.alt = "Logo";
    img.className = "site-logo";
    titleLink.prepend(img);
  });
</script>
```

**Qué modificar aquí:**
- Normalmente **no necesitas cambiar nada** si mantienes:
  - `assets/css/custom.css`
  - `assets/img/logotipo.png`
  - `assets/img/favicon.ico`

**Cuándo sí lo cambiarías:**
- Si decides renombrar archivos (no recomendado).
- Si quieres insertar otro elemento adicional en el `<head>` (por ejemplo: analytics, meta tags especiales, etc.).

---

## 4) Cómo funciona `custom.css` (qué tocar y qué NO tocar)

`assets/css/custom.css` contiene reglas para:

- Colores del header y sidebar.
- Colores de enlaces (y quitar el morado/azul por defecto).
- Estados hover/active del menú.
- Jerarquía visual del menú (nivel 1, 2, 3).
- Ajustes del botón hamburguesa en móvil.
- Ocultar el footer original del tema y mostrar tu footer personalizado.
- Tamaño del logo en el título.

### 4.1 Paleta rápida (qué buscar)

En este CSS verás repetidos estos colores:

- **Rojo principal:** `#E00034`
- **Rosa claro/acento:** `#FFD5DE`
- **Rojo oscuro hover:** `#b00028`

Recomendación práctica:
- Para cambiar la “marca”, normalmente te basta con cambiar:
  - `#E00034` (color principal)
  - `#FFD5DE` (acento)
  - y la variable `--link-color`.

Ejemplo de variable de enlaces:

```css
:root { --link-color: #E00034; }
a, a:visited { color: var(--link-color); }
```

### 4.2 Sidebar y navegación (menú lateral)

El CSS fuerza el sidebar en rojo y los links en blanco:

```css
.side-bar,
.side-bar .site-nav,
.side-bar .nav-list { background-color: #E00034 !important; }

.nav-list .nav-list-link,
.nav-list .nav-list-link:visited { color: #ffffff !important; }
```

Y define estados activos/hover más visibles.

### 4.3 Footer: ocultar el del tema y usar el tuyo

El CSS oculta el footer del tema:

```css
footer.site-footer { display: none !important; }
```

Y define estilos para tu footer:

```css
.custom-footer { ... }
.custom-footer a { ... }
```

Esto funciona en conjunto con `_includes/footer_custom.html`.

---

## 5) Footer personalizado (`footer_custom.html`)

Tu footer actual:

- Muestra copyright.
- Enlaza a tu perfil.
- Enlaza a la licencia CC BY 4.0.
- Enlaza a la página “Uso de IA”.
- Muestra “Last modified” con fecha/hora.

Ejemplo (simplificado):

```html
<footer class="custom-footer">
  <p class="custom-footer__copy">
    Copyright © 2026 IBERO.
    <a href="...">Huber Giron</a>.
    <a href="...">CC BY 4.0</a>.
    <a href="{{ '/uso-ia/' | relative_url }}">Uso de IA</a>
  </p>

  <p class="custom-footer__modified">
    <strong>Last modified:</strong>
    {{ modified | date: "%A, %B %-d, %Y at %H:%M" }}
  </p>
</footer>
```

### Qué cambiar aquí (típicamente)
- El texto “Copyright © 2026 …”.
- Tu nombre y enlace.
- La licencia (si aplica).
- El enlace “Uso de IA” (si quieres ocultarlo o moverlo).

---

## 6) Checklist rápido cuando “no se ve” el cambio

1) **Guardaste el archivo** (en Codespaces o en tu editor).
2) Hiciste **commit** y **push** al repositorio.
3) Esperaste a que **GitHub Actions** termine (verde).
4) Abriste tu sitio y forzaste recarga:
   - Windows: `Ctrl + F5` o `Ctrl + Shift + R`
   - macOS: `Cmd + Shift + R`

Tip de diagnóstico:
- Abre directamente el CSS en el navegador:  
  `TU_URL/assets/css/custom.css`  
  Si no carga, el problema es de ruta o de build.


---

## Siguiente sección

Este es el último tema de personalización. Puedes volver a:

- [Inicio](index.md)
- [Publicar en GitHub Pages](01-publicar-en-github-pages.md)
