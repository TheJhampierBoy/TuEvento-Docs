# Tu Evento — Documentation

Documentation repository for the training project **Tu Evento**, developed as part of the **Technologist in Software Analysis and Development** (ADSO) program at SENA, Sede de la Industria y los Servicios — Neiva, Huila.

**Tu Evento** is an event management solution made up of a web app and a mobile app. It allows managing users, events, seat selection and ticket sales, with S3-compatible file storage.

- **Code repository:** [github.com/lozano2303/TuEvento](https://github.com/lozano2303/TuEvento)

## Cohort (Ficha) and members

- **Ficha:** 3145556 (2026)
- **Team:** CapySoft
- **Members:**
  - Jhampier Santos Ortiz
  - Cristofer David Lozano Contreras

## Repository structure

The documentation is written in Markdown and published in two languages. Every file has the same relative path in `es/` and `en/`.

| Path | Content |
|---|---|
| `es/` | Documentation in Spanish |
| `en/` | Documentation in English (translation of `es/`) |
| `_assets/` | Images used by the Markdown documents |
| `MANIFEST.csv` | Inventory of the documents: original file, Markdown path in each language and status |
| `GLOSARIO_ES_EN.md` | Spanish–English glossary used in the translations |
| `REGLAS_CONVERSION.md` | Rules followed to convert the original documents to Markdown |
| `Registro_de_Contradicciones.md` | Contradictions found between documents and the code, and their resolution |

Inside `es/` and `en/` (structure requested by the instructor):

| Path | Content |
|---|---|
| `01_Documento_General_Proyecto.md` | Project scope, methodology, Scrum planning, business document and cost analysis |
| `02_Especificacion_Requisitos.md` | SRS, user stories, requirements confirmation and acceptance, data collection and technology watch |
| `03_Analisis_Software.md` | Software analysis, requirements, risk matrix, use cases, class, state and sequence diagrams |
| `04_Propuesta_Tecnica.md` | Technical proposal and technical sheet |
| `05_Diseno_Software.md` | Design patterns, architecture, package, process, flow and activity diagrams, checklist |
| `06_Base_Datos/` | `Modelo_ER.md` (ERD and per-module ERMs), `Diccionario_Datos.md` (draft generated from the implemented schema), `Script_BD.sql` (design) and `Script_BD_implementado.sql` (implemented schema) |
| `07_Pruebas/` | `Plan_Pruebas.md` and `Evidencias/` (test cases, backend and mobile tests) |
| `08_Calidad_Mejoras.md` | Software quality and corrective, preventive and improvement actions |
| `09_Implementacion.md` | Implementation manual |
| `10_Manual_Tecnico.md` | Technical manual |
| `11_Manual_Instalacion.md` | Installation manual |
| `12_Manual_Usuario.md` | Web and mobile user manuals |
| `13_Articulo_Proyecto.md` | Project article |
| `14_Anexos/` | Traceability matrix, distribution of responsibilities, evidence links, terms and conditions, prototype |
| `15_Enlace_Repositorio_GitHub.txt` | Link to the code repository |

The consolidated files (`01`–`05`, `08`–`10`, `12`, `13`) gather several documents without changing their content. Images of the original files are in `_assets/originales/`.

> The original files (PDF, DOCX and XLSX) were replaced by their Markdown versions. They remain available in the Git history up to commit `cd046e3`, and `MANIFEST.csv` records the original path of each one.

---

# Tu Evento — Documentación

Repositorio de documentación del proyecto formativo **Tu Evento**, desarrollado en el marco del programa **Tecnólogo en Análisis y Desarrollo de Software** (ADSO) del SENA, Sede de la Industria y los Servicios — Neiva, Huila.

**Tu Evento** es una solución de gestión de eventos compuesta por una aplicación web y una móvil. Permite administrar usuarios, eventos, selección de asientos y venta de boletas, con almacenamiento de archivos compatible con S3.

- **Repositorio de código:** [github.com/lozano2303/TuEvento](https://github.com/lozano2303/TuEvento)

## Ficha e integrantes

- **Ficha:** 3145556 (2026)
- **Equipo:** CapySoft
- **Integrantes:**
  - Jhampier Santos Ortiz
  - Cristofer David Lozano Contreras

## Estructura del repositorio

La documentación está escrita en Markdown y se publica en dos idiomas. Cada archivo tiene la misma ruta relativa en `es/` y en `en/`.

| Ruta | Contenido |
|---|---|
| `es/` | Documentación en español |
| `en/` | Documentación en inglés (traducción de `es/`) |
| `_assets/` | Imágenes que usan los documentos Markdown |
| `MANIFEST.csv` | Inventario de los documentos: archivo original, ruta del Markdown en cada idioma y estado |
| `GLOSARIO_ES_EN.md` | Glosario español–inglés usado en las traducciones |
| `REGLAS_CONVERSION.md` | Reglas seguidas para convertir los documentos originales a Markdown |
| `Registro_de_Contradicciones.md` | Contradicciones detectadas entre los documentos y el código, y su resolución |

Dentro de `es/` y `en/` (estructura pedida por el instructor):

| Ruta | Contenido |
|---|---|
| `01_Documento_General_Proyecto.md` | Alcance, metodología, planificación Scrum, documento empresarial y análisis de costos |
| `02_Especificacion_Requisitos.md` | SRS, historias de usuario, confirmación y aceptación de requisitos, recolección de datos y vigilancia tecnológica |
| `03_Analisis_Software.md` | Análisis del software, requisitos, matriz de riesgos, casos de uso y diagramas de clases, estados y secuencia |
| `04_Propuesta_Tecnica.md` | Propuesta técnica y ficha técnica |
| `05_Diseno_Software.md` | Patrones de diseño, diagramas de arquitectura, paquetes, procesos, flujo y actividades, lista de chequeo |
| `06_Base_Datos/` | `Modelo_ER.md` (DER y MER por módulo), `Diccionario_Datos.md` (borrador generado del esquema implementado), `Script_BD.sql` (diseño) y `Script_BD_implementado.sql` (esquema implementado) |
| `07_Pruebas/` | `Plan_Pruebas.md` y `Evidencias/` (casos de prueba, pruebas del backend y de la app móvil) |
| `08_Calidad_Mejoras.md` | Calidad de software y acciones correctivas, preventivas y de mejora |
| `09_Implementacion.md` | Manual de implementación |
| `10_Manual_Tecnico.md` | Manual técnico |
| `11_Manual_Instalacion.md` | Manual de instalación |
| `12_Manual_Usuario.md` | Manuales de usuario web y móvil |
| `13_Articulo_Proyecto.md` | Artículo del proyecto |
| `14_Anexos/` | Matriz de trazabilidad, distribución de responsabilidades, enlaces de evidencias, términos y condiciones, prototipo |
| `15_Enlace_Repositorio_GitHub.txt` | Enlace al repositorio de código |

Los archivos consolidados (`01`–`05`, `08`–`10`, `12`, `13`) reúnen varios documentos sin cambiar su contenido. Las imágenes de los archivos originales están en `_assets/originales/`.

> Los archivos originales (PDF, DOCX y XLSX) se reemplazaron por sus versiones en Markdown. Siguen disponibles en el historial de Git hasta el commit `cd046e3`, y `MANIFEST.csv` registra la ruta original de cada uno.
