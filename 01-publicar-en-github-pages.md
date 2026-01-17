---
layout: default
title: Publicar en GitHub Pages
nav_order: 2
---

# Publicar tu sitio en GitHub Pages

## Opción A (recomendada para clase): Project Page

Publicas el sitio desde un repositorio tipo:

- `https://github.com/TU_USUARIO/TU_REPO`
- `https://TU_USUARIO.github.io/TU_REPO/`

### Paso 1. Crear el repo

1. Crea un repositorio en GitHub (p. ej. `documentacion-equipo-3`).
2. Sube el contenido de esta plantilla (o clónala y empújala a tu repo).

### Paso 2. Configurar `_config.yml`

Edita estos dos campos:

```yml
url: "https://TU_USUARIO.github.io"
baseurl: "/TU_REPO"
```

- `url` es tu página principal de GitHub Pages.
- `baseurl` es el nombre del repositorio, con `/` al inicio.

### Paso 3. Activar GitHub Pages

En tu repositorio:

1. **Settings** → **Pages**
2. **Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: `main`
   - Folder: `/ (root)`
3. Guarda.

GitHub te dará la URL final.

---

## Opción B: User/Organization Page

Si publicas desde el repo especial `TU_USUARIO.github.io`:

```yml
url: "https://TU_USUARIO.github.io"
baseurl: ""
```

---

## Validación rápida

- Revisa que el menú lateral aparezca.
- Revisa que los links internos funcionen.
- Revisa que el logo/estilos carguen (si ya pusiste tus assets).

> Nota: Si cambias `url` o `baseurl`, espera a que GitHub vuelva a desplegar.
