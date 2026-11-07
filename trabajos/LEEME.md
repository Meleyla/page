# Tres trabajos en R: Tarpuy, inti y página de reanálisis

| Carpeta | Trabajo | Archivo principal |
|---|---|---|
| `01_tarpuy_libro_campo` | Diseño experimental y libro de campo (quinua × salinidad) | `tarpuy_libro_campo.qmd` |
| `02_inti_analisis` | ANOVA, comparación de medias y heredabilidad (papa × sequía) | `inti_analisis.qmd` |
| `03_pagina_reanalisis` | Página web Quarto: reanálisis de virus en camote | `index.qmd`, `datos.qmd`, `reanalisis.qmd` |

## 1. Instalar paquetes (una sola vez)

En la consola de RStudio:

```r
install.packages(c("remotes", "tidyverse", "writexl", "agricolae",
                   "multcomp", "broom", "cowplot", "car", "knitr", "rmarkdown"))

remotes::install_github("flavjack/inti")
```

`inti` se instala desde GitHub porque los trabajos usan su versión más reciente. Si en algún momento te pide actualizar otros paquetes, elige **1 (All)**.

## 2. Abrir y renderizar cada trabajo

1. Haz doble clic en el archivo `.Rproj` de la carpeta (por ejemplo `02_inti_analisis.Rproj`). Así RStudio abre con la carpeta correcta.
2. Abre el `.qmd`.
3. Pulsa **Render**. RStudio ya trae Quarto, no hay que instalar nada más.

Resultados:

- **Tarpuy**: `tarpuy_libro_campo.html` y la carpeta `salidas/` con el libro de campo en Excel y el croquis en PNG.
- **inti**: `inti_analisis.html`.
- **Página**: en la carpeta `03_pagina_reanalisis` usa la pestaña **Build → Render Website**. La web queda en la carpeta `docs/`.

## 3. Publicar la página en GitHub Pages

1. En github.com crea un repositorio **público** llamado `reanalisis-camote`, sin README.
2. En la Terminal de la Mac:

```bash
cd ruta/a/03_pagina_reanalisis      # arrastra la carpeta a la Terminal para pegar la ruta
git init
git add .
git commit -m "Página de reanálisis de virus en camote"
git branch -M main
git remote add origin https://github.com/bryanchavez03/reanalisis-camote.git
git push -u origin main
```

3. En GitHub: **Settings → Pages → Branch: `main`, carpeta `/docs` → Save**.
4. En 1–2 minutos la página estará en:
   `https://bryanchavez03.github.io/reanalisis-camote/`

Si cambias algo: **Render Website** y luego `git add . && git commit -m "actualización" && git push`.

Si `git` pide instalar herramientas, acepta (son las de Apple). Si `git push` pide contraseña, GitHub ya no acepta la contraseña normal: usa un *token* (Settings → Developer settings → Personal access tokens) o instala GitHub Desktop.
