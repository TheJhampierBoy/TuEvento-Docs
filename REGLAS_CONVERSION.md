# Reglas de conversión a Markdown — Tu Evento

| Campo | Valor |
|---|---|
| Proyecto | Tu Evento — CapySoft |
| Repositorio | TuEvento-Docs |
| Fecha | 2026-10-23 |
| Versión | 1.6 (conversión masiva al español + representación de archivos no documentales) |
| Estado | Conversión al español **completada** (62 documentos en `md/es/`, todos en `borrador`, pendientes de revisión humana). v1.6: los 86 archivos no documentales (13 SQL, 4 accesos directos `.url`, 1 draw.io y 68 imágenes) están representados en 43 Markdown de `md/es/` (sección 5.3), en `borrador`; las imágenes **no** están transcritas. Traducción al inglés no iniciada |

> **Nota (2026-10-24).** Estas reglas describen la conversión tal como se hizo, con la estructura `md/es/` y `md/en/` y las carpetas `00_Informes` … `11_Anexos`. Después, el equipo eliminó los originales y reorganizó `es/` y `en/` en la raíz con la estructura pedida por el instructor (`01_Documento_General_Proyecto.md` … `15_Enlace_Repositorio_GitHub.txt`). La estructura vigente está en `README.md` y la correspondencia entre cada original y su ubicación actual, en `MANIFEST.csv`.

## 1. Alcance

Estas reglas definen cómo se convierten a Markdown los documentos originales de `TuEvento-Docs` (PDF, DOCX y XLSX), cómo se registran en el manifiesto y cómo se prepararán las futuras traducciones al inglés.

Principio rector: **ninguna conversión se declara completa si hay texto ilegible, tablas reconstruidas sin verificar o elementos que no se pudieron recuperar.** Toda pérdida se declara.

## 2. Estructura

```
TuEvento-Docs/
├── 00_Informes/ … 11_Anexos/      ← originales: no se modifican, mueven, renombran ni eliminan
└── md/
    ├── REGLAS_CONVERSION.md         ← este documento
    ├── MANIFEST.csv                 ← correspondencia original ↔ Markdown (fuente de verdad)
    ├── Registro_de_Contradicciones.md
    ├── _assets/<ruta-del-original-normalizada>/<Slug>/   ← imágenes extraídas (compartidas por es y en)
    ├── es/<carpeta numerada>/[<subcarpeta normalizada>/]<Slug>.md
    └── en/<carpeta numerada>/[<subcarpeta normalizada>/]<Slug>.md
```

- `md/es/` y `md/en/` replican las 12 carpetas numeradas (`00_Informes` … `11_Anexos`). Solo se replican las subcarpetas que contienen documentos convertibles.
- Los nombres de las carpetas **no se traducen** en `md/en/`. Un mismo documento tiene la misma ruta relativa en ambos idiomas.
- Las carpetas vacías llevan un `.gitkeep`, que se elimina cuando la carpeta reciba su primer Markdown.
- Los Markdown que ya existen (README, Consolidación de enlaces, Distribución de responsabilidades y los 14 MER) **se conservan en su sitio**. No se copian a `md/es/`; el manifiesto apunta a su ruta original.

## 3. Nombres de archivo (normalización)

El nombre del Markdown se deriva del original de forma determinista:

1. Se quitan las tildes y diacríticos (`Análisis` → `Analisis`).
2. Cada secuencia de caracteres que no sea letra ASCII o dígito se sustituye por `_`.
3. Se eliminan los `_` del principio y del final, y se conserva el uso de mayúsculas y minúsculas.
4. La extensión pasa a `.md`.

Ejemplo: `02_Analisis_Software/Análisis del Software-Tu evento.docx` → `md/es/02_Analisis_Software/Analisis_del_Software_Tu_evento.md`.

Las subcarpetas se normalizan igual (`Recoleccion de datos` → `Recoleccion_de_datos`). Las erratas de los nombres originales (`secuencie`, `Planificaion`, `Languaje`) **se mantienen** para conservar la trazabilidad; se anotan en el manifiesto.

## 4. Encabezado YAML de cada Markdown convertido

```yaml
---
id: TE-0000                      # mismo id que en MANIFEST.csv
title: "<título del documento original>"
lang: es                         # es | en
source: <ruta del original>
source_sha256: <hash del original en el momento de convertir>
conversion: "<herramienta y versión>; sin revisión manual | con revisión manual"
converted_on: AAAA-MM-DD
fidelity: completa | pendiente_revision | parcial | solo_imagen   # ver sección 6
losses:                          # obligatorio si fidelity ≠ completa
  - "<qué se perdió o no se verificó, con página, hoja o sección>"
status: borrador | revisado
reviewed_by: ""                  # se completa al revisar
# Solo en md/en/:
translation_of: md/es/<ruta>.md
es_sha256: <hash del Markdown en español traducido>
---
```

Excepción (v1.6): los índices de imágenes representan varios originales, así que en ellos `id`, `source` y `source_sha256` son listas paralelas, en el mismo orden (sección 5.3).

## 5. Métodos por formato

| Formato | Herramienta prevista | Reglas específicas |
|---|---|---|
| DOCX | `pandoc -t gfm --wrap=none --extract-media=<ruta relativa a _assets>` (se ejecuta desde la carpeta del Markdown para que los enlaces sean relativos) | Mantener la jerarquía de títulos. **Si el original no usa estilos de título** (p. ej. todo `NormalWeb`), pandoc no genera `#`: se marcan a mano y, mientras tanto, la fidelidad es `parcial`. **Encabezados y pies de página**: pandoc los ignora; se extraen aparte (texto e imágenes) a una sección final «Encabezados y pies de página del original». Las tablas con celdas combinadas se escriben como tabla HTML. Las imágenes se enlazan con texto alternativo. Las listas numeradas automáticas se comprueban contra el original. Se elimina el carácter BOM (`U+FEFF`). Los **campos** de encabezados y pies (`PAGE`, `NUMPAGES`) se escriben como `{PAGE}`, `{NUMPAGES}`, no con su valor guardado. **Índice manual** («Tabla de Contenido», «Índice»): se conserva su texto, incluidos los números de página del original, y se quita la cita (`>`) que pandoc genera por la sangría de las subentradas. Las tablas con listas o varios párrafos por celda quedan en HTML (pandoc). |
| PDF con texto **etiquetado** (`Tagged: yes` en `pdfinfo`, p. ej. exportado desde Word) | `pdfplumber`, recorriendo el **árbol de estructura** (`H1`–`H6`, `P`, `L`/`LI`/`Lbl`/`LBody`, `Table`/`TR`/`TD`) y uniendo los caracteres por `mcid` | Es el método preferente: conserva el orden lógico y las tablas que cruzan páginas como una sola. Títulos `Hn` → `#`×n. Listas: viñeta → `-`; numeración → se conserva la etiqueta original. Tablas GFM con la primera fila como encabezado y `<br>` entre párrafos de una celda. Se omiten el texto sin etiquetar (pies y números de página) y las **filas de encabezado repetidas** por salto de página, y ambos se anotan en `losses`. Se escapan `<` y `>` (`&lt;`, `&gt;`), porque GFM los ocultaría como etiquetas HTML. No se conservan negritas, cursivas ni fuente monoespaciada. |
| PDF con texto **sin etiquetar** (LaTeX/pdfTeX, ReportLab, LibreOffice + pypdf) | Conversor propio con `pdfplumber` (**método C**, piloto 3). Se descartaron `pdftotext -layout` (sin estructura; deja cabeceras, pies y guiones) y `pymupdf4llm` 2.0 (cuela la plantilla del SRS en cada página, **corta palabras entre columnas** de las fichas, deja 114 tildes de LaTeX sin componer, parte párrafos en cada línea y pone todos los títulos al mismo nivel) | **Plantilla**: se omiten las líneas en el 12 % superior o inferior repetidas en ≥ 40 % de páginas, los números de página sueltos (también si son la primera o la última línea), los cuadros de cabecera y los logos repetidos; se ignoran objetos fuera de la página. **Tildes de LaTeX** (glifo aparte): se recomponen salvo en fuente monoespaciada. **Guiones de corte**: se unen si siguen minúsculas y se listan en `losses`. **Títulos**: negrita de línea completa o tamaño ≥ 1,3 × cuerpo; nivel por numeración («3.1.1» → 3), y sin numeración por tamaño y alineación (centrado antes que izquierda); los de varias líneas se unen si mantienen alineación o sangría francesa; en la portada solo es título la línea de mayor tamaño. **Índice manual**: se conserva el texto y el número de página, sin líneas guía, y sin convertir en títulos. **Párrafos**: una línea continúa la anterior si esta llega al margen derecho y la nueva no tiene sangría. **Viñetas**: caracteres (`•`) o formas dibujadas cuadradas de ~3 pt a la izquierda de la línea, también dentro de celdas. **Código**: líneas monoespaciadas de cuerpo menor → bloque `text` con la columna original. **Tablas con bordes**: `find_tables` + HTML con `colspan`/`rowspan` calculados por la unión de bordes x; se unen entre páginas si la anterior acaba en el último 25 % y la siguiente empieza en el primer 25 % con los mismos bordes laterales, **salvo que la nueva parte empiece con la misma etiqueta** («Identificador:») que la anterior (registro nuevo); se omiten las filas de encabezado repetidas. **Cuadros de una sola celda** (cuatro bordes con texto, que `find_tables` no devuelve): se tratan como tabla de una celda para poder unirlos con la ficha anterior. **Tablas con solo líneas horizontales** (APA): tríos de líneas (arriba, bajo encabezado, abajo), columnas por el encabezado; **fila nueva cuando la distancia entre líneas supera 1,35 × el tamaño de letra** (las líneas partidas de una celda van a interlineado normal). **Palabras partidas por el ancho de la celda** (sin guion): se unen sin espacio si la línea anterior es una sola palabra que ocupa ≥ 85 % del ancho y la siguiente empieza por minúscula, dígito o `_`, salvo que empiece por una palabra funcional completa (o, y, e, u, a, de, del, en, el, la, los, las, con, por, para, sin); cada unión se lista en `losses`. **Figuras** (rectángulos o curvas grandes fuera de tablas, agrupados de forma iterativa con una distancia de 40 pt, e imágenes no repetidas): recorte a 200 ppp en `_assets` y su texto en un comentario HTML, agrupado por caja; fidelidad máxima `parcial`. Se escapan `< > * \``. **Memoria**: un PDF con muchos objetos (p. ej. el SRS, con unos 4500 rectángulos residuales por página) necesita unos 2 GB; se convierte un documento cada vez. |
| PDF sin texto (escaneado o imagen) | `pdftoppm -r 300` + `tesserocr` (tesseract 5, `tessdata_best` `spa+eng`). Modo `PSM 11` (texto disperso) para diagramas | Se incluye la imagen de cada página como referencia fiel. El texto del OCR va en un bloque `text` marcado con `<!-- OCR: revisar · confianza … -->`. Se descartan las líneas con menos de 2 letras (trazos leídos como `\|`, `©`). Las páginas totalmente blancas se indican como «en blanco», sin imagen. Fidelidad: `solo_imagen` mientras no haya una transcripción manual revisada. **En diagramas** (secuencia, procesos, flujo), el OCR es solo apoyo para búsquedas: la representación fiel requiere transcripción manual (por ejemplo, a Mermaid). |
| PDF de diseño (Canva) | `pdfplumber` + imagen de cada página | El texto se extrae en orden de lectura y se añade la imagen de la página. Fidelidad máxima: `parcial`. |
| XLSX | `openpyxl`, cargando el libro dos veces (`data_only=True` para valores y `False` para fórmulas) | Una sección `## Hoja: <nombre>` por hoja, con el rango usado. Tabla con columna `Fila` (número original) y columnas con la letra de Excel, sin inventar encabezados. Se omiten solo las filas totalmente vacías. Se aplican los formatos que cambian el significado: **porcentaje** (`0.0%`) y **fecha**. Debajo de cada hoja: celdas combinadas, paneles inmovilizados, autofiltro, **validaciones de datos** (con su lista) y **formato condicional** (regla, sin estilo), y una tabla con **cada fórmula** y su valor en caché. Los valores en caché no se recalculan. Las imágenes incrustadas se extraen a `_assets`. |

Los parámetros exactos y la versión de cada herramienta se registran en `conversion` del encabezado YAML.

### 5.1 Verificación automática por formato

| Formato | Comprobación |
|---|---|
| DOCX | (1) Texto de `word/document.xml` frente al Markdown (sin YAML, marcas ni etiquetas HTML) como cadena continua sin espacios: debe ser idéntico, lo que también comprueba el **orden**. (2) Títulos: misma secuencia de (nivel, texto) que los estilos `Título 1/2/3`. (3) Tablas: mismo número de tablas y de celdas por fila, en orden. (4) Elementos de lista: tantos como párrafos con numeración (`numPr`). |
| PDF etiquetado | (1) Texto fuera de tablas frente al **flujo de contenido** del PDF (orden independiente del árbol), como cadena continua: idéntico. (2) Texto de tablas: mismo conjunto de palabras; solo pueden faltar las filas de encabezado repetidas. (3) Títulos, tablas (celdas por fila) y elementos de lista frente al árbol de estructura. (4) Contraste con `pdftotext -raw` como indicador adicional (similitud ≥ 0,99). |
| XLSX | Se vuelve a leer cada tabla del Markdown y se compara **cada celda no vacía** con el valor formateado del XLSX; debe haber 0 diferencias. |
| PDF sin etiquetar | Referencia independiente `pdftotext -raw` (sin cabeceras ni pies detectados por posición): **cobertura y precisión de palabras** (multiconjunto) ≥ 98 %, **orden** (similitud de secuencias) ≥ 97 %; **índice del PDF** frente a los títulos (todas las entradas como título, en orden y con desfase de nivel constante); tablas frente a los títulos «Tabla N» o a los registros («Identificador:») y **ninguna tabla con dos registros**; viñetas dibujadas frente a las del Markdown; imágenes referenciadas existentes; 0 números de página, tildes sueltas o guiones de corte. Las palabras que falten deben explicarse en `losses` (p. ej. encabezados repetidos omitidos). **Por sección**: el original se divide por los títulos del Markdown (en línea propia, excluyendo las páginas de índice, que se comparan aparte) y cada sección debe coincidir en palabras. **Por tabla**: cada «Tabla N» seguida de su tabla con el mismo título; filas revisadas visualmente donde haya celdas de varias líneas (las palabras completas no garantizan que las filas estén bien separadas). **Por registro** (fichas): mismas etiquetas y palabras que el tramo del original. **Figuras**: revisión visual de que cada recorte contiene el diagrama completo. Artefactos conocidos de la referencia: `pdftotext` no compone «ı» + acento (se normaliza a «í») y su filtro de muebles descarta números que quedan solos en una línea. |
| PDF con OCR | Se transcriben a mano las etiquetas de una página de muestra y se mide qué proporción recupera el OCR; el resultado se anota en `losses`. |
| Todos | Se visualiza el Markdown como GFM (`pandoc -f gfm -t html`) y se comprueba que el número de tablas, títulos y elementos de lista coincide y que no hay citas ni etiquetas que oculten texto. |

### 5.2 Ajustes introducidos en la conversión masiva (v1.5)

- **DOCX con estilo Título (Title)**: pandoc lo pasa a metadatos y no lo escribe en GFM; se restituye a mano como `#` y se anota en `losses`. Los guiones escritos como texto al inicio de línea se escapan (`\-`).
- **XLSX**: las validaciones de datos con extensión `x14` (que openpyxl no carga) se leen del XML de la hoja; las imágenes incrustadas (`xl/media/`) se extraen a `_assets` con su celda de anclaje.
- **PDF sin etiquetar (método C)**:
  - las viñetas de ReportLab sin Unicode («(cid:127)») se escriben como «•»;
  - una viñeta nunca se trata como sub/superíndice;
  - las palabras de líneas distintas fusionadas llevan espacio;
  - los guiones de corte dentro de celdas se unen: en LaTeX, sin guion si sigue una minúscula; en otros productores (ReportLab), el guion se conserva porque es real;
  - las palabras partidas por carácter se unen si la palabra completa aparece en el documento con más frecuencia que el fragmento (p. ej. «gatewa» / «y»);
  - las tablas de ReportLab sin reglas verticales (banda oscura de encabezado y filas con regla horizontal) se reconstruyen como tabla, y las bandas de fondo con texto no son figuras;
  - las cajas de diagrama que pdfplumber toma por tablas de 1 fila se incluyen en la figura;
  - el hueco entre líneas se calcula por documento (interlineado doble APA), una línea continúa la anterior si su primera palabra no habría cabido en ella (margen derecho real, percentil 98), y dos líneas de título solo se unen si la primera ocupa al menos el 60 % del ancho.
- **PDF etiquetado de Word**: las imágenes no están en el árbol de estructura; se recortan del original a 200 ppp y se enlazan en su posición.
- **PDF de Canva**: sus caracteres no están enlazados al árbol de etiquetas. El texto se agrupa en cuadros (líneas cercanas que se solapan), con tolerancia proporcional al tamaño de letra (`x_tolerance_ratio=0.15`, por el espaciado entre letras). Se incluyen los caracteres que sobresalen del borde de la página y una imagen de cada página. La fidelidad es `parcial`.

Las comprobaciones se normalizan igual en ambos lados: se ignoran los espacios, los caracteres de marcado (`* _ \` # > | \`) y las viñetas (`• ● ○ ▪`). Por eso no detectan diferencias en esos caracteres, que se revisan a mano.

### 5.3 Representación de archivos no documentales (v1.6)

Los SQL, los accesos directos, el archivo de draw.io y las imágenes no son documentos y su contenido no se reinterpreta: se **representan** en Markdown para que todo el repositorio sea legible desde `md/es/`. El original sigue siendo la fuente; el Markdown lo enlaza con una ruta relativa codificada para URL (espacios como `%20`). La ruta se deriva con las reglas de la sección 3.

| Tipo | Destino | Representación | Fidelidad |
|---|---|---|---|
| SQL (`.sql`) | Un Markdown por script (`md/es/04_Diseno_Software/SQL/<Slug>.md`) | Enlace al original y el script completo en un bloque ` ```sql `, **sin reformatear ni corregir**. La cerca usa más acentos graves que la secuencia más larga del script. | `pendiente_revision` |
| Acceso directo (`.url`) | Un Markdown por acceso directo | La URL exacta como autoenlace (`<URL>`), enlace al original y el contenido literal del archivo en un bloque `ini`. No se modifica ni se acorta ninguna URL, aunque contenga parámetros de seguimiento o datos personales (estos se anotan en `observaciones`). | `pendiente_revision` |
| Draw.io (XML `mxfile`) | Un Markdown por archivo | Enlace al original; tablas de actores (`shape=umlActor`), casos de uso (`ellipse`), otros elementos y relaciones (aristas con su etiqueta; `endArrow=none` = asociación), leídas **solo del XML**, con el id de cada celda; observaciones verificadas, y el XML completo copiado literalmente en un bloque `xml`. No se dibuja el diagrama ni se añaden elementos que no estén en el XML. | `pendiente_revision` |
| Imágenes (PNG, JPG) | Un índice por carpeta: `md/es/<carpeta normalizada>/Indice_de_imagenes.md` | Tabla resumen (número, nombre, id, formato, dimensiones) y una sección por imagen con id, ruta original, formato, dimensiones, tamaño, SHA-256, «Transcripción: No transcrita» y la imagen (`![nombre sin extensión](ruta al original)`). La imagen **no se copia** a `_assets`. Su texto **no se transcribe**. | `solo_imagen` |

**Finales de línea en los bloques de código.** Los Markdown se guardan en UTF-8 con LF. Si el original usa CRLF, el bloque usa LF: en CommonMark (sección 2.1) CRLF y LF son el mismo final de línea y los visores muestran LF, así que no es un cambio del código. Si el original no termina en salto de línea, el contenido del bloque termina con uno, porque la cerca de cierre debe ir en su propia línea. Ambos casos se anotan en `losses` de cada archivo.

**Verificación (5.1 para estos tipos):**

| Tipo | Comprobación |
|---|---|
| SQL | Comparación **byte a byte**: se toma el contenido del bloque (sin su último salto si el original no termina en salto), se sustituye cada LF por CRLF si el original usa CRLF, y el resultado debe ser idéntico al original (mismo SHA-256 que `source_sha256`). También se cuentan CR o LF sueltos, tabulaciones, espacios de final de línea y caracteres no ASCII del original. |
| `.url` | La URL del autoenlace y el bloque `ini` son idénticos al original. |
| Draw.io | El bloque `xml` es idéntico al original; cada fila de las tablas corresponde a una celda del XML (actores + casos de uso + otros elementos + relaciones + 2 celdas raíz = total de celdas). |
| Imágenes | Las imágenes del disco coinciden con las del manifiesto; cada imagen aparece **exactamente una vez** en el índice de **su** carpeta; la ruta relativa decodificada apunta a ese original; el texto alternativo, el título de la sección, el id, el tamaño, las dimensiones y el SHA-256 coinciden con el archivo y con el manifiesto; las listas `id`, `source` y `source_sha256` del YAML están en el mismo orden que las secciones. |
| Todos | Hashes de los originales antes y después iguales; enlaces relativos sin romper; renderizado GFM sin errores; búsqueda de secretos (regla 9.4). |

## 6. Niveles de fidelidad

| Valor | Significado |
|---|---|
| `completa` | Todo el texto, todas las tablas y todas las imágenes están presentes y se revisaron contra el original. Sin pérdidas. |
| `pendiente_revision` | La verificación automática (sección 5.1) no encontró diferencias de contenido; solo hay pérdidas de presentación. Falta la revisión humana para pasar a `completa`. |
| `parcial` | Hay contenido no recuperado o sin verificar (texto dentro de imágenes o diagramas, gráficos sin datos, celdas combinadas aproximadas, OCR dudoso, títulos sin jerarquía). Las pérdidas se listan en `losses`. |
| `solo_imagen` | El documento se representa con imágenes de página y una descripción manual; no hay texto fiable. |
| `sin_evaluar` | Todavía no se ha convertido (valor inicial en el manifiesto). |
| `no_aplica` | El archivo no se convierte (imagen, SQL, acceso directo, duplicado o Markdown existente). Desde la v1.6, las imágenes, los SQL, los accesos directos y el draw.io se representan según la sección 5.3 y llevan la fidelidad que indica esa sección; `no_aplica` queda para los duplicados y los Markdown existentes. |

**Pérdidas de presentación** (se registran en `losses`, pero no rebajan la fidelidad): negritas, cursivas, fuentes, colores y bordes; tablas escritas en HTML; sangría de un índice manual; encabezados y pies de página extraídos aparte; pies de paginación y filas de encabezado repetidas por salto de página.

**Normalizaciones registradas** (tampoco rebajan la fidelidad, porque el texto resultante es el que se ve en el original, pero se listan una a una en `losses`): tildes de LaTeX recompuestas, palabras partidas con guion al final de línea y palabras partidas sin guion por el ancho de una celda.

## 7. MANIFEST.csv

Una fila por archivo del repositorio documental. Se excluyen `.git/`, `TuEvento/` (clon de código), `.claude/`, `.kiro/`, `md/` y `.gitignore`.

| Columna | Contenido |
|---|---|
| `id` | `TE-NNNN`, asignado por orden alfabético de ruta en la versión inicial. Es estable: un id nuevo se añade al final y no se renumera. |
| `original` | Ruta relativa del original. |
| `formato` | Extensión en minúsculas, o `sin_extension`. |
| `categoria` | `documento`, `hoja_calculo`, `markdown_existente`, `imagen`, `codigo_sql`, `acceso_directo` o `diagrama_drawio`. |
| `bytes`, `sha256_original` | Tamaño y hash del original al generar el manifiesto. |
| `detalle` | Páginas, caracteres de texto extraíbles, tablas, imágenes, hojas, fórmulas o celdas combinadas. En los archivos de la sección 5.3: líneas, bytes y finales de línea (SQL), dominio del destino (`.url`), elementos del diagrama (draw.io) y formato y dimensiones (imágenes). |
| `md_es`, `md_en` | Rutas de destino previstas, o la ruta del original si ya es Markdown. Cada ruta es única, **salvo** los índices de imágenes (sección 5.3): todas las imágenes de una carpeta comparten el mismo `Indice_de_imagenes.md`, y en `observaciones` se indican los ids con los que se comparte y que la imagen no está transcrita. |
| `metodo_conversion` | Método previsto (y, tras convertir, el usado). |
| `riesgo_conversion` | `bajo`, `medio`, `alto` o `no_aplica`, según el inventario. |
| `fidelidad` | Ver sección 6. |
| `estado_es`, `estado_en` | `pendiente`, `borrador`, `revisado`, `existente`, `duplicado` o `no_aplica`. |
| `duplicado_de` | Ruta del original canónico si el archivo es un duplicado exacto (mismo SHA-256). |
| `observaciones` | Erratas, datos personales, dependencias externas y riesgos. |

Criterio de riesgo inicial: **alto** para PDF sin texto, PDF de Canva y DOCX con más de 20 tablas o más de 15 imágenes; **medio** para PDF con más de 10 imágenes o más de 30 páginas, DOCX con tablas o más de 3 imágenes, y XLSX con fórmulas, celdas combinadas o imágenes; **bajo** en el resto.

## 8. Correspondencia y desactualización

- **Original → español:** si el `sha256` actual del original difiere de `source_sha256` en el Markdown, la versión en español está desactualizada.
- **Español → inglés:** si el `sha256` actual del Markdown en español difiere de `es_sha256` en el Markdown inglés, la traducción está desactualizada.
- El manifiesto es la fuente de verdad. Si hay discrepancia con el encabezado YAML, se corrige el manifiesto o el encabezado tras revisar, nunca se deja en silencio.

## 9. Reglas de contenido

1. **No se corrige el contenido** al convertir: erratas, datos incorrectos y contradicciones se conservan tal cual. Las contradicciones se registran en `Registro_de_Contradicciones.md`.
2. **No se completa** contenido ausente con suposiciones. Lo que no se puede leer se marca `[ilegible]` o `[no recuperado: <motivo>]`.
3. **Datos personales:** nombres de personas entrevistadas o encuestadas y correos personales se señalan en `observaciones` antes de publicar o traducir. No se eliminan sin decisión del equipo.
4. **Secretos:** antes de guardar un Markdown se buscan patrones sensibles (`password\s*[:=]`, `secret`, `token`, `AKIA`, `-----BEGIN`, `://usuario:clave@`) y se revisa cada coincidencia (las palabras «token» o «secret» suelen ser conceptos, no secretos). Un **secreto real** (credencial, clave o token válido) se redacta como `***` y se avisa. Los **datos de ejemplo** de un documento (p. ej. contraseñas ficticias en casos de prueba) no se alteran sin decisión del equipo: se avisa y se anota en `observaciones`. Pendiente de decisión: las contraseñas de ejemplo de `06_Pruebas/Casos_de_Prueba_TuEvento.xlsx`.
5. **Enlaces externos** (Figma, Google Drive, SharePoint, diagrams.net) se conservan y se anotan como dependencia externa no versionada.
6. **Duplicados exactos:** se convierte solo el original canónico; el duplicado queda en el manifiesto con `duplicado_de`.
7. **Imágenes, SQL y accesos directos** no se convierten; se enlazan desde el Markdown correspondiente. Desde la v1.6, además, se representan en Markdown según la sección 5.3 (copia literal, enlace o índice), sin transcribir el contenido de las imágenes.
8. **Traducción al inglés:** no se inicia hasta que el Markdown en español esté en estado `revisado`. El texto de las imágenes no se traduce; se indica en `losses`.

## 10. Lista de verificación por documento

- [ ] Encabezado YAML completo y `id` igual al del manifiesto.
- [ ] Todos los títulos, párrafos y listas del original están presentes (comparación página por página o sección por sección).
- [ ] Tablas comparadas con el original; celdas combinadas tratadas según la sección 5.
- [ ] Imágenes extraídas a `_assets`, enlazadas y con texto alternativo.
- [ ] `fidelity` y `losses` reflejan honestamente lo que falta.
- [ ] Búsqueda de secretos y de datos personales hecha.
- [ ] Fila del manifiesto actualizada (`estado_es`, `fidelidad`, `metodo_conversion`).

## 11. Herramientas: estado y requisitos

Entorno aislado preparado el 2026-10-23 en `~/.venvs/tuevento-docs`, sin `sudo`, sin instalaciones globales y fuera de ambos repositorios:

| Herramienta | Versión | Origen | Para qué |
|---|---|---|---|
| `uv` | 0.13.5 | Binario oficial de Astral (GitHub), con SHA-256 verificado; copiado en `bin/` del entorno | Crear el entorno e instalar paquetes |
| Python | 3.12.3 | Intérprete del sistema (`/usr/bin/python3.12`) | — |
| `pandoc` | 3.9 | Incluido en `pypandoc_binary` 1.17 | DOCX → Markdown |
| `pdfplumber` / `pypdf` | 0.11.10 / 6.21.2 | PyPI | PDF con texto |
| `openpyxl` | 3.1.5 | PyPI | XLSX |
| `Pillow` | 13.0.0 | PyPI (ya en el entorno) | Formato y dimensiones de las imágenes de los índices (sección 5.3) |
| `tesserocr` | 2.12.0 (tesseract 5.5.3 incluido) | PyPI (rueda binaria) | OCR |
| Modelos OCR `spa`, `eng`, `osd` | `tessdata_best` 4.1.0 | GitHub `tesseract-ocr/tessdata_best`, en `~/.venvs/tuevento-docs/tessdata/` | OCR en español e inglés |
| `pdftoppm`, `pdfimages`, `pdfinfo`, `pdftotext` | Sistema (poppler) | Ya instalados | Renderizar páginas y diagnóstico |
| `pymupdf` / `pymupdf4llm` | 2.0 / 2.0 | PyPI | **Solo comparación** en el piloto 3 (método descartado). Licencia AGPL; no se usa en la conversión y puede desinstalarse. |

La caché de `uv` está en `~/.venvs/tuevento-docs/.uv-cache`. Para eliminar el entorno basta con borrar `~/.venvs/tuevento-docs`.

SHA-256 de los modelos: `spa` `e2c1ffda…ab2c`, `eng` `8280aed0…66ba`, `osd` `9cf5d576…00ff`.
