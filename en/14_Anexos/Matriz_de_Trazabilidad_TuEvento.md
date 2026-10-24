---
id: TE-0164
title: "Matriz_de_Trazabilidad_TuEvento"
lang: en
source: 11_Anexos/Matriz_de_Trazabilidad_TuEvento.pdf
source_sha256: f9851d363790ea9e04932d42629615411bd47825b5125cba4c97c11ff800ebcf
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–6: «Matriz de Trazabilidad - Tu Evento Pagina {n}»."
  - "PDF generated without LaTeX: hyphens at the end of a line are real hyphens and are kept when joining lines (they are not syllabic line-break hyphens)."
  - "10 ReportLab bullets without a Unicode mapping (Helvetica code 127, «(cid:127)» in the extraction) written as «•», which is how they look in the original."
  - "Cover page: highlighted lines that are not the title are written as paragraphs: «Propósito»; «Referencias de repositorios»; «Estructura del código fuente»."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
  - "Translation: the code blocks of the source-code structure and of the traceability chain are kept as in the original (their Spanish comments are not translated); file names are not translated either."
status: borrador
reviewed_by: ""
translation_of: es/14_Anexos/Matriz_de_Trazabilidad_TuEvento.md
es_sha256: 460e87adc18893c5022afd20c7f2277f0f8f97dd3893460c128cd702bec5840b
---
# Traceability Matrix — Tu Evento Training Project

| **Field** | **Detail** |
|---|---|
| **Project** | Tu Evento |
| **Programme / Ficha** | Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development) — Ficha (training group) 314556 (2026) |
| **Team members** | Jhampier Santos Ortiz · Cristofer David Lozano Contreras |
| **Update date** | October 2026 |

**Purpose**

This document relates each requirement/user story to the modules implemented in the source code (backend, web frontend and mobile application) and to the tests that validate them, making it possible to verify that everything specified was designed, built and tested.

**Repository references**

| **Repository** | **URL** |
|---|---|
| **Documentation** | https://github.com/TheJhampierBoy/TuEvento-Docs |
| **Source code (Backend + Web Frontend + Mobile)** | https://github.com/lozano2303/tu-evento |
| **User stories** | Historias_Usuario_TuEvento.docx |
| **SRS** | Manual SRS Tu Evento.docx |
| **Test cases** | Casos_de_Prueba_TuEvento.xlsx |

**Source code structure**

| `lozano2303/tu-evento` `\|-- TuEventoBackend/ -> API REST (Spring Boot / Java)` ``\| `-- src/main/java/TuEvento/Backend/`` `\| \|-- controller/ -> Controladores REST (endpoints)` `\| \|-- service/ -> Logica de negocio` `\| \|-- model/ -> Entidades / modelos de datos` `\| \|-- repository/ -> Acceso a datos (JPA)` `\| \|-- dto/ -> Objetos de transferencia` `\| \|-- jwt/ -> Seguridad / autenticacion JWT` ``\| `-- config/ -> Configuracion general`` `\|-- TuEventoFrontend (Web)/ -> Frontend web (React + Vite)` ```-- TuEventoFrontend (Mobile)/ -> App movil (React Native + Expo)`` ```-- src/`` `\|-- screens/auth/ -> Pantallas de autenticacion` `\|-- screens/home/ -> Pantallas principales` `\|-- api/ -> Llamadas a la API` `\|-- components/ -> Componentes reutilizables` `\|-- navigation/ -> Navegacion` ```-- constants/ -> Constantes globales`` |
|---|

## Traceability Matrix

#### Table conventions

- **RF =** Functional Requirement
- **HU =** User Story
- **BE =** Backend (TuEventoBackend)
- **Web =** Web Frontend (TuEventoFrontend Web)
- **Mob =** Mobile App (TuEventoFrontend Mobile)
- **CP =** Test Case (evidence in `06_Pruebas/Backend/)`
### Module 1 — User Registration and Authentication

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-01 / HU-01** | The user can register with email and password | `RegisterController.java ·` `RegisterService.java · User.java ·` `AccountActivation.java` | screens/auth/RegisterScreen.tsx | RegisterController.pdf |
| **RF-02 / HU-01** | Account verification by email | `AccountActivationController.java ·` `AccountActivationService.java` | screens/auth/CodeVerificationScreenR egister.tsx | AccountActivationController.pdf · AccountActivationEmailController.pdf |
| **RF-03 / HU-02** | The user can log in with JWT | `LoginController.java · LoginService.java ·` `jwt/ · Login.java` | screens/auth/LoginScreen.tsx | LoginController.pdf |
| **RF-04 / HU-02** | Password recovery by email | `RecoverPasswordService.java ·` `RecoverPassword.java · controller/email/` | screens/auth/ForgotPasswordScreen.ts x · CodeVerifcationForgotPassword.tsx · NewPasswordScreen.tsx | — |

### Module 2 — User and Profile Management

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-05 / HU-03** | Consult and update the user profile | `UserController.java · UserService.java ·` `User.java` | screens/home/ProfileScreen.tsx · Web Frontend (profile) | UserController.pdf |
| **RF-06 / HU-03** | Management of the user's address | `AddressController.java ·` `AddressService.java · Address.java` | Web Frontend | AddressController.pdf |
| **RF-07 / HU-04** | Request to become an organizer | `OrganizerPetitionController.java ·` `OrganizerPetitionService.java ·` `OrganizerPetition.java` | Web Frontend | OrganizerPetitionController.pdf |

### Module 3 — Event Management

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-08 / HU-05** | Create, edit and delete events | `EventController.java · EventService.java ·` `Event.java` | Web Frontend (organizer dashboard) | EventController.pdf |
| **RF-09 / HU-05** | Management of event images | `EventImgController.java ·` `EventImgService.java · EventImg.java ·` `StorageController.java` (AWS S3) | Web Frontend | EventImgController.pdf · StorageController.pdf |
| **RF-10 / HU-05** | Configure the layout (seat map) of the event | `EventLayoutController.java ·` `EventLayoutService.java · EventLayout.java` | Web Frontend | EventLayoutController.pdf |
| **RF-11 / HU-06** | Discover and filter events by category | `CategoryController.java ·` `CategoryService.java ·` `CategoryEventController.java ·` `Category.java · CategoryEvent.java` | screens/home/EvenListScreen.tsx · Web Frontend | CategoryController.pdf · CategoryEventController.pdf |
| **RF-12 / HU-06** | Rate an event | `EventRatingController.java ·` `EventRatingService.java · EventRating.java` | Web Frontend · Mobile App | EventRatingController.pdf |

### Module 4 — Location and Geolocation

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-13 / HU-07** | Associate a physical location with an event | `LocationController.java ·` `LocationService.java · Location.java ·` `Address.java` | Web Frontend | LocationController.pdf |
| **RF-14 / HU-07** | Management of cities and departments | `CityController.java · CityService.java ·` `DepartmentController.java ·` `DepartmentService.java · City.java ·` `Department.java` | Web Frontend | CityController.pdf · DepartmentController.pdf |

### Module 5 — Seats, Sections and Tickets

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-15 / HU-08** | Configure the sections of the event | `SectionController.java ·` `SectionService.java · Section.java ·` `SectionNameController.java ·` `SectionName.java` | Web Frontend | SectionController.pdf |
| **RF-16 / HU-08** | Manage seats by section | `SeatController.java · SeatService.java ·` `Seat.java · SeatTicket.java` | Web Frontend | SeatController.pdf |
| **RF-17 / HU-09** | Buy a ticket and reserve a seat | `TicketController.java · TicketService.java ·` `Ticket.java · SeatTicket.java` | Web Frontend · Mobile App | TicketController.pdf |

### Module 6 — Notifications

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-18 / HU-10** | Send and receive system notifications | `NotificationController.java ·` `NotificationService.java ·` `Notification.java · NotificationUser.java ·` `NotificationUserService.java` | Web Frontend · Mobile App | NotificationController.pdf |

### Module 7 — QR Check-in

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-19 / HU-11** | Validate entry to the event with a QR code | `TicketController.java` (validation endpoint) · `Ticket.java` | screens/home/readerQr.tsx | TicketController.pdf · mobile.pdf |

### Module 8 — Cloud Storage (AWS)

| **RF / HU ID** | **Requirement description** | **Backend Component** | **Frontend/Mobile Component** | **Associated test** |
|---|---|---|---|---|
| **RF-20 / HU-12** | Upload and manage files and images in AWS S3 | `StorageController.java · service/aws/ ·` `service/impl/` | Web Frontend (image upload) | StorageController.pdf |

## Coverage summary

| **Module** | **Implemented controllers** | **Available tests** | **Implemented screens** |
|---|---|---|---|
| **Registration and authentication** | 3 (Register, AccountActivation, Login) | 3 PDFs | 6 auth screens (mobile) |
| **User management** | 3 (User, Address, OrganizerPetition) | 3 PDFs | ProfileScreen (mobile) + Web |
| **Event management** | 5 (Event, EventImg, EventLayout, Category, EventRating) | 5 PDFs | EvenListScreen (mobile) + Web |
| **Location and geolocation** | 3 (Location, City, Department) | 3 PDFs | Web |
| **Seats, sections and tickets** | 4 (Section, SectionName, Seat, Ticket) | 4 PDFs | Web + Mobile |
| **Notifications** | 1 (Notification) | 1 PDF | Web + Mobile |
| **QR check-in** | 1 (Ticket - validation) | readerQr.tsx + mobile.pdf | readerQr.tsx (mobile) |
| **AWS storage** | 1 (Storage) | 1 PDF | Web |
| **Total** | **21 controllers** | **21 test PDFs** | **3 platforms** |

## Complete traceability chain

| `SRS / Historias de Usuario` `\|` `v` `Analisis (diagramas de clases, casos de uso)` `\|` `v` `Diseno (arquitectura, DER, patrones, SQL)` `\|` `v` `Codigo fuente` `\|-- Backend: model -> repository -> service -> controller` `\|-- Web: TuEventoFrontend (Web)` ```-- Mobile: TuEventoFrontend (Mobile) / src/screens`` `\|` `v` `Pruebas (Plan, Casos de prueba, evidencias por controlador, mobile)` `\|` `v` `Acciones correctivas y mejora` |
|---|

## Remarks

- The user stories with an exact ID (HU-XX) must be verified in Historias_Usuario_TuEvento.docx to cross-check the correct number with each RF.
- The Web Frontend does not have a screens folder listed explicitly in the repository (it uses React + Vite); its coverage is verified at the level of deployed functionality.
- The tests of the mobile app are consolidated in mobile.pdf.
- Each test PDF in `06_Pruebas/Backend/` corresponds exactly to one backend controller, covering the 21 implemented controllers.
*Document updated in October 2026. Update it when new modules, branches or versions are added to the repository.*
