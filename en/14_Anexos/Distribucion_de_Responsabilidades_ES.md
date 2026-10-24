---
id: TE-0003
title: "Distribucion_de_Responsabilidades_ES"
lang: en
source: 00_Informes/Distribucion_de_Responsabilidades_ES.md
conversion: "Original Markdown (no conversion). English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-24
fidelity: pendiente_revision
losses:
  - "Translation: commit messages, branch names, file paths and identifiers are kept as in the original (they are not translated)."
  - "Translation: decimal numbers use the English format (59.9 % instead of 59,9 %)."
status: borrador
reviewed_by: ""
translation_of: es/14_Anexos/Distribucion_de_Responsabilidades_ES.md
es_sha256: 48ddd151b65997ce5c509982b3d646a596183236c663f4d02b80f8a8b1613704
---
# Distribution of Responsibilities — CapySoft Team

---

## 1. General Information

| Field | Value |
|---|---|
| **Training project** | Tu Evento — web and mobile platform for creating, managing and running events |
| **Work team** | CapySoft |
| **Training program** | Technologist in Software Analysis and Development (ADSO) |
| **Cohort (Ficha)** | 3145556 |
| **Institution** | SENA |
| **Code repository** | [github.com/lozano2303/TuEvento](https://github.com/lozano2303/TuEvento) |
| **Verified branch / commit** | `develop` / `5a64c1b` |
| **Documentation repository** | [github.com/TheJhampierBoy/TuEvento-Docs](https://github.com/TheJhampierBoy/TuEvento-Docs) |
| **Date prepared** | October 23, 2026 |
| **Version** | 1.0 |
| **Written by** | Jhampier Santos Ortiz and Cristofer David Lozano Contreras |

### 1.1 Methodological note

- **Git evidence.** The counts are taken from the code repository, across all its branches and **without merge commits** (`git log --all --no-merges`). The different aliases of each member are added together.
- **Count by area.** The non-merge commits that modify the area's path are counted (`git log --all --no-merges -- <path>`). A commit that modifies several areas is counted in each of them.
- **Percentages.** They are rounded to whole numbers, except in section 2.2. In each row, % Cristofer = 100 − % Jhampier.
- **Pull requests.** The `Merge pull request #N` commits in the Git history are analyzed. GitHub reviews and approvals are not part of that history.
- **Declared information.** The roles, the participation in the documentation (section 2.3), the co-authorship of the Figma prototype and the owners of the documentation deliverables are declared by the team and are not derived from Git.
- **Working rules.** Sections 6 and 7 contain **proposals**. The repositories contain no evidence that the team has formally adopted them.

---

## 2. Members, Roles and Participation

### 2.1 Members

| Full name | Git alias | Declared role |
|---|---|---|
| **Jhampier Santos Ortiz** | `Jhampier`, `ortizjhampier`, `TheJhampierBoy` | Full Stack Developer |
| **Cristofer David Lozano Contreras** | `Cristofer Lozano`, `Cristofer lozano`, `Cristofer Lozano (kriztoff)` | Full Stack Developer |

**Work focus according to Git:**

- **Jhampier Santos Ortiz:**
  - Web administration panel and web authentication.
  - Backend extensions: account reactivation, Google sign-in, comments and replies, and event review flow and notifications.
  - Backend unit tests.
  - Continuous integration and deployment (CI/CD) infrastructure: Jenkins, Kubernetes and Render.
- **Cristofer David Lozano Contreras:**
  - Base implementation of the backend modules.
  - Security configuration.
  - Liquibase migrations and relational model.
  - 2D layout editor, checkout and internationalization (i18n).
  - Mobile application.

### 2.2 Commits in the code repository (without merges)

| Member | Consolidated aliases (commits) | Commits | % |
|---|---|---|---|
| Cristofer | `Cristofer Lozano` (383) · `Cristofer lozano` (2) · `Cristofer Lozano (kriztoff)` (1) | 386 | 59.9 % |
| Jhampier | `Jhampier` (231) · `ortizjhampier` (27) | 258 | 40.1 % |
| **Total** | | **644** | **100 %** |

> The `TheJhampierBoy` alias and almost all the `Cristofer Lozano (kriztoff)` commits are merge commits made from GitHub. If merges are included, the total rises to 765 (Cristofer 449, Jhampier 316). This figure is for reference only and is not used to assign responsibilities.

### 2.3 Participation in the documentation (declared)

| Member | Documentation participation |
|---|---|
| Jhampier Santos Ortiz | 50 % |
| Cristofer David Lozano Contreras | 50 % |

- **Source.** It is a **declared and equal distribution of the documentation participation**, established by the team. **It is not derived from Git** and is independent of the percentages calculated from the code commits in section 2.2 (59.9 % / 40.1 %).
- **`TuEvento-Docs` repository.** Its 19 commits are by Jhampier. This shows that he centralized the uploading and organization of the files, not that he is the only author of their content.
- **File metadata.** Some files in `TuEvento-Docs` record accounts outside the team as author or last editor, such as institutional templates or computers where they were edited. This metadata is not used to assign responsibilities.

---

## 3. RACI Matrix

**Conventions:** R = Responsible (executes) · A = Assigned approver (cross-review role derived from rule 2) · C = Consulted (contributed commits in the area) · I = Informed (no commits in the area)

**Assignment rules:**

1. The main responsible (R) is whoever has **at least 60 %** of the area's commits. If nobody reaches that percentage, both are R.
2. The Approver (A) is the member who is **not** the main responsible. If both are R, the A goes to whoever has **fewer** commits in the area. In case of a tie, no A is assigned.
3. The member who is not the main one is marked as C if they have commits in the area, or as I if they have none.
4. The documentation areas are assigned by function, according to the responsibility the team declared for each deliverable (section 4). They are not derived from Git or from the overall documentation participation percentage (section 2.3).
5. Column A indicates a role assignment derived from these rules. **It does not imply that approvals were recorded**: the Git history contains no pull request reviews or approvals (section 6.3).

The "Basis" column shows Jhampier's / Cristofer's commits in the area.

| Area | Jhampier | Cristofer | Basis (J / C) |
|---|---|---|---|
| Analysis and requirements | R | C, A | Declared |
| Software design | R | C, A | Declared |
| Backend — architecture base (`shared/`) | C, A | R | 14 / 56 |
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
| Security (`shared/infrastructure/security`) | C, A | R | 6 / 25 |
| Database (Liquibase `db/`) | C, A | R | 15 / 49 |
| Web — Landing, About Us | R | R, A | 12 / 10 |
| Web — Login, verification, password recovery and change | R | C, A | 25 / 12 |
| Web — CompleteProfile, ReactivateAccountPage | R | C, A | 2 / 1 |
| Web — ProfilePage | R | R, A | 14 / 12 |
| Web — Administration panel (dashboard, financial, reports, events) | R | C, A | 38 / 8 |
| Web — Category and section type administration | I, A | R | 0 / 9 |
| Web — OrganizerPetitionForm | R | C, A | 10 / 1 |
| Web — EventCreateWizard | C, A | R | 1 / 4 |
| Web — 2D layout editor | I, A | R | 0 / 26 |
| Web — EventManage, EventDetail (includes the seat selector) | C, A | R | 23 / 41 |
| Web — Events (list and filters) | C, A | R | 2 / 7 |
| Web — Checkout and payments | I, A | R | 0 / 6 |
| Web — WalletPage | C, A | R | 1 / 2 |
| Web — Notifications | C, A | R | 1 / 3 |
| Web — OrganizerEarnings | R | C, A | 2 / 1 |
| Web — TerminosDeUso, Privacidad | R | R | 1 / 1 |
| Web — Visual themes | C, A | R | 2 / 4 |
| Web — i18n | I, A | R | 0 / 25 |
| Mobile application | C, A | R | 2 / 73 |
| Backend unit tests (`src/test`) | R | C, A | 20 / 9 |
| Infrastructure and deployment | R | C, A | 43 / 12 |
| Project documentation | R | C, A | Declared |
| Repository management (merging pull requests) | R, A | R | 41 / 45 PR |

**Matrix notes:**

- **TerminosDeUso, Privacidad:** there is a tie (1 / 1), so both are R and no A is assigned (rule 2).
- **Web — Visual themes:** the count underestimates Jhampier's contribution because of the size of commit `4ba2993` (section 5.3).
- **Repository management:** the basis is the number of pull requests merged by each member (section 6.3). The A goes to Jhampier, who merged fewer (41 versus 45).
- **Pull request review:** it is not included as a matrix area because the Git history records no reviews or approvals. Only one merge of a branch from the other member was identified (PR #11).
- **Backend unit tests:** the area refers to the test code (`src/test`), not to test analysis reports.
- **Infrastructure and deployment:** includes `Jenkinsfile`, `jenkins/`, `k8s/`, `render.yaml`, `docker-compose.yml` and the `Dockerfile`s (details in section 5.5).
- **Areas with fewer than 10 commits in total:** the result is indicative.

---

## 4. Responsibilities by Deliverable

The owners of the documentation deliverables (rows 1–4 and 6–14) are **declared by the team** for each deliverable. They indicate who takes the main responsibility for each one and are independent of the overall documentation participation percentage in section 2.3, which is equal. Paths are relative to `TuEvento-Docs`, unless stated otherwise. All the listed deliverables are in the indicated repository; those in the code repository were verified at commit `5a64c1b`.

| # | Deliverable | Main | Co-owner | Location |
|---|---|---|---|---|
| 1 | SRS — Software Requirements Specification | Jhampier | Cristofer | `en/02_Especificacion_Requisitos.md` |
| 2 | Software analysis | Jhampier | Cristofer | `en/03_Analisis_Software.md` |
| 3 | Technical proposal | Jhampier | Cristofer | `en/04_Propuesta_Tecnica.md` |
| 4 | Software design | Jhampier | Cristofer | `en/05_Diseno_Software.md` · `en/06_Base_Datos/` |
| 5 | Source code (backend, web and mobile) | Both | — | Repository `lozano2303/TuEvento` (details in section 5) |
| 6 | Testing documentation | Jhampier | Cristofer | `en/07_Pruebas/` |
| 7 | Implementation procedure | Jhampier | — | `en/09_Implementacion.md` |
| 8 | Corrective, preventive and improvement actions | Jhampier | — | `en/08_Calidad_Mejoras.md` |
| 9 | Technical manual | Jhampier | — | `en/10_Manual_Tecnico.md` |
| 10 | User manual | Jhampier | Cristofer | `en/12_Manual_Usuario.md` |
| 11 | Project article | Jhampier | Cristofer | `en/13_Articulo_Proyecto.md` |
| 12 | Cost analysis | Jhampier | — | `en/01_Documento_General_Proyecto.md` |
| 13 | Prototype (Figma) | Both | — | `en/14_Anexos/Prototipo/` · [Figma](https://www.figma.com/design/iuw3YMS7t81m3hIKMAvtHf/Tu-Evento) |
| 14 | Traceability matrix | Jhampier | — | `en/14_Anexos/Matriz_de_Trazabilidad_TuEvento.md` |
| 15 | CI/CD pipeline | Jhampier | — | Code repository: `Jenkinsfile`, `docker-compose.yml`, `k8s/` |

**Notes on the deliverables:**

- **Deliverable 13:** the co-authorship of the prototype is based on information declared by the team.
- **Deliverable 15:** Jhampier is the main owner overall (43 / 12). `docker-compose.yml` was created by Cristofer and has contributions from both (section 5.5).
- **Unit test analysis report:** the file `INFORME_PRUEBAS_UNITARIAS.md` was added to the code repository in commit `f8ca512` (October 9, 2026) and removed in commit `47f25f7` (October 13, 2026). Since it is not available in any branch of the repository, it is not listed among the deliverables.

---

## 5. Responsibilities by System Module

The 60 % rule from section 3 applies. Areas with fewer than 10 commits in total are indicative and are marked with *.

### 5.1 Backend — Hexagonal architecture (Spring Boot)

Each module follows the `domain → application → infrastructure → interfaces` structure, inside `TuEventoBackend/tu-evento/src/main/java/com/capysoft/tuevento/modules/`.

| Module | J / C | % J / % C | Main responsible |
|---|---|---|---|
| Security | 30 / 37 | 45 / 55 | Both |
| Profile | 3 / 11 | 21 / 79 | Cristofer |
| Event (whole module) | 30 / 33 | 48 / 52 | Both |
| Event — comments and ratings (backend and web) | 14 / 16 | 47 / 53 | Both |
| Category | 0 / 13 | 0 / 100 | Cristofer |
| Section / SectionType | 0 / 10 | 0 / 100 | Cristofer |
| Seat* | 0 / 9 | 0 / 100 | Cristofer |
| Geolocation | 0 / 10 | 0 / 100 | Cristofer |
| Language | 0 / 25 | 0 / 100 | Cristofer |
| Notification | 3 / 7 | 30 / 70 | Cristofer |
| Payment | 9 / 10 | 47 / 53 | Both |
| Wallet* | 3 / 6 | 33 / 67 | Cristofer |
| Storage | 2 / 14 | 13 / 87 | Cristofer |
| Ticket* | 1 / 7 | 13 / 87 | Cristofer |
| Theme* | 0 / 8 | 0 / 100 | Cristofer |

> The "Event — comments and ratings" row details part of the work on events. It counts the commits that modify files in `TuEventoBackend/tu-evento/src/main/java/` and `TuEventoFrontend/web/src/` whose name contains `comment` or `rating`, case-insensitive. That is why it includes web files and is not directly comparable with the whole-module row.

**Evidence by module:**

- **Security.**
  - Cristofer's base: `3f726d8` (JPA entities), `57879a5` (repositories and mappers), `964e3af` (use cases).
  - Jhampier's extensions: `bac6ee5` (account reactivation), `25ec270` (login v2), `007932f` (Google sign-in).
- **Profile.** Cristofer: `a81be65` (layered module, avatar initializer and REST endpoints). Jhampier: `88c831b` (biography filter, name validation and 14-day wait to change it).
- **Event.** Cristofer: `a67a8c9`, `f32fb2e` and `75d5479` (domain, persistence and use cases). Jhampier: `a5efb11` (administrator event management panel) and `ae670ce`.
- **Event — comments and ratings.**
  - Jhampier: `f164816` (replies, inline editing and cascade delete), `ae670ce` and `5538ec4` (mention prefix and WebSocket race condition, in `EventDetail.jsx`).
  - Cristofer: `1b7f949` (comment translation).
- **Category.** Cristofer: `feat(category): add liquibase changesets` and `feat(admin): add category and section type management panels`.
- **Section / SectionType.** Cristofer: `ae39dd0` (changesets 052–054) and `feat(translations): add section type auto-translation system`.
- **Seat.** Cristofer: `6dbc75c` (changesets 055–057) and `feat(seats): add reservation columns and base WebSocket/STOMP config with JWT handshake auth`.
- **Geolocation.** Cristofer: `feat(geolocation): add seed data for 33 departments and 1122 cities`.
- **Language.** Cristofer: `06c2ad7` (language management module) and `75a2531` (migration of identifiers from `long` to `int`).
- **Notification.** Cristofer: `bfd1dbb` (whole module). Jhampier: `97900af` (`NEW_COMMENT` and `NEW_REPLY` types) and `550f19e` (event review notifications, phase 4).
- **Payment.**
  - Cristofer: PR #63 (`feature/payment-module`), PR #69 (`feature/payment-refund`) and `e80cc82` (integration with `fake-payment-gateway`).
  - Jhampier: `95f9d75` (`findEarningsByOrganizer`), `6908408` (`CreditOrganizerEarningsUseCase`) and `190e667` (credit to the organizer's wallet with the `APPROVED` webhook).
- **Wallet.** Cristofer: PR #70 (`feature/wallet-module`).
- **Storage.** Cristofer: PR #6 (`feature/storage-module`) and `86dcce6` (moderation with OpenNSFW2 and Sightengine). Jhampier: `c14a71d` (NSFW service integration).
  - Related: `5a64c1b` (Jhampier) adjusts R2/S3 compatibility in `shared/infrastructure/config/S3Config.java`. It is shared configuration and is not counted in the Storage module.
- **Ticket.** Cristofer: `fix(ticket,seat): sync seat status with payment outcome`.
- **Theme.** Cristofer: `feat(theme): add liquibase changesets 034-038`.

### 5.2 Database

| Task | Main responsible | Evidence |
|---|---|---|
| Relational model (`DataBase/MR/`) derived from the ERM | Cristofer | `2f923f3` (only commit in `DataBase/`) |
| Liquibase changesets (`src/main/resources/db/`) | Cristofer (49), with collaboration from Jhampier (15) | History of the `db/` path |
| Fixes to constraints, cascades and types | Cristofer | `fix(db): cascade delete from event`, `fix(db): align seat status/type check constraints` |

> Example of Jhampier's contribution to Liquibase: `a5ea593` (migration 090 of the reply fields in comments).

### 5.3 Web Frontend (React/Vite)

Paths are relative to `TuEventoFrontend/web/src/pages/`, except in the theme and i18n rows.

| Page / Component | J / C | % J / % C | Main responsible |
|---|---|---|---|
| `ladingPage`, `AboutUs` | 12 / 10 | 55 / 45 | Both |
| `login`, `CodeVerification`, `ForgotPassword`, `ChangePassword` | 25 / 12 | 68 / 32 | Jhampier |
| `CompleteProfile`, `ReactivateAccountPage`* | 2 / 1 | 67 / 33 | Jhampier |
| `ProfilePage` | 14 / 12 | 54 / 46 | Both |
| Administration panel: `AdminPanel`, `AdminDashboard`, `AdminFinancial`, `AdminReports`, `AdminEventManagement` | 38 / 8 | 83 / 17 | Jhampier |
| Category and section type administration (management and translations)* | 0 / 9 | 0 / 100 | Cristofer |
| `OrganizerPetitionForm` | 10 / 1 | 91 / 9 | Jhampier |
| `EventCreateWizard`* | 1 / 4 | 20 / 80 | Cristofer |
| `EventLayoutEditor`, `EventLayoutEditorDemo` | 0 / 26 | 0 / 100 | Cristofer |
| `EventManage`, `EventDetail` | 23 / 41 | 36 / 64 | Cristofer |
| `Events`* | 2 / 7 | 22 / 78 | Cristofer |
| `Checkout`, `PaymentConfirmation`, `PaymentPending`* | 0 / 6 | 0 / 100 | Cristofer |
| `WalletPage`* | 1 / 2 | 33 / 67 | Cristofer |
| `Notifications`* | 1 / 3 | 25 / 75 | Cristofer |
| `OrganizerEarnings`* | 2 / 1 | 67 / 33 | Jhampier |
| `TerminosDeUso`, `Privacidad`* | 1 / 1 | 50 / 50 | Both |
| Visual themes (`themes.js`, `ThemeContext`, `BaseModal`, `ThemeCustomizePanel`)* | 2 / 4 | 33 / 67 | Cristofer (see the exception) |
| i18n (`i18n.js`, `i18n/`, `locales/`) | 0 / 25 | 0 / 100 | Cristofer |

**Evidence by page:**

- **Landing and About Us.** Jhampier: `0934425` (landing and layout), `feat: improve landing hero with animated waves and particles` and `feat: improve about us hero`. Cristofer: `4e3f28c` (multilingual landing).
- **Authentication.** Jhampier: `feat(auth): Google Sign-In`, `feat: nueva version del login v2` and `style(auth): replace login hero image with full-cover layout`.
- **CompleteProfile and ReactivateAccountPage.** Jhampier: `bac6ee5` (creates `ReactivateAccountPage`) and `1297406`. Cristofer: `9595030` (translation).
- **ProfilePage.** Jhampier: `feat(profile): move deactivate button to themes column` and `feat: Google OAuth onboarding`. Cristofer: translations and fixes.
- **Administration panel.** Jhampier: `feat: add admin reports page`, `feat: update admin dashboard stats`, `feat: add Financial Control and Refunds page` and `feat: update admin event management page`.
- **Category and section type administration.** Cristofer: `feat(admin): add category and section type management panels` and `feat(translations): add category translation admin panel`.
- **OrganizerPetitionForm.** Jhampier: `0c3e6b2` (organizer requests and avatar upload).
- **EventCreateWizard.** Cristofer: `b08b11b` (wizard with cascading selection of department, city and site). Jhampier: `6d28332` (review flow, phase 2).
- **Layout editor.** Cristofer: PR #44 (`feature/event-layout-editor-2d`) and PR #48 (`feature/layout-editor-backend-sync`).
- **EventManage and EventDetail.** Cristofer: `4fb43ea` (seat selector) and `07df868` (event management CRUD). Jhampier: `f164816` and `5538ec4`.
- **Events.** Cristofer: `524f436` (real-time translation) and `cd6b4d1` (media gallery). Jhampier: `feat: add events page and related services` and `feat(ui): add date filter`.
- **Checkout and payments.** Cristofer: `feat(web/checkout): implement checkout and payment pending flow`.
- **WalletPage.** Cristofer: `feat(wallet): integrate dynamic theming and real backend data in wallet page`.
- **Notifications.** Jhampier: `feat(notifications): add icons and tips for all notification types`.
- **OrganizerEarnings.** Jhampier: `feat: add OrganizerEarnings page with KPI cards and earnings table`.
- **Terms and privacy.** Jhampier: PR #68 and PR #71 (`feat/terminos-privacidad-footer`). Cristofer: `feat: translate terms of use and privacy policy pages`.
- **Visual themes.**
  - Cristofer integrated the themes module into web and mobile (`0ac1bb8`) and redesigned the mobile application with a theme selector (`9fa9a51`, mobile files only). In the current web: `2c6d65c`, `29b329f`, `b1a31d3` (translation of `ThemeCustomizePanel`) and `6d66864`.
  - Jhampier: `4ba2993` (33 files, +4460 / −1364; includes the current web theme system together with email templates, interface adjustments and infrastructure) and `264df32`.
  - **Exception:** because of the size of `4ba2993`, the commit count underestimates Jhampier's contribution to the current web version.
- **i18n.** Cristofer: PR #90 (`feature/language-translation-service-integration`).

### 5.4 Mobile Application (React Native / Expo)

In `TuEventoFrontend/movil/` there are **75 non-merge commits**: 73 by Cristofer and 2 by Jhampier. Jhampier's are `cfa9713` (initial frontend structure) and `dc26e48` (mobile OAuth flow adjustment).

| Mobile screen / module | Responsible | Evidence |
|---|---|---|
| Authentication | Cristofer | `style(mobile): migrate components and auth screens to theme tokens` |
| Home / Landing | Cristofer | `style(mobile): migrate landing home and terms screens to theme tokens` |
| EventsHome, EventDetail | Cristofer | Branch `feature-mobile/integration` |
| Seat map (Skia, WebSocket) | Cristofer | `feat(mobile): add seat map canvas with Skia` |
| Checkout and payment | Cristofer | `feat(mobile): add checkout and payment flow with fake gateway integration` |
| Wallet | Cristofer | `feat(mobile-wallet): implement wallet integration for mobile app` |
| Notifications | Cristofer | `feat(mobile-notifications): implement notifications module for mobile app` |
| Administration panel | Cristofer | `feat(mobile-admin): implement admin panel with events management and organizer requests` |
| Profile, settings and themes | Cristofer | `style(mobile): add theme selector screen and navigation` |

### 5.5 Infrastructure and DevOps

| Item | J / C | Main responsible | Evidence |
|---|---|---|---|
| `Jenkinsfile` | 28 / 0 | Jhampier | `5c4f67e` (Docker, Jenkins and Kubernetes), `2cd4855` |
| `docker-compose.yml` | 14 / 11 | Both | Created by Cristofer (`941b6cc`). Jhampier: `5c4f67e` and later commits |
| `Dockerfile` (backend, web and services) | 9 / 4 | Jhampier | History of the `Dockerfile`s |
| `k8s/` | 4 / 0 | Jhampier* | `5c4f67e`, `adfe4a4` |
| `render.yaml` | 2 / 0 | Jhampier* | `68c6821` (Render configuration, phase 1) |
| `docs/PIPELINE-TECHNICAL-DOCUMENT.md` | 2 / 0 | Jhampier* | History of the file |
| SonarQube (pipeline stages) | — | Jhampier | `4b12d99`, `fix: use correct sonarqube container hostname` |
| Docker image registry (`jhampier23/tu-evento`) | — | Jhampier | `d32e35c` |
| `fake-payment-gateway/` | 0 / 6 | Cristofer* | `4e2a91c` (simulated gateway service for local development) |
| `nsfw-service/` | 1 / 2 | Cristofer* | Cristofer: `86dcce6`. The backend integration is by Jhampier (`c14a71d`) |

> Overall (`Jenkinsfile`, `jenkins/`, `k8s/`, `render.yaml`, `docker-compose.yml` and the `Dockerfile`s): Jhampier 43 and Cristofer 12, that is, 78 % / 22 %.

---

## 6. Team Workflow

> **Nature of this section.** The repositories contain no contribution rules file (`CONTRIBUTING.md`, `.github/`) nor any record that the team has formally adopted working rules. Therefore, the rules in this section and the procedure in section 7 are presented as **proposals**. Each subsection also describes the practice observed in Git.

### 6.1 Branching strategy

**Proposal:**

- No direct commits to `main` or `develop`; every change is integrated through a pull request.
- Changes reach `main` only through a pull request from `develop`.
- Branch prefixes: `feat/`, `fix/`, `chore/` and `hotfix/`, in *kebab-case*.
- Versioning with SemVer tags (`v1.0.0`, `v1.1.0`, …).
- Merging: **Squash and Merge** into `develop` and **Merge Commit** into `main`.

**Observed practice:**

| Branch | Purpose |
|---|---|
| `main` | Demo-ready code |
| `develop` | Main integration branch |
| `feature/<name>`, `feat/<name>` | Features. E.g.: `feature/wallet-module`, `feat/event-comments-websocket` |
| `fix/<name>` | Fixes. E.g.: `fix/backend-config-and-migrations` |
| `style/<name>` | Visual changes. E.g.: `style/admin-panel-modal-redesign` |
| `backup/<name>` | Backup before restructurings. E.g.: `backup/before-rewrite-ae670ce` |

> **Differences from the proposal:**
> - The prefixes `feature/`, `style/` and `backup/` were used, which are not in the proposal.
> - The repository has no tags (0 *tags*), so SemVer versioning has not been applied.

### 6.2 Commit message convention (Conventional Commits)

**Proposal:** use the format `type(scope): description`, in English, with the following types.

| Type | Use |
|---|---|
| `feat` | New feature |
| `fix` | Defect fix |
| `refactor` | Restructuring without behavior change |
| `chore` | Maintenance, configuration or dependencies |
| `docs` | Documentation |
| `style` | Visual or formatting changes |
| `test` | Tests |
| `perf` | Performance |

> **Observed practice (644 non-merge commits):**
> - 598 (93 %) start with one of the eight proposed types, with or without scope (`type: …` or `type(scope): …`).
> - Of those, 239 (37 % of the total) also include the scope in parentheses.
> - Another 3 use the `build` and `ci` types, which are not in the proposed list.
> - Some messages are written in Spanish.

### 6.3 Pull requests

**Proposal:**

- Pull requests of at most 400 modified lines.
- At least one approval before merging.
- Reviewer response within at most 24 business hours.
- **Cross** review: each member reviews the other's work.

**Observed practice:**

**86 pull requests** were identified, numbered from #1 to #90; #2, #3, #37 and #89 do not appear. PR #1 has two merge commits (`7b0f9b7` and `43013f7`) and is counted once. A branch is considered "own branch" when most of its commits are by the member who merged it.

| Member | Merged PRs | Own branch | Other member's branch |
|---|---|---|---|
| Cristofer (`kriztoff`) | 45 | 45 | 0 |
| Jhampier (`TheJhampierBoy`) | 41 | 40 | 1 (PR #11) |
| **Total** | **86** | **85** | **1** |

- Between PR #60 and #72, Cristofer merged 7 and Jhampier 6. From #73 to #88, Jhampier merged all 16.
- The Git history does not include GitHub reviews or approvals, so it does not allow cross review to be confirmed.

### 6.4 Definition of Ready (DoR)

**Proposal.** A user story is ready for development when:

- it is written in the **As a / I want / so that** format;
- it has at least **two acceptance criteria** in the **Given / When / Then** format;
- its dependencies are resolved (merged into `develop` or agreed);
- if it requires new endpoints, its **OpenAPI contract** is defined before starting.

### 6.5 Definition of Done (DoD)

**Proposal.** An item is done when:

- the pull request is approved by the other member;
- the tests do not reduce the existing coverage;
- the Jenkins pipeline finishes without errors;
- the affected documentation is updated (README, OpenAPI, data model or architecture decision records);
- if the team enables a *staging* environment, the deployment to that environment passes the *smoke test*. The repositories contain no evidence of such an environment.

---

## 7. Proposed Procedure for Changes and Task Reassignment

> **Nature of this section:** proposal (see section 6).

| Situation | Proposed procedure |
|---|---|
| A member cannot complete a task | They notify the team. The other member takes it over temporarily and the change is recorded in the pull request or the commit. |
| Defect in the other member's code | A `fix/<description>` branch is created with its pull request, which the original author reviews. |
| Scope change that affects both | It is discussed in the team channel and recorded in the pull request or in an *issue*. |
| Change that affects the documentation | `TuEvento-Docs` is updated with a commit in Conventional Commits format. Currently Jhampier centralizes the file uploads (section 2.3). |
| Permanent reassignment of a module | It is recorded in a new version of this document, the RACI matrix is updated and the instructor is informed. |

---


*Version 1.0 · October 23, 2026 · CapySoft Team · SENA Cohort (Ficha) 3145556*
