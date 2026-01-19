---
layout: default
title: Escribir en Markdown
nav_order: 4
---

# Escribir en Markdown

Markdown es el formato principal para escribir contenido en tu sitio (Just the Docs). La idea es que puedas crear páginas claras y consistentes, sin depender de Word ni formatos complicados.

---

## 1) Encabezados (títulos)

Código:

```md
# Título de la página (H1)
## Sección (H2)
### Subsección (H3)
```

Ejemplo (cómo se ve):

**Título de la página (H1)**  
**Sección (H2)**  
**Subsección (H3)**

- En cada página usa **un solo H1** (el título de la página).
- Dentro del contenido usa **H2 para secciones** y **H3 para subsecciones**.
- Mantén frases cortas y listas para pasos o requerimientos.


---

## 2) Negritas, cursivas y texto en línea

Código:

```md
**negrita**
*cursiva*
`codigo en linea`
```

Ejemplos (cómo se ve):
- **Entrega final** el viernes.
- *Entrega final* el viernes.
- Usa `git status` para ver cambios.

---

## 3) Listas (viñetas, numeradas y tareas)

### Viñetas

Código:

```md
- Punto 1
- Punto 2
  - Subpunto 2.1
```

Ejemplo (cómo se ve):
- Punto 1
- Punto 2
  - Subpunto 2.1

### Numeradas (pasos)

Código:

```md
1. Abre Codespaces
2. Edita el archivo
3. Haz commit
4. Haz push
```

Ejemplo (cómo se ve):
1. Abre Codespaces
2. Edita el archivo
3. Haz commit
4. Haz push

### Checklists (útiles para entregas)

Código:

```md
- [ ] Agregué portada (index.md)
- [ ] Publiqué en GitHub Pages
- [ ] Verifiqué Actions en verde
```

Ejemplo (cómo se ve):
- [ ] Agregué portada (index.md)
- [ ] Publiqué en GitHub Pages
- [ ] Verifiqué Actions en verde

---

## 4) Enlaces (a páginas, secciones, archivos y web)

### Enlace a otra página del sitio

Código:

```md
[Ir a Estructura del repositorio](02-estructura-del-repo.md)
```

Ejemplo (cómo se ve):  
[Ir a Estructura del repositorio](02-estructura-del-repo.md)

### Enlace a una sección dentro de la misma página (ancla)

Primero, crea un encabezado:

```md
## Mi Seccion Importante
```

Luego enlaza así:

```md
[Ir a Mi Seccion Importante](#mi-seccion-importante)
```

Ejemplo (cómo se ve):  
[Ir a Mi Seccion Importante](#mi-seccion-importante)

> Nota: los espacios se convierten en guiones y todo queda en minúsculas.

### Enlace a un archivo (PDF, ZIP, etc.)

Guarda el archivo en `assets/files/` y enlaza así:

```md
[Descargar hoja de datos](assets/files/calendario.pdf)
```

Ejemplo (cómo se ve):  
[Descargar hoja de datos](assets/files/calendario.pdf)

### Enlace externo

Código:

```md
[GitHub](https://github.com)
```

Ejemplo (cómo se ve):  
[GitHub](https://github.com)

---

## 5) Imágenes (y buenas prácticas de rutas)

Guarda imágenes en `assets/img/`.

Código:

```md
![Diagrama del sistema](assets/img/diagrama-sistema.png)
```

Ejemplo (cómo se ve):  
(El ejemplo renderiza cuando la imagen existe en esa ruta)

<!-- Ejemplo sugerido usando un archivo que normalmente ya existe en la plantilla -->
![Ejemplo (logo)](assets/img/logotipo.png)

Buenas prácticas:
- Usa nombres consistentes: `fig15-...`, `diagrama-...`, `captura-...`
- Evita espacios y acentos en nombres de archivo.
- Respeta mayúsculas/minúsculas (en web sí importa).

---

## 6) Video (opciones recomendadas)

### Opción A: Enlace

Ideal para no romper el diseño.

Código:

```md
[Ver video de demostración (YouTube)](https://www.youtube.com/watch?v=ID_DEL_VIDEO)
```

Ejemplo (cómo se ve):  
[Ver video de demostración (YouTube)](https://www.youtube.com/watch?v=6om9bh6pz_s)

### Opción B: Embed

Puedes incrustar un video con HTML. Úsalo con moderación.

Código:

```html
<iframe width="560" height="315" src="https://www.youtube.com/watch?v=ID_DEL_VIDEO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

Ejemplo (cómo se ve):

<iframe width="560" height="315" src="https://www.youtube.com/embed/6om9bh6pz_s?si=vGGN_nxT5MHCHusO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>

### Opción C: Video MP4 (archivo local en tu repositorio)

1) Guarda tu video en una carpeta del repo, por ejemplo:
- `assets/videos/` (recomendado para mantener orden), o
- `assets/img/` (si ya estás usando esa ruta en tu curso)

2) Inserta el video con HTML:

Código:

```html
<video controls width="720">
  <source src="{{ '/assets/videos/demo.mp4' | relative_url }}" type="video/mp4">
  Tu navegador no soporta video HTML5.
</video>
```

Ejemplo (cómo se ve):  
(Solo renderiza cuando exista `assets/videos/demo.mp4` en tu repo)

<video controls width="720">
  <source src="{{ '/assets/videos/demo.mp4' | relative_url }}" type="video/mp4">
  Tu navegador no soporta video HTML5.
</video>

Recomendaciones:
- Mantén los MP4 **ligeros** (clips cortos). Archivos muy grandes hacen el repo pesado y lento de descargar.
- Usa nombres simples: `demo-robot.mp4`, `calibracion-01.mp4`.

---

## 7) Código (bloques con resaltado y fragmentos)

### Bloque con resaltado

Código:

````md
```python
print("hola")
```
````

Ejemplo (cómo se ve):

```python
print("hola")
```

### Bloque sin lenguaje (texto plano)

Código:

````md
```text
git status
git add .
git commit -m "mensaje"
git push
```
````

Ejemplo (cómo se ve):

```text
git status
git add .
git commit -m "mensaje"
git push
```

### Código en línea

Código:

```md
Usa `git status` para ver cambios.
```

Ejemplo (cómo se ve):  
Usa `git status` para ver cambios.

---

## 8) Tablas

Código:

```md
| Campo | Tipo | Ejemplo |
|------:|:----:|:--------|
| RAM   | GB   | 8       |
| CPU   | x86  | i5      |
```

Ejemplo (cómo se ve):

| Campo | Tipo | Ejemplo |
|------:|:----:|:--------|
| RAM   | GB   | 8       |
| CPU   | x86  | i5      |

Buenas prácticas:
- No abuses de tablas anchas (en móvil se vuelven incómodas).
- Si la tabla se vuelve enorme, considera dividir en 2 o pasar a lista.

---

## 9) Citas y separadores

### Cita (blockquote)

Código:

```md
> Esto es una cita o nota rápida.
```

Ejemplo (cómo se ve):

> Esto es una cita o nota rápida.

### Separador

Código:

```md
---
```

Ejemplo (cómo se ve):

---


---

## 10) Bloques colapsables 

Puedes usar HTML nativo.

Código:

```html
<details>
  <summary>Ver solución</summary>

  Aquí va la explicación o solución paso a paso.
</details>
```

Ejemplo (cómo se ve):

<details>
  <summary>Ver solución</summary>

  Aquí va la explicación o solución paso a paso.
</details>

---

## 11) Plantilla rápida para una página del curso

Copia y adapta.

Código (front matter):

```yml
---
layout: default
title: Titulo de mi pagina
nav_order: 50
---
```

Ejemplo (cómo se vería al inicio de un archivo `mi-pagina.md`):

```yml
---
layout: default
title: Mi pagina de ejemplo
nav_order: 50
---
```

Y debajo, tu contenido:

```md
## Objetivo
- Explicar un concepto de forma clara.

## Materiales
- 1 imagen
- 1 enlace
- 1 PDF

## Pasos
1. Paso 1
2. Paso 2

## Evidencia
- Foto / captura / enlace
```

---

## Siguiente sección

[Estilos y personalización visual](04-estilos.md)
