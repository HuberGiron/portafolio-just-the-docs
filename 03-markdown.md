---
layout: default
title: Escribir en Markdown
nav_order: 4
---

# Escribir en Markdown

## Encabezados

```md
# Título (H1)
## Sección (H2)
### Subsección (H3)
```

> Recomendación: usa **H2** como sección principal dentro de páginas; evita múltiples H1.

---

## Listas

```md
- Punto 1
- Punto 2
  - Subpunto

1. Paso 1
2. Paso 2
```

---

## Código

Bloque con resaltado:

````md
```python
print("hola")
```
````

Código en línea: `git status`.

---

## Tablas

```md
| Campo | Tipo | Ejemplo |
|------:|:----:|:--------|
| RAM   | GB   | 8       |
| CPU   | x86  | i5      |
```

---

## Callouts (notas, advertencias)

Just the Docs soporta callouts con clases.

```md
{: .note }
Nota: este es un recordatorio.

{: .warning }
Advertencia: cuidado con esto.
```

{: .note }
Nota: En algunos repos, estas clases ya vienen habilitadas por el tema.

{: .warning }
Advertencia: si tu instancia no muestra callouts, revisa que estés usando el tema Just the Docs.
