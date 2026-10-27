# Distribución de Responsabilidades — Equipo CapySoft

---

## 1. Datos Generales

| Campo | Valor |
|---|---|
| **Proyecto formativo** | Tu Evento — plataforma web y móvil para creación, administración y operación de eventos |
| **Equipo de trabajo** | CapySoft |
| **Programa de formación** | Tecnólogo en Análisis y Desarrollo de Software (ADSO) |
| **Ficha** | 3145556 |
| **Institución** | SENA |
| **Repositorio de código** | [github.com/lozano2303/TuEvento](https://github.com/lozano2303/TuEvento) |
| **Rama / commit verificado** | `develop` / `5a64c1b` |
| **Repositorio de documentación** | [github.com/TheJhampierBoy/TuEvento-Docs](https://github.com/TheJhampierBoy/TuEvento-Docs) |
| **Fecha de elaboración** | 23 de octubre de 2026 |
| **Versión** | 1.0 |
| **Redacción del documento** | Jhampier Santos Ortiz y Cristofer David Lozano Contreras |

### 1.1 Nota metodológica

- **Evidencia de Git.** Los conteos se obtienen del repositorio de código, en todas sus ramas y **sin commits de merge** (`git log --all --no-merges`). Se suman los distintos alias de cada integrante.
- **Conteo por área.** Se cuentan los commits sin merge que modifican la ruta del área (`git log --all --no-merges -- <ruta>`). Un commit que modifica varias áreas se cuenta en cada una de ellas.
- **Porcentajes.** Se redondean a enteros, salvo en la sección 2.2. En cada fila, % Cristofer = 100 − % Jhampier.
- **Pull requests.** Se analizan los commits `Merge pull request #N` del historial de Git. Las revisiones (*reviews*) y aprobaciones de GitHub no forman parte de ese historial.
- **Información declarada.** Los roles, la participación en la documentación (sección 2.3), la coautoría del prototipo en Figma y los responsables de los entregables documentales son declarados por el equipo y no se derivan de Git.
- **Reglas de trabajo.** Las secciones 6 y 7 contienen **propuestas**. Los repositorios no contienen evidencia de que el equipo las haya adoptado formalmente.

---

## 2. Integrantes, Roles y Participación

### 2.1 Integrantes

| Nombre completo | Alias en Git | Rol declarado |
|---|---|---|
| **Jhampier Santos Ortiz** | `Jhampier`, `ortizjhampier`, `TheJhampierBoy` | Desarrollador Full Stack |
| **Cristofer David Lozano Contreras** | `Cristofer Lozano`, `Cristofer lozano`, `Cristofer Lozano (kriztoff)` | Desarrollador Full Stack |

**Énfasis de trabajo según Git:**

- **Jhampier Santos Ortiz:**
  - Panel de administración web y autenticación web.
  - Extensiones del backend: reactivación de cuenta, inicio de sesión con Google, comentarios y respuestas, y flujo y notificaciones de revisión de eventos.
  - Pruebas unitarias del backend.
  - Infraestructura de integración y despliegue continuos (CI/CD): Jenkins, Kubernetes y Render.
- **Cristofer David Lozano Contreras:**
  - Implementación base de los módulos del backend.
  - Configuración de seguridad.
  - Migraciones de Liquibase y modelo relacional.
  - Editor de layout 2D, checkout e internacionalización (i18n).
  - Aplicación móvil.

### 2.2 Commits en el repositorio de código (sin merges)

| Integrante | Alias consolidados (commits) | Commits | % |
|---|---|---|---|
| Cristofer | `Cristofer Lozano` (383) · `Cristofer lozano` (2) · `Cristofer Lozano (kriztoff)` (1) | 386 | 59,9 % |
| Jhampier | `Jhampier` (231) · `ortizjhampier` (27) | 258 | 40,1 % |
| **Total** | | **644** | **100 %** |

> El alias `TheJhampierBoy` y casi todos los commits de `Cristofer Lozano (kriztoff)` corresponden a commits de merge realizados desde GitHub. Si se incluyen los merges, el total asciende a 765 (Cristofer 449, Jhampier 316). Esta cifra es solo de referencia y no se utiliza para atribuir responsabilidades.

### 2.3 Participación en la documentación (declarada)

| Integrante | Participación documental |
|---|---|
| Jhampier Santos Ortiz | 50 % |
| Cristofer David Lozano Contreras | 50 % |

- **Fuente.** Es una **distribución declarada y equitativa de la participación documental**, establecida por el equipo. **No se deduce de Git** y es independiente de los porcentajes calculados a partir de los commits de código de la sección 2.2 (59,9 % / 40,1 %).
- **Repositorio `TuEvento-Docs`.** Sus 19 commits son de Jhampier. Esto indica que él centralizó la carga y organización de los archivos, no que sea el único autor de su contenido.
- **Metadatos de archivos.** Algunos archivos de `TuEvento-Docs` registran como autor o último editor a cuentas ajenas al equipo, como plantillas institucionales o equipos donde se editaron. Estos metadatos no se utilizan para atribuir responsabilidades.

---

## 3. Matriz RACI

**Convenciones:** R = Responsable (ejecuta) · A = Aprobador asignado (rol de revisión cruzada que se deriva de la regla 2) · C = Consultado (aportó commits en el área) · I = Informado (sin commits en el área)

**Reglas de asignación:**

1. Es responsable principal (R) quien tiene **al menos el 60 %** de los commits del área. Si nadie alcanza ese porcentaje, ambos son R.
2. El Aprobador (A) es el integrante que **no** es responsable principal. Si ambos son R, la A corresponde a quien tiene **menos** commits en el área. En caso de empate no se asigna A.
3. El integrante que no es principal se marca como C si tiene commits en el área, o como I si no tiene ninguno.
4. Las áreas documentales se asignan por función, según la responsabilidad que el equipo declaró para cada entregable (sección 4). No se derivan de Git ni del porcentaje global de participación documental (sección 2.3).
5. La columna A indica una asignación de rol derivada de estas reglas. **No implica que se hayan registrado aprobaciones**: el historial de Git no contiene revisiones ni aprobaciones de pull requests (sección 6.3).

La columna «Base» indica los commits de Jhampier / Cristofer en el área.

| Área | Jhampier | Cristofer | Base (J / C) |
|---|---|---|---|
| Análisis y requisitos | R | C, A | Declarada |
| Diseño de software | R | C, A | Declarada |
| Backend — base de arquitectura (`shared/`) | C, A | R | 14 / 56 |
| Backend — Security | R, A | R | 30 / 37 |
| Backend — Profile | C, A | R | 3 / 11 |
| Backend — Event | R, A | R | 30 / 33 |
| Backend — Notification | C, A | R | 3 / 7 |
| Backend — Payment | R, A | R | 9 / 10 |
| Backend — Wallet | C, A | R | 3 / 6 |
| Backend — Storage | C, A | R | 2 / 14 |
| Backend — Ticket | C, A | R | 1 / 7 |
| Backend — Language | I, A | R | 0 / 25 |
| Backend — Category | I, A | R | 0 / 13 |
| Backend — Section / SectionType | I, A | R | 0 / 10 |
| Backend — Geolocation | I, A | R | 0 / 10 |
| Backend — Seat | I, A | R | 0 / 9 |
| Backend — Theme | I, A | R | 0 / 8 |
| Seguridad (`shared/infrastructure/security`) | C, A | R | 6 / 25 |
| Base de datos (Liquibase `db/`) | C, A | R | 15 / 49 |
| Web — Landing, About Us | R | R, A | 12 / 10 |
| Web — Login, verificación, recuperación y cambio de contraseña | R | C, A | 25 / 12 |
| Web — CompleteProfile, ReactivateAccountPage | R | C, A | 2 / 1 |
| Web — ProfilePage | R | R, A | 14 / 12 |
| Web — Panel de administración (dashboard, financiero, reportes, eventos) | R | C, A | 38 / 8 |
| Web — Administración de categorías y tipos de sección | I, A | R | 0 / 9 |
| Web — OrganizerPetitionForm | R | C, A | 10 / 1 |
| Web — EventCreateWizard | C, A | R | 1 / 4 |
| Web — Editor de layout 2D | I, A | R | 0 / 26 |
| Web — EventManage, EventDetail (incluye el selector de asientos) | C, A | R | 23 / 41 |
| Web — Events (listado y filtros) | C, A | R | 2 / 7 |
| Web — Checkout y pagos | I, A | R | 0 / 6 |
| Web — WalletPage | C, A | R | 1 / 2 |
| Web — Notifications | C, A | R | 1 / 3 |
| Web — OrganizerEarnings | R | C, A | 2 / 1 |
| Web — TerminosDeUso, Privacidad | R | R | 1 / 1 |
| Web — Temas visuales | C, A | R | 2 / 4 |
| Web — i18n | I, A | R | 0 / 25 |
| Aplicación móvil | C, A | R | 2 / 73 |
| Pruebas unitarias del backend (`src/test`) | R | C, A | 20 / 9 |
| Infraestructura y despliegue | R | C, A | 43 / 12 |
| Documentación del proyecto | R | C, A | Declarada |
| Gestión del repositorio (fusión de pull requests) | R, A | R | 41 / 45 PR |

**Notas de la matriz:**

- **TerminosDeUso, Privacidad:** hay empate (1 / 1), por lo que ambos son R y no se asigna A (regla 2).
- **Web — Temas visuales:** el conteo subestima el aporte de Jhampier por el tamaño del commit `4ba2993` (sección 5.3).
- **Gestión del repositorio:** la base es el número de pull requests fusionados por cada integrante (sección 6.3). La A corresponde a Jhampier, que fusionó menos (41 frente a 45).
- **Revisión de pull requests:** no se incluye como área de la matriz porque el historial de Git no registra revisiones ni aprobaciones. Solo se identificó una fusión de una rama del otro integrante (PR #11).
- **Pruebas unitarias del backend:** el área se refiere al código de pruebas (`src/test`), no a informes de análisis de pruebas.
- **Infraestructura y despliegue:** incluye `Jenkinsfile`, `jenkins/`, `k8s/`, `render.yaml`, `docker-compose.yml` y los `Dockerfile` (detalle en la sección 5.5).
- **Áreas con menos de 10 commits en total:** el resultado tiene valor indicativo.

---

## 4. Responsabilidades por Entregable

Los responsables de los entregables documentales (filas 1–4 y 6–14) son **declarados por el equipo** para cada entregable. Indican quién asume la responsabilidad principal de cada uno y son independientes del porcentaje global de participación documental de la sección 2.3, que es equitativo. Las rutas son relativas a `TuEvento-Docs`, salvo que se indique otra cosa. Todos los entregables listados se encuentran en el repositorio indicado; los del repositorio de código se verificaron en el commit `5a64c1b`.

| # | Entregable | Principal | Co-responsable | Ubicación |
|---|---|---|---|---|
| 1 | ERS — Especificación de Requisitos | Jhampier | Cristofer | `es/02_Especificacion_Requisitos.md` |
| 2 | Análisis del software | Jhampier | Cristofer | `es/03_Analisis_Software.md` |
| 3 | Propuesta técnica | Jhampier | Cristofer | `es/04_Propuesta_Tecnica.md` |
| 4 | Diseño del software | Jhampier | Cristofer | `es/05_Diseno_Software.md` · `es/06_Base_Datos/` |
| 5 | Código fuente (backend, web y móvil) | Ambos | — | Repositorio `lozano2303/TuEvento` (detalle en la sección 5) |
| 6 | Documentación de pruebas | Jhampier | Cristofer | `es/07_Pruebas/` |
| 7 | Procedimiento de implementación | Jhampier | — | `es/09_Implementacion.md` |
| 8 | Acciones correctivas, preventivas y de mejora | Jhampier | — | `es/08_Calidad_Mejoras.md` |
| 9 | Manual técnico | Jhampier | — | `es/10_Manual_Tecnico.md` |
| 10 | Manual de usuario | Jhampier | Cristofer | `es/12_Manual_Usuario.md` |
| 11 | Artículo del proyecto | Jhampier | Cristofer | `es/13_Articulo_Proyecto.md` |
| 12 | Análisis de costos | Jhampier | — | `es/01_Documento_General_Proyecto.md` |
| 13 | Prototipo (Figma) | Ambos | — | `es/14_Anexos/Prototipo/` · [Figma](https://www.figma.com/design/iuw3YMS7t81m3hIKMAvtHf/Tu-Evento) |
| 14 | Matriz de trazabilidad | Jhampier | — | `es/14_Anexos/Matriz_de_Trazabilidad_TuEvento.md` |
| 15 | Pipeline CI/CD | Jhampier | — | Repositorio de código: `Jenkinsfile`, `docker-compose.yml`, `k8s/` |

**Notas sobre los entregables:**

- **Entregable 13:** la coautoría del prototipo se basa en información declarada por el equipo.
- **Entregable 15:** Jhampier es el principal en conjunto (43 / 12). `docker-compose.yml` lo creó Cristofer y tiene aportes de ambos (sección 5.5).
- **Informe de análisis de pruebas unitarias:** el archivo `INFORME_PRUEBAS_UNITARIAS.md` se añadió al repositorio de código en el commit `f8ca512` (9 de octubre de 2026) y se eliminó en el commit `47f25f7` (13 de octubre de 2026). Como no está disponible en ninguna rama del repositorio, no figura entre los entregables.

---

## 5. Responsabilidades por Módulo del Sistema

Se aplica la regla del 60 % de la sección 3. Las áreas con menos de 10 commits en total tienen valor indicativo y se marcan con *.

### 5.1 Backend — Arquitectura hexagonal (Spring Boot)

Cada módulo sigue la estructura `domain → application → infrastructure → interfaces`, dentro de `TuEventoBackend/tu-evento/src/main/java/com/capysoft/tuevento/modules/`.

| Módulo | J / C | % J / % C | Responsable principal |
|---|---|---|---|
| Security | 30 / 37 | 45 / 55 | Ambos |
| Profile | 3 / 11 | 21 / 79 | Cristofer |
| Event (módulo completo) | 30 / 33 | 48 / 52 | Ambos |
| Event — comentarios y calificaciones (backend y web) | 14 / 16 | 47 / 53 | Ambos |
| Category | 0 / 13 | 0 / 100 | Cristofer |
| Section / SectionType | 0 / 10 | 0 / 100 | Cristofer |
| Seat* | 0 / 9 | 0 / 100 | Cristofer |
| Geolocation | 0 / 10 | 0 / 100 | Cristofer |
| Language | 0 / 25 | 0 / 100 | Cristofer |
| Notification | 3 / 7 | 30 / 70 | Cristofer |
| Payment | 9 / 10 | 47 / 53 | Ambos |
| Wallet* | 3 / 6 | 33 / 67 | Cristofer |
| Storage | 2 / 14 | 13 / 87 | Cristofer |
| Ticket* | 1 / 7 | 13 / 87 | Cristofer |
| Theme* | 0 / 8 | 0 / 100 | Cristofer |

> La fila «Event — comentarios y calificaciones» detalla una parte del trabajo sobre eventos. Cuenta los commits que modifican archivos de `TuEventoBackend/tu-evento/src/main/java/` y de `TuEventoFrontend/web/src/` cuyo nombre contiene `comment` o `rating`, sin distinguir mayúsculas. Por eso incluye archivos de la web y no es comparable de forma directa con la fila del módulo completo.

**Evidencia por módulo:**

- **Security.**
  - Base de Cristofer: `3f726d8` (entidades JPA), `57879a5` (repositorios y mappers), `964e3af` (casos de uso).
  - Extensiones de Jhampier: `bac6ee5` (reactivación de cuenta), `25ec270` (login v2), `007932f` (inicio de sesión con Google).
- **Profile.** Cristofer: `a81be65` (módulo con capas, inicializador de avatar y endpoints REST). Jhampier: `88c831b` (filtro de biografía, validación del nombre y espera de 14 días para cambiarlo).
- **Event.** Cristofer: `a67a8c9`, `f32fb2e` y `75d5479` (dominio, persistencia y casos de uso). Jhampier: `a5efb11` (panel de gestión de eventos del administrador) y `ae670ce`.
- **Event — comentarios y calificaciones.**
  - Jhampier: `f164816` (respuestas, edición en línea y borrado en cascada), `ae670ce` y `5538ec4` (prefijo de mención y condición de carrera en WebSocket, en `EventDetail.jsx`).
  - Cristofer: `1b7f949` (traducción de comentarios).
- **Category.** Cristofer: `feat(category): add liquibase changesets` y `feat(admin): add category and section type management panels`.
- **Section / SectionType.** Cristofer: `ae39dd0` (changesets 052–054) y `feat(translations): add section type auto-translation system`.
- **Seat.** Cristofer: `6dbc75c` (changesets 055–057) y `feat(seats): add reservation columns and base WebSocket/STOMP config with JWT handshake auth`.
- **Geolocation.** Cristofer: `feat(geolocation): add seed data for 33 departments and 1122 cities`.
- **Language.** Cristofer: `06c2ad7` (módulo de gestión de idiomas) y `75a2531` (migración de los identificadores de `long` a `int`).
- **Notification.** Cristofer: `bfd1dbb` (módulo completo). Jhampier: `97900af` (tipos `NEW_COMMENT` y `NEW_REPLY`) y `550f19e` (notificaciones de revisión de eventos, fase 4).
- **Payment.**
  - Cristofer: PR #63 (`feature/payment-module`), PR #69 (`feature/payment-refund`) y `e80cc82` (integración con `fake-payment-gateway`).
  - Jhampier: `95f9d75` (`findEarningsByOrganizer`), `6908408` (`CreditOrganizerEarningsUseCase`) y `190e667` (abono a la billetera del organizador con el webhook `APPROVED`).
- **Wallet.** Cristofer: PR #70 (`feature/wallet-module`).
- **Storage.** Cristofer: PR #6 (`feature/storage-module`) y `86dcce6` (moderación con OpenNSFW2 y Sightengine). Jhampier: `c14a71d` (integración del servicio NSFW).
  - Relacionado: `5a64c1b` (Jhampier) ajusta la compatibilidad con R2/S3 en `shared/infrastructure/config/S3Config.java`. Es configuración compartida y no se cuenta en el módulo Storage.
- **Ticket.** Cristofer: `fix(ticket,seat): sync seat status with payment outcome`.
- **Theme.** Cristofer: `feat(theme): add liquibase changesets 034-038`.

### 5.2 Base de Datos

| Tarea | Responsable principal | Evidencia |
|---|---|---|
| Modelo relacional (`DataBase/MR/`) derivado del MER | Cristofer | `2f923f3` (único commit en `DataBase/`) |
| Changesets de Liquibase (`src/main/resources/db/`) | Cristofer (49), con colaboración de Jhampier (15) | Historial de la ruta `db/` |
| Correcciones de restricciones, cascadas y tipos | Cristofer | `fix(db): cascade delete from event`, `fix(db): align seat status/type check constraints` |

> Ejemplo de aporte de Jhampier en Liquibase: `a5ea593` (migración 090 de los campos de respuesta en comentarios).

### 5.3 Frontend Web (React/Vite)

Las rutas son relativas a `TuEventoFrontend/web/src/pages/`, salvo en las filas de temas e i18n.

| Página / Componente | J / C | % J / % C | Responsable principal |
|---|---|---|---|
| `ladingPage`, `AboutUs` | 12 / 10 | 55 / 45 | Ambos |
| `login`, `CodeVerification`, `ForgotPassword`, `ChangePassword` | 25 / 12 | 68 / 32 | Jhampier |
| `CompleteProfile`, `ReactivateAccountPage`* | 2 / 1 | 67 / 33 | Jhampier |
| `ProfilePage` | 14 / 12 | 54 / 46 | Ambos |
| Panel de administración: `AdminPanel`, `AdminDashboard`, `AdminFinancial`, `AdminReports`, `AdminEventManagement` | 38 / 8 | 83 / 17 | Jhampier |
| Administración de categorías y tipos de sección (gestión y traducciones)* | 0 / 9 | 0 / 100 | Cristofer |
| `OrganizerPetitionForm` | 10 / 1 | 91 / 9 | Jhampier |
| `EventCreateWizard`* | 1 / 4 | 20 / 80 | Cristofer |
| `EventLayoutEditor`, `EventLayoutEditorDemo` | 0 / 26 | 0 / 100 | Cristofer |
| `EventManage`, `EventDetail` | 23 / 41 | 36 / 64 | Cristofer |
| `Events`* | 2 / 7 | 22 / 78 | Cristofer |
| `Checkout`, `PaymentConfirmation`, `PaymentPending`* | 0 / 6 | 0 / 100 | Cristofer |
| `WalletPage`* | 1 / 2 | 33 / 67 | Cristofer |
| `Notifications`* | 1 / 3 | 25 / 75 | Cristofer |
| `OrganizerEarnings`* | 2 / 1 | 67 / 33 | Jhampier |
| `TerminosDeUso`, `Privacidad`* | 1 / 1 | 50 / 50 | Ambos |
| Temas visuales (`themes.js`, `ThemeContext`, `BaseModal`, `ThemeCustomizePanel`)* | 2 / 4 | 33 / 67 | Cristofer (ver la excepción) |
| i18n (`i18n.js`, `i18n/`, `locales/`) | 0 / 25 | 0 / 100 | Cristofer |

**Evidencia por página:**

- **Landing y About Us.** Jhampier: `0934425` (landing y layout), `feat: improve landing hero with animated waves and particles` y `feat: improve about us hero`. Cristofer: `4e3f28c` (landing multilingüe).
- **Autenticación.** Jhampier: `feat(auth): Google Sign-In`, `feat: nueva version del login v2` y `style(auth): replace login hero image with full-cover layout`.
- **CompleteProfile y ReactivateAccountPage.** Jhampier: `bac6ee5` (crea `ReactivateAccountPage`) y `1297406`. Cristofer: `9595030` (traducción).
- **ProfilePage.** Jhampier: `feat(profile): move deactivate button to themes column` y `feat: Google OAuth onboarding`. Cristofer: traducciones y correcciones.
- **Panel de administración.** Jhampier: `feat: add admin reports page`, `feat: update admin dashboard stats`, `feat: add Financial Control and Refunds page` y `feat: update admin event management page`.
- **Administración de categorías y tipos de sección.** Cristofer: `feat(admin): add category and section type management panels` y `feat(translations): add category translation admin panel`.
- **OrganizerPetitionForm.** Jhampier: `0c3e6b2` (solicitudes de organizador y subida de avatar).
- **EventCreateWizard.** Cristofer: `b08b11b` (asistente con selección en cascada de departamento, ciudad y sitio). Jhampier: `6d28332` (flujo de revisión, fase 2).
- **Editor de layout.** Cristofer: PR #44 (`feature/event-layout-editor-2d`) y PR #48 (`feature/layout-editor-backend-sync`).
- **EventManage y EventDetail.** Cristofer: `4fb43ea` (selector de asientos) y `07df868` (CRUD de gestión de eventos). Jhampier: `f164816` y `5538ec4`.
- **Events.** Cristofer: `524f436` (traducción en tiempo real) y `cd6b4d1` (galería de medios). Jhampier: `feat: add events page and related services` y `feat(ui): add date filter`.
- **Checkout y pagos.** Cristofer: `feat(web/checkout): implement checkout and payment pending flow`.
- **WalletPage.** Cristofer: `feat(wallet): integrate dynamic theming and real backend data in wallet page`.
- **Notifications.** Jhampier: `feat(notifications): add icons and tips for all notification types`.
- **OrganizerEarnings.** Jhampier: `feat: add OrganizerEarnings page with KPI cards and earnings table`.
- **Términos y privacidad.** Jhampier: PR #68 y PR #71 (`feat/terminos-privacidad-footer`). Cristofer: `feat: translate terms of use and privacy policy pages`.
- **Temas visuales.**
  - Cristofer integró el módulo de temas en web y móvil (`0ac1bb8`) y rediseñó la aplicación móvil con un selector de tema (`9fa9a51`, solo archivos móviles). En la web actual: `2c6d65c`, `29b329f`, `b1a31d3` (traducción de `ThemeCustomizePanel`) y `6d66864`.
  - Jhampier: `4ba2993` (33 archivos, +4460 / −1364; incluye el sistema de temas web actual junto con plantillas de correo, ajustes de interfaz e infraestructura) y `264df32`.
  - **Excepción:** por el tamaño de `4ba2993`, el conteo de commits subestima el aporte de Jhampier a la versión web actual.
- **i18n.** Cristofer: PR #90 (`feature/language-translation-service-integration`).

### 5.4 Aplicación Móvil (React Native / Expo)

En `TuEventoFrontend/movil/` hay **75 commits** sin merge: 73 de Cristofer y 2 de Jhampier. Los de Jhampier son `cfa9713` (estructura inicial del frontend) y `dc26e48` (ajuste del flujo OAuth móvil).

| Pantalla / Módulo móvil | Responsable | Evidencia |
|---|---|---|
| Autenticación | Cristofer | `style(mobile): migrate components and auth screens to theme tokens` |
| Inicio / Landing | Cristofer | `style(mobile): migrate landing home and terms screens to theme tokens` |
| EventsHome, EventDetail | Cristofer | Rama `feature-mobile/integration` |
| Mapa de asientos (Skia, WebSocket) | Cristofer | `feat(mobile): add seat map canvas with Skia` |
| Checkout y pago | Cristofer | `feat(mobile): add checkout and payment flow with fake gateway integration` |
| Billetera (Wallet) | Cristofer | `feat(mobile-wallet): implement wallet integration for mobile app` |
| Notificaciones | Cristofer | `feat(mobile-notifications): implement notifications module for mobile app` |
| Panel de administración | Cristofer | `feat(mobile-admin): implement admin panel with events management and organizer requests` |
| Perfil, configuración y temas | Cristofer | `style(mobile): add theme selector screen and navigation` |

### 5.5 Infraestructura y DevOps

| Elemento | J / C | Responsable principal | Evidencia |
|---|---|---|---|
| `Jenkinsfile` | 28 / 0 | Jhampier | `5c4f67e` (Docker, Jenkins y Kubernetes), `2cd4855` |
| `docker-compose.yml` | 14 / 11 | Ambos | Creado por Cristofer (`941b6cc`). Jhampier: `5c4f67e` y commits posteriores |
| `Dockerfile` (backend, web y servicios) | 9 / 4 | Jhampier | Historial de los `Dockerfile` |
| `k8s/` | 4 / 0 | Jhampier* | `5c4f67e`, `adfe4a4` |
| `render.yaml` | 2 / 0 | Jhampier* | `68c6821` (configuración de Render, fase 1) |
| `docs/PIPELINE-TECHNICAL-DOCUMENT.md` | 2 / 0 | Jhampier* | Historial del archivo |
| SonarQube (etapas del pipeline) | — | Jhampier | `4b12d99`, `fix: use correct sonarqube container hostname` |
| Registro de imágenes Docker (`jhampier23/tu-evento`) | — | Jhampier | `d32e35c` |
| `fake-payment-gateway/` | 0 / 6 | Cristofer* | `4e2a91c` (servicio de pasarela simulada para desarrollo local) |
| `nsfw-service/` | 1 / 2 | Cristofer* | Cristofer: `86dcce6`. La integración en el backend es de Jhampier (`c14a71d`) |

> En conjunto (`Jenkinsfile`, `jenkins/`, `k8s/`, `render.yaml`, `docker-compose.yml` y los `Dockerfile`): Jhampier 43 y Cristofer 12, es decir, 78 % / 22 %.

---

## 6. Flujo de Trabajo en Equipo

> **Carácter de esta sección.** Los repositorios no contienen un archivo de reglas de contribución (`CONTRIBUTING.md`, `.github/`) ni un registro de que el equipo haya adoptado formalmente reglas de trabajo. Por ello, las reglas de esta sección y el procedimiento de la sección 7 se presentan como **propuestas**. En cada apartado se describe, además, la práctica observada en Git.

### 6.1 Estrategia de ramas

**Propuesta:**

- No hacer commits directos en `main` ni en `develop`; todo cambio se integra mediante pull request.
- Los cambios llegan a `main` solo mediante pull request desde `develop`.
- Prefijos de rama: `feat/`, `fix/`, `chore/` y `hotfix/`, en *kebab-case*.
- Versionado con etiquetas SemVer (`v1.0.0`, `v1.1.0`, …).
- Fusión: **Squash and Merge** hacia `develop` y **Merge Commit** hacia `main`.

**Práctica observada:**

| Rama | Propósito |
|---|---|
| `main` | Código listo para demostración |
| `develop` | Rama principal de integración |
| `feature/<nombre>`, `feat/<nombre>` | Funcionalidades. Ej.: `feature/wallet-module`, `feat/event-comments-websocket` |
| `fix/<nombre>` | Correcciones. Ej.: `fix/backend-config-and-migrations` |
| `style/<nombre>` | Cambios visuales. Ej.: `style/admin-panel-modal-redesign` |
| `backup/<nombre>` | Respaldo antes de reestructuraciones. Ej.: `backup/before-rewrite-ae670ce` |

> **Diferencias con la propuesta:**
> - Se usaron los prefijos `feature/`, `style/` y `backup/`, que no figuran en la propuesta.
> - El repositorio no tiene etiquetas (0 *tags*), por lo que el versionado SemVer no se ha aplicado.

### 6.2 Convención de mensajes de commit (Conventional Commits)

**Propuesta:** usar el formato `tipo(ámbito): descripción`, en inglés, con los tipos siguientes.

| Tipo | Uso |
|---|---|
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de un defecto |
| `refactor` | Reestructuración sin cambio de comportamiento |
| `chore` | Mantenimiento, configuración o dependencias |
| `docs` | Documentación |
| `style` | Cambios visuales o de formato |
| `test` | Pruebas |
| `perf` | Rendimiento |

> **Práctica observada (644 commits sin merge):**
> - 598 (93 %) comienzan con uno de los ocho tipos propuestos, con o sin ámbito (`tipo: …` o `tipo(ámbito): …`).
> - De ellos, 239 (37 % del total) incluyen además el ámbito entre paréntesis.
> - Otros 3 usan los tipos `build` y `ci`, que no figuran en la lista propuesta.
> - Algunos mensajes están redactados en español.

### 6.3 Pull requests

**Propuesta:**

- Pull requests de un máximo de 400 líneas modificadas.
- Al menos una aprobación antes de fusionar.
- Respuesta del revisor en un máximo de 24 horas hábiles.
- Revisión **cruzada**: cada integrante revisa el trabajo del otro.

**Práctica observada:**

Se identificaron **86 pull requests**, numerados del #1 al #90; no aparecen los #2, #3, #37 ni #89. El PR #1 tiene dos commits de merge (`7b0f9b7` y `43013f7`) y se cuenta una sola vez. Se considera «rama propia» aquella en la que la mayoría de los commits son del integrante que la fusionó.

| Integrante | PR fusionados | Rama propia | Rama del otro integrante |
|---|---|---|---|
| Cristofer (`kriztoff`) | 45 | 45 | 0 |
| Jhampier (`TheJhampierBoy`) | 41 | 40 | 1 (PR #11) |
| **Total** | **86** | **85** | **1** |

- Entre el PR #60 y el #72, Cristofer fusionó 7 y Jhampier 6. Del #73 al #88, Jhampier fusionó los 16.
- El historial de Git no incluye las revisiones ni las aprobaciones de GitHub, por lo que no permite constatar la revisión cruzada.

### 6.4 Definición de Listo (Definition of Ready, DoR)

**Propuesta.** Una historia de usuario está lista para desarrollarse cuando:

- está redactada en el formato **Como / quiero / para que**;
- tiene al menos **dos criterios de aceptación** en el formato **Dado / Cuando / Entonces**;
- sus dependencias están resueltas (fusionadas en `develop` o acordadas);
- si requiere endpoints nuevos, tiene definido el **contrato OpenAPI** antes de empezar.

### 6.5 Definición de Hecho (Definition of Done, DoD)

**Propuesta.** Un ítem está terminado cuando:

- el pull request está aprobado por el otro integrante;
- las pruebas no reducen la cobertura existente;
- el pipeline de Jenkins finaliza sin errores;
- la documentación afectada está actualizada (README, OpenAPI, modelo de datos o registros de decisiones de arquitectura);
- si el equipo habilita un entorno de *staging*, el despliegue en ese entorno supera la prueba de humo (*smoke test*). Los repositorios no contienen evidencia de un entorno de este tipo.

---

## 7. Procedimiento Propuesto para Cambios y Reasignación de Tareas

> **Carácter de esta sección:** propuesta (ver la sección 6).

| Situación | Procedimiento propuesto |
|---|---|
| Un integrante no puede completar una tarea | Lo notifica al equipo. El otro integrante la asume de forma temporal y el cambio queda registrado en el pull request o en el commit. |
| Defecto en el código del otro integrante | Se crea una rama `fix/<descripción>` con su pull request, que revisa el autor original. |
| Cambio de alcance que afecta a ambos | Se discute en el canal del equipo y se registra en el pull request o en un *issue*. |
| Cambio que afecta a la documentación | Se actualiza `TuEvento-Docs` con un commit en formato Conventional Commits. Actualmente Jhampier centraliza la carga de archivos (sección 2.3). |
| Reasignación definitiva de un módulo | Se registra en una nueva versión de este documento, se actualiza la matriz RACI y se informa al instructor. |

---


*Versión 1.0 · 23 de octubre de 2026 · Equipo CapySoft · Ficha SENA 3145556*
