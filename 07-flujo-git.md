---
layout: default
title: Flujo de trabajo con Git
nav_order: 8
---

# Flujo de trabajo con Git (para alumnos)

## Forma 1 (simple): clonar y trabajar en el mismo repo

1. Clona:

```bash
git clone https://github.com/TU_USUARIO/TU_REPO.git
cd TU_REPO
```

2. Crea una rama:

```bash
git checkout -b docs/mi-aporte
```

3. Edita/crea páginas `.md`.
4. Commit + push:

```bash
git add .
git commit -m "Agrega sección de X"
git push -u origin docs/mi-aporte
```

5. Abre un Pull Request.

---

## Forma 2 (común en clase): fork + pull request

1. Haz **Fork** del repo del docente.
2. Clona tu fork.
3. Trabaja en rama.
4. Pull Request hacia el repo original.

---

## Reglas prácticas para documentación

- Un cambio = un commit (idealmente).
- Imágenes siempre en `assets/img/`.
- No subas archivos gigantes (video crudo). Enlaza a YouTube/Drive.
- Revisa los links antes de entregar.
