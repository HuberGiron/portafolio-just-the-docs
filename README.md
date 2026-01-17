# Plantilla Just the Docs (para clase)

Esta es una **plantilla de documentación** basada en **Just the Docs** (Jekyll) para que tus alumnos:

- descarguen/clonen un repositorio,
- editen páginas Markdown,
- agreguen imágenes y videos,
- publiquen en **GitHub Pages**.

Incluye header/footer personalizados y carga CSS adicional desde `head_custom.html` fileciteturn1file0L1-L2 y un footer con créditos/licencia fileciteturn1file1L7-L14.

---

## 1) Flujo para el docente (crear el repo base)

1. Crea un repositorio, por ejemplo: `plantilla-docs-clase`.
2. Sube el contenido de este template.
3. Edita `_config.yml`:

   - `title` y `description`
   - `url` y `baseurl` (depende del tipo de GitHub Pages)

   En tu versión original ya usas `remote_theme` y `baseurl` fileciteturn1file2L5-L11; aquí lo dejamos preparado para que tus alumnos solo lo ajusten.

4. Activa GitHub Pages: **Settings → Pages → Deploy from a branch → main / root**.
5. Comparte a tus alumnos:

   - la URL del repo
   - la URL pública del sitio

---

## 2) Flujo para alumnos

### Opción A: Clonar (si el docente les da acceso de escritura)

```bash
git clone https://github.com/DOCENTE/TU_REPO.git
cd TU_REPO
```

Trabajen en ramas y hagan Pull Request.

### Opción B: Fork (recomendado si cada alumno/equipo publica su propio sitio)

1. Haz **Fork** del repo.
2. Clona tu fork.
3. Cambia `_config.yml`:

```yml
url: "https://TU_USUARIO.github.io"
baseurl: "/NOMBRE_DE_TU_REPO"
```

4. Activa GitHub Pages en tu repo.

---

## 3) Editar contenido

- La home está en `index.md`.
- Agrega nuevas páginas creando archivos `.md` con front matter:

```yml
---
layout: default
title: Mi nueva página
nav_order: 10
---
```

- Imágenes: `assets/img/` y luego:

```md
![texto](assets/img/mi-imagen.png)
```

---

## 4) Correr el sitio localmente (opcional)

Si quieres vista previa en tu computadora:

1. Instala Ruby (recomendado con rbenv/asdf) y Bundler.
2. En la carpeta del repo:

```bash
bundle install
bundle exec jekyll serve
```

Abre: `http://127.0.0.1:4000`

---

## Licencia

Define la licencia que usarás para el contenido del curso (MIT, CC BY 4.0, etc.). Este template deja un footer con CC BY 4.0 como ejemplo fileciteturn1file1L11-L13.
