# Apuntes de Lenguaje de Marcas

Apuntes personales del módulo de Lenguaje de Marcas, construidos con
[MkDocs](https://www.mkdocs.org/) y el tema
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Desarrollo local

```bash
python -m venv .venv
.venv\Scripts\activate      # Windows
pip install -r requirements.txt
mkdocs serve
```

Abre <http://127.0.0.1:8000> para ver los cambios en vivo.

## Estructura

```
docs/
├── index.md
├── 01-introduccion/
├── 02-html/
├── 03-css/
├── 04-xml/
├── 05-xslt/
└── 06-javascript/
```

## Publicación

Al hacer `push` a `main`, el workflow de GitHub Actions
(`.github/workflows/deploy.yml`) construye el sitio y lo publica en la rama
`gh-pages`. Actívalo en **Settings → Pages → Source: Deploy from a branch →
gh-pages**.
