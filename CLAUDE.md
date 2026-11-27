# LM apunteak

Apuntes de clase de LM (Lenguajes de Marcas y Sistemas de Gestión de Información) en MkDocs Material.

## Forma de trabajar
- Trabajo desde dos ordenadores (casa y trabajo). Al empezar: `git pull`. Al terminar: commit + `git push`. Nunca dejar cambios sin subir.
- Contenido bilingüe con `mkdocs-static-i18n`: `docs/es/` (idioma por defecto) y `docs/eu/`. Cada cambio de contenido se hace en las dos versiones.
- Mensajes de commit en euskera, cortos (p. ej. "Responsive eu eta es").

## Estructura y herramientas
- `site/` está en `.gitignore`: no se commitea. Al hacer push a `main`, la Action `.github/workflows/deploy.yml` publica en GitHub Pages.
- Previsualizar con `mkdocs serve` (`pip install -r requirements.txt`).
