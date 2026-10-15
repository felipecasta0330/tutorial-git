# Tutorial de Git basado en *Pro Git*

**Autor:** Juan Felipe Castañeda Rodríguez
**Curso:** Ciencia de Datos — Actividad 2: *Hands on*, configuración de herramientas
**Institución:** Fundación Universitaria Agraria de Colombia (UNIAGRARIA)
**Fecha:** octubre de 2026

---

## 1. Descripción

Este repositorio contiene un tutorial de Git dividido en **10 capítulos**, uno por cada capítulo del libro oficial [*Pro Git*](https://git-scm.com/book/es/v2) (Chacon & Straub). Cada capítulo se redactó en un documento de Microsoft Word independiente, se exportó a PDF y se acompaña de un archivo `.txt` con las notas de comandos del capítulo.

El objetivo de la actividad es practicar el flujo básico de Git (`clone` → `add` → `commit` → `push`) con mensajes de confirmación claros, haciendo un *push* al repositorio remoto cada vez que se termina un capítulo.

## 2. Estructura del repositorio

```
tutorial-git/
├── README.md               ← este archivo (documentación del proceso)
├── .gitignore              ← archivos temporales que Git no debe rastrear
├── bitacora_cambios.txt    ← registro de cada cambio realizado
├── word/                   ← capítulos en Word (.docx)
├── pdf/                    ← capítulos exportados a PDF
└── notas/                  ← notas de comandos por capítulo (.txt)
```

## 3. Contenido del tutorial

| # | Capítulo | Word | PDF | Notas |
|---|----------|------|-----|-------|
| 1 | Inicio: sobre el control de versiones | [docx](word/Cap01_Inicio.docx) | [pdf](pdf/Cap01_Inicio.pdf) | [txt](notas/Cap01_Inicio_comandos.txt) |
| 2 | Fundamentos de Git | [docx](word/Cap02_Fundamentos.docx) | [pdf](pdf/Cap02_Fundamentos.pdf) | [txt](notas/Cap02_Fundamentos_comandos.txt) |
| 3 | Ramificaciones en Git | [docx](word/Cap03_Ramificaciones.docx) | [pdf](pdf/Cap03_Ramificaciones.pdf) | [txt](notas/Cap03_Ramificaciones_comandos.txt) |
| 4 | Git en el servidor | [docx](word/Cap04_Git_en_el_servidor.docx) | [pdf](pdf/Cap04_Git_en_el_servidor.pdf) | [txt](notas/Cap04_Git_en_el_servidor_comandos.txt) |
| 5 | Git en entornos distribuidos | [docx](word/Cap05_Git_distribuido.docx) | [pdf](pdf/Cap05_Git_distribuido.pdf) | [txt](notas/Cap05_Git_distribuido_comandos.txt) |
| 6 | GitHub | [docx](word/Cap06_GitHub.docx) | [pdf](pdf/Cap06_GitHub.pdf) | [txt](notas/Cap06_GitHub_comandos.txt) |
| 7 | Herramientas de Git | [docx](word/Cap07_Herramientas.docx) | [pdf](pdf/Cap07_Herramientas.pdf) | [txt](notas/Cap07_Herramientas_comandos.txt) |
| 8 | Personalización de Git | [docx](word/Cap08_Personalizacion.docx) | [pdf](pdf/Cap08_Personalizacion.pdf) | [txt](notas/Cap08_Personalizacion_comandos.txt) |
| 9 | Git y otros sistemas | [docx](word/Cap09_Git_y_otros_sistemas.docx) | [pdf](pdf/Cap09_Git_y_otros_sistemas.pdf) | [txt](notas/Cap09_Git_y_otros_sistemas_comandos.txt) |
| 10 | Los entresijos internos de Git | [docx](word/Cap10_Internos_de_Git.docx) | [pdf](pdf/Cap10_Internos_de_Git.pdf) | [txt](notas/Cap10_Internos_de_Git_comandos.txt) |

## 4. Proceso seguido

### Paso 1 — Crear la cuenta en GitHub
Registro en [github.com](https://github.com) con correo institucional/personal y verificación del correo.

### Paso 2 — Instalar y configurar Git
Se descargó Git desde [git-scm.com](https://git-scm.com/downloads) y se verificó la instalación. Luego se configuró la identidad que aparece en cada commit:

```bash
git --version
git config --global user.name "Juan Felipe Castañeda Rodríguez"
git config --global user.email "felipecasta0330@gmail.com"
git config --global init.defaultBranch main
git config --list
```

### Paso 3 — Crear el repositorio en GitHub
Desde **New repository** se creó el repositorio público `tutorial-git`, inicializado con un README.

### Paso 4 — Clonar el repositorio
```bash
git clone https://github.com/felipecasta0330/tutorial-git.git
cd tutorial-git
```

### Paso 5 — Estructura inicial
Se crearon las carpetas `word/`, `pdf/` y `notas/`, el `.gitignore` y la `bitacora_cambios.txt`:

```bash
git add .
git commit -m "Crea estructura inicial, .gitignore y bitácora de cambios"
git push origin main
```

### Paso 6 — Un capítulo a la vez (add → commit → push)
Por cada capítulo se redactó el documento en Word siguiendo *Pro Git*, se exportó a PDF, se generaron sus notas `.txt` y se registró el cambio en la bitácora. Después:

```bash
git status
git add word/Cap01_Inicio.docx pdf/Cap01_Inicio.pdf notas/Cap01_Inicio_comandos.txt bitacora_cambios.txt
git commit -m "Agrega capítulo 1: inicio y control de versiones"
git push origin main
```

Se repitió el ciclo para los capítulos 2 a 10, con un *push* al terminar cada uno.

### Paso 7 — Modificaciones y correcciones
Se hicieron cambios sobre archivos ya confirmados (por ejemplo, ampliar las notas de un capítulo y actualizar la bitácora) para practicar el registro de modificaciones con `git diff` y nuevos commits.

### Paso 8 — Documentar el proceso
Se completó este README con todo el proceso y se subió con un último commit.

## 5. Mensajes de commit usados

Convención: verbo en **imperativo** + qué se hizo, en una línea corta.

| # | Mensaje |
|---|---------|
| 1 | `Crea estructura inicial, .gitignore y bitácora de cambios` |
| 2 | `Agrega capítulo 1: inicio y control de versiones` |
| 3 | `Agrega capítulo 2: fundamentos de Git` |
| 4 | `Agrega capítulo 3: ramificaciones en Git` |
| 5 | `Agrega capítulo 4: Git en el servidor` |
| 6 | `Agrega capítulo 5: Git en entornos distribuidos` |
| 7 | `Agrega capítulo 6: GitHub` |
| 8 | `Agrega capítulo 7: herramientas de Git` |
| 9 | `Agrega capítulo 8: personalización de Git` |
| 10 | `Agrega capítulo 9: Git y otros sistemas` |
| 11 | `Agrega capítulo 10: entresijos internos de Git` |
| 12 | `Amplía notas del capítulo 2 con comandos de log y etiquetas` |
| 13 | `Documenta el proceso completo en el README` |

El historial real puede verse con:

```bash
git log --oneline --graph
```

## 6. Comandos de Git utilizados

| Comando | Para qué se usó |
|---------|-----------------|
| `git config` | Configurar nombre, correo y rama por defecto |
| `git clone` | Copiar el repositorio de GitHub al computador |
| `git status` | Revisar qué archivos cambiaron antes de cada commit |
| `git diff` | Ver las modificaciones hechas en los `.txt` |
| `git add` | Preparar los archivos de cada capítulo |
| `git commit -m` | Confirmar los cambios con un mensaje descriptivo |
| `git push` | Enviar cada capítulo terminado a GitHub |
| `git log` | Consultar el historial de commits |

## 7. Referencias

- Chacon, S., & Straub, B. (2014). *Pro Git* (2.ª ed.). Apress. https://git-scm.com/book/es/v2
- GitHub, Inc. (2019). *GitHub Guides*. https://guides.github.com/
- Hutch Data Science. (s. f.). *Using GitHub in a workflow*. https://hutchdatascience.org/Tools_for_Reproducible_Workflows_in_R/using-github-in-a-workflow.html
