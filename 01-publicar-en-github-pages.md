---
layout: default
title: Publicar en GitHub Pages
nav_order: 2
---

# Publicar sitio en GitHub Pages

En este curso vamos a publicar tu documentación como un **sitio web** usando:

- **GitHub** (para guardar el repositorio y el historial)
- **GitHub Pages** (para convertir el repositorio en una URL pública)
- **Codespaces** (para editar desde el navegador, sin instalar nada)

---

## 1) Conceptos

- **GitHub**: plataforma para alojar proyectos (repositorios) y colaborar.
- **Repositorio (repo)**: carpeta de proyecto con archivos + historial.
- **Commit**: “guardar un cambio” en el historial con un mensaje.
- **Push**: enviar tus commits a GitHub (a la nube).
- **GitHub Pages**: servicio que publica tu repo como sitio web.
- **Pipeline (Actions)**: proceso automático que construye y publica el sitio cuando haces *push*.

![Figura 1 — GitHub](assets/img/01-publicar/github.png)
**Figura 1:** Página principal de GitHub.

---

## 2) Crear tu proyecto en GitHub

Vas a partir del repo plantilla (este repositorio).

[Github de este repositorio](https://github.com/HuberGiron/portafolio-just-the-docs)

### Ruta A (recomendada): Fork del repositorio

1. Abre el repositorio a copiar en GitHub.
2. Clic en **Fork**.
3. Configura:
   - **Owner**: tu usuario (o la organización de tu equipo)
   - **Repository name**: por ejemplo `documentacion-equipo-3`
4. Clic en **Create fork**.

![Figura 2 — Fork](assets/img/01-publicar/fork.png)
**Figura 2:** Botón *Fork* y pantalla de creación.

> Ventaja: no necesitas “subir archivos” manualmente; ya tienes el proyecto completo en tu cuenta.

### Ruta B (alternativa): Crear un repo nuevo y subir los archivos

Úsala solo si se necesita “crear repo desde cero”.

1. Abre GitHub → **New repository**.
2. Nombre: `documentacion-equipo-3`.
3. Crea el repo.
4. Descarga el repo en tu computadora:
   - **Code → Download ZIP** (o descarga el `.zip` que te entregó el profesor).
5. Sube el contenido a tu repo:
   - **Add file → Upload files**
   - Arrastra los archivos (descomprimidos) a la ventana
   - Clic en **Commit changes**


![Figura 3 — Download ZIP + Upload files](assets/img/01-publicar/download.png)
**Figura 3:** Descargar ZIP.

![Figura 4 — New repo](assets/img/01-publicar/nuevo.png)
![Figura — New ](assets/img/01-publicar/new.png)
![Figura  — exixting](assets/img/01-publicar/upload.png)
![Figura  — upload](assets/img/01-publicar/files.png)
**Figura 4:** Crear repositorio nuevo.

---

## 3) Abrir el proyecto con Codespaces (sin instalar nada)

1. En tu repo (tu fork o tu repo nuevo):
   - Clic en **Code → Codespaces → Create codespace on main**
2. Se abre un VS Code en el navegador.

![Figura 5 — Codespaces](assets/img/01-publicar/codespace.png)
**Figura 5:** Crear Codespace.

> Nota: Codespaces puede tardar 1–3 minutos en iniciar la primera vez.

---

## 4) Configurar `_config.yml` para que funcione tu URL

En el explorador de archivos abre `_config.yml` y ajusta **solo**:

```yml
url: "https://TU_USUARIO.github.io"
baseurl: "/TU_REPO"
```

Ejemplo típico:
- Usuario: `ana-ibero`
- Repo: `documentacion-equipo-3`

Entonces:

```yml
url: "https://ana-ibero.github.io"
baseurl: "/documentacion-equipo-3"
```

![Figura 6 — Edit config](assets/img/01-publicar/config.png)
**Figura 6:** Editando `_config.yml` en Codespaces.

> Si `baseurl` no coincide con el nombre del repo, los links y estilos suelen “romperse”.

---

## 5) Hacer tu primer cambio (commit) y subirlo (push)

En Codespaces:

1. Modifica un archivo sencillo, por ejemplo `index.md`.
2. Ve a la pestaña **Source Control** (ícono de rama).
3. En **Message**, escribe un mensaje de commit, por ejemplo:
   - `Actualiza portada`
4. Clic en **Commit**.
5. Clic en **Sync Changes** (o **Push**).

![Figura 7 — Commit y Push](assets/img/01-publicar/commit.png)
**Figura 7:** Source Control → Commit → Sync Changes.

### ¿Qué pasó en realidad?

Cuando haces **push**:
1. Tus archivos se guardan en GitHub.
2. Se dispara un **pipeline (GitHub Actions)**.
3. GitHub construye el sitio (Jekyll + Just the Docs).
4. GitHub publica la versión nueva en **GitHub Pages**.

---

## 6) Activar GitHub Pages y obtener tu URL

En tu repositorio (en GitHub, no en Codespaces):

1. **Settings → Pages**
2. En **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: `main`
   - Folder: `/ (root)`
3. Guarda.

GitHub te mostrará tu URL con este formato:

- `https://TU_USUARIO.github.io/TU_REPO/`

![Figura  — Pages ](assets/img/01-publicar/pages.png)
![Figura 8 — Pages settings](assets/img/01-publicar/website.png)
**Figura 8:** Settings → Pages (branch y folder).

---

## 7) Verificar que el sitio ya está publicado

### Verificación rápida (lo mínimo)

1. En el repo, abre la pestaña **Actions**.
2. Busca el workflow que dice algo como **pages build and deployment**.
3. Espera a que salga en **verde (success)**.
4. Regresa a **Settings → Pages** y abre la URL.

![Figura 9 — Actions success](assets/img/01-publicar/actions.png)
**Figura 9:** Actions con ejecución exitosa.


### Señales típicas

- Si **Actions** sigue corriendo: espera (es normal).
- Si falla (rojo): abre el job y lee el error (a veces es un YAML mal indentado o un archivo faltante).

---

## Checklist 

- [ ] Hacer **commit** y **push** (desde Codespaces).
- [ ] Ajustaste `url` y `baseurl` en `_config.yml`.
- [ ] Activaste **Settings → Pages** con `main` y `/ (root)`.
- [ ] En **Actions** la ejecución está en verde.
- [ ] Tu URL abre y el menú lateral aparece.

---

## Siguiente sección
[Estructura del repositorio ](02-estructura-del-repo.md)