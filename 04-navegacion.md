---
layout: default
title: Navegación y menús
nav_order: 5
---

# Navegación y menús

## Orden básico

El orden en la barra lateral depende de `nav_order`:

```yml
---
title: Mi página
nav_order: 7
---
```

---

## Secciones con páginas hijas

Crea una página “padre”:

```yml
---
title: Unidad 1
nav_order: 10
has_children: true
---
```

Luego, en cada página hija:

```yml
---
title: 1.1 Introducción
parent: Unidad 1
nav_order: 1
---
```

---

## Ocultar páginas del menú

Para páginas “legales” o de política:

```yml
nav_exclude: true
```

Este repo incluye una página ejemplo “Uso de IA” oculta del menú.
