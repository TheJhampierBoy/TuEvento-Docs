---
title: "General project document"
lang: en
documents: [TE-0004, TE-0009, TE-0010, TE-0017, TE-0001]
status: borrador
---
# General project document — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Project scope](#doc-te-0004)
2. [Selected methodology](#doc-te-0009)
3. [Scrum planning (timeline)](#doc-te-0010)
4. [Tu Evento S.A.S. — business document](#doc-te-0017)
5. [Cost analysis](#doc-te-0001)

---

<a id="doc-te-0004"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Alcance_Proyecto_TuEvento.md
id: TE-0004
title: "Alcance_Proyecto_TuEvento"
lang: en
source: 01_Especificacion_Requisitos/Alcance_Proyecto_TuEvento.docx
source_sha256: aa16d4f223c9d48a7fdeec5b3124c376fe6a690b174523fa2fa53b81824429af
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the anchors of the table of contents links are translated with the same convention as in the Spanish version (heading text without its number), so that they point to the English headings."
status: borrador
reviewed_by: ""
translation_of: es/01_Documento_General_Proyecto.md#doc-te-0004
es_sha256: 158253375e36fe861ff3dfa97b53b2ce6599207eec4cd1273e024990eb21ff0a
-->

# Project scope

**CapySoft**

*Development Team — Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development)*

**PROJECT SCOPE DOCUMENT**

**Project: TuEvento**

Version 1.0

|  |  |
|:--:|:--:|
| **Field** | **Detail** |
| **Development Team** | CapySoft |
| **Project** | TuEvento |
| **Document** | Project Scope |
| **Version** | 1.0 |
| **Ficha (training group)** | 3145556 |
| **Team members** | Jhampier Santos Ortiz Cristofer David Lozano Contreras |

# **2. Version Control**

|  |  |  |  |
|:--:|:--:|:--:|:--:|
| **Version** | **Date** | **Description of the change** | **Author(s)** |
| 1.0 | July 2026 | Initial preparation of the TuEvento Project Scope Document, based on the SRS version 1.0. | Jhampier Santos Ortiz, Cristofer David Lozano Contreras |

# **3. Table of Contents**

[**2. Version Control** [2](#version-control)](#version-control)

[**3. Table of Contents** [3](#table-of-contents)](#table-of-contents)

[**4. Introduction** [4](#introduction)](#introduction)

[**5. General Objective** [4](#general-objective)](#general-objective)

[**6. Specific Objectives** [4](#specific-objectives)](#specific-objectives)

[**7. Project Scope** [4](#project-scope)](#project-scope)

[**7.1 General description of the system** [4](#general-description-of-the-system)](#general-description-of-the-system)

[**7.2 What the project includes** [5](#what-the-project-includes)](#what-the-project-includes)

[**7.3 Modules that will be developed** [5](#modules-that-will-be-developed)](#modules-that-will-be-developed)

[**7.4 Participating actors** [5](#participating-actors)](#participating-actors)

[**7.5 Processes covered by the system** [5](#processes-covered-by-the-system)](#processes-covered-by-the-system)

[**8. Included Features** [6](#included-features)](#included-features)

[**9. Features Out of Scope** [7](#features-out-of-scope)](#features-out-of-scope)

[**10. Project Deliverables** [8](#project-deliverables)](#project-deliverables)

[**11. Project Constraints** [8](#project-constraints)](#project-constraints)

[**12. Project Assumptions** [9](#project-assumptions)](#project-assumptions)

[**13. Scope Acceptance Criteria** [9](#scope-acceptance-criteria)](#scope-acceptance-criteria)

[**14. Conclusions** [9](#conclusions)](#conclusions)

<a id="introduction"></a>

# **4. Introduction**

The purpose of this document is to formally establish the Scope of the "TuEvento" Project, developed by the company CapySoft, taking as its sole basis the information contained in the project's Software Requirements Specification (SRS) document, version 1.0.

The Project Scope clearly and precisely delimits which features, modules, actors and processes will be addressed during the development of the system, as well as the aspects that are explicitly excluded. This document constitutes a fundamental tool for project management, since it makes it possible to align the expectations of the stakeholders, avoid the uncontrolled expansion of requirements (scope creep) and establish objective criteria to determine when the project is considered completed.

The "TuEvento" project corresponds to a comprehensive platform, in web and mobile versions, aimed at the creation, administration and operation of events, allowing organizers to manage floor plans, seats and reservations, and attendees to view, reserve and acquire tickets securely.

# **5. General Objective**

To define and delimit the scope of the "TuEvento" project, specifying the features, modules, actors and processes that will be developed based on the Software Requirements Specification (SRS) document, in order to guarantee efficient project management and clear communication among all the stakeholders.

# **6. Specific Objectives**

- Delimit the included and excluded features of the "TuEvento" project, in accordance with the functional and non-functional requirements established in the SRS.

- Identify the modules, actors and processes that will be covered by the system in its web and mobile versions.

- Establish the formal deliverables of the project, including the software and the associated documentation.

- Determine the technical, technological and platform constraints that condition the development of the system.

- Define the acceptance criteria that will make it possible to validate compliance with the agreed scope.

<a id="project-scope"></a>

# **7. Project Scope**

## **7.1 General description of the system**

"TuEvento" is a web and mobile application developed by CapySoft, whose objective is to provide organizers and attendees with a comprehensive tool for planning, managing and participating in events. The product will be developed under a modular architecture oriented to microservices, with a backend based on a RESTful API developed in Java (version 21) with Spring Boot, and a PostgreSQL relational database (version 17) managed through Spring Data JPA. The security of the system is based on authentication through JWT and Refresh Token.

The web version allows organizers to design the layout of floor plans, configure seats, publish events, manage sales and control attendance through the validation of QR codes. The mobile version (Android and iOS) allows attendees to view events, select and buy tickets through the sandbox payment gateway, intended for testing the payment flow, receive push notifications, access their digital tickets and scan QR codes to validate their entry.

## **7.2 What the project includes**

- User management: registration, login and logout, authentication with JWT and Refresh Token, password recovery and change, account creation and deletion, profile customization, and optional linking with social networks in the web version.

- Event management: creation, editing, deletion and publication of events by organizers, including the layout design of the venue's floor plan from the web version, with the definition of prices, zones, seats and availability.

- Reservations, purchases and attendance: purchase of tickets from the mobile and web application, selection of seats from the available floor plan, generation of tickets with unique QR codes, attendance validation by reading the QR and integration with a sandbox payment gateway connected to the backend.

- User interaction: ratings and comments on events, push notifications, automatic reminders, an event sharing system, advanced search filters and configuration of notification preferences.

- Cross-platform compatibility: availability in a web version (Google Chrome and Microsoft Edge) and in mobile applications for Android and iOS, guaranteeing the viewing of events, the purchase of tickets, QR scanning and profile management on both platforms.

- Security: authentication based on JWT, Refresh Token system, credential validation, auditing of renewals and records, secure routing, protection through an API Gateway and role control.

## **7.3 Modules that will be developed**

Based on the functional requirements specified in the SRS, the project will develop the following modules: User Management, Administration Management, Event Management, Reservations and Attendance Control, Mobile Compatibility, Languages, Dashboard by Role, Session Security, Notifications, Payments, Architecture and Preferences/Customization (interface themes), Event Exploration and Digital Wallet. The detail of each module and its respective functional requirement is presented in section 8 of this document.

## **7.4 Participating actors**

|  |  |
|:--:|:--:|
| **Type of actor** | **Main activities** |
| **User (attendee)** | Reserve seats, comment on and rate events, create an account, deactivate the account, reset the password and choose events. |
| **User (anonymous, web only)** | Create an account, log in and search for events. |
| **Administrator** | View the users who want to become organizers, and accept or reject those requests. |
| **User (organizer)** | Create models (floor plans), save progress on the model design, view the history of created events and delete events already created. |

## **7.5 Processes covered by the system**

- Registration, verification, authentication and login/logout of users.

- Management and customization of the user profile, including password recovery and permanent account deletion.

- Validation and acceptance or rejection of requests from users who want to become organizers.

- Creation, layout design, editing and publication of the structure (floor plan) of the events by the organizers.

- Reservation and temporary blocking of seats, payment confirmation and generation of the QR codes associated with the reservation.

- Attendance validation by reading the QR code at the entry to the event.

- Payment processing through the sandbox payment gateway and balance management through the digital wallet system.

- Sending of push notifications and automatic reminders to users.

- Viewing, searching and filtering of events, as well as rating and commenting on them.

- Presentation of differentiated dashboards according to the user's role (attendee, organizer or administrator).

# **8. Included Features**

The modules and functional requirements (RF) defined in the SRS that will be developed within the scope of the "TuEvento" project are summarized below.

|  |  |  |
|:--:|:--:|:--:|
| **Module** | **Code** | **Feature** |
| User Management | **RF1** | User registration |
| User Management | **RF2** | Authentication with social networks (OAuth) |
| User Management | **RF3** | User login |
| User Management | **RF4** | Profile management and customization |
| User Management | **RF5** | Recover password |
| User Management | **RF6** | Log out |
| User Management | **RF7** | Permanent account deletion |
| Administration Management | **RF8** | System administration module (validation of organizer requests) |
| Event Management | **RF9** | Editing and layout design of the event structure |
| Reservations and Attendance Control | **RF10** | Seat reservation |
| Reservations and Attendance Control | **RF11** | Generation and validation of a QR code per reservation |
| Mobile Compatibility | **RF12** | Functionality on iOS devices |
| Languages | **RF13** | Multi-language support (ES/EN/PT/JA) |
| Dashboard | **RF14** | Dashboard by role (attendee, organizer and administrator) |
| Session Security | **RF15** | Refresh Token system |
| Notifications | **RF16** | Push notification system |
| Payments | **RF17** | Sandbox payment gateway with the Strategy pattern |
| Mobile Functionality | **RF18** | Purchase of tickets from the mobile application |
| Architecture | **RF19** | Layout design and management of events from the web version |
| Preferences and Customization | **RF20** | Microservice-oriented architecture |
| Preferences and Customization | **RF21** | Migration of the backend to an N-tier architecture with DDD |
| Theme Customization | **RF22** | Interface theme system (light, dark, purple, blue) |
| Event Exploration | **RF23** | Event filters |
| Attendance Control | **RF24** | QR code reader for attendance validation |
| Wallet | **RF25** | Digital wallet system (compensatory balance) |

In addition, the system must comply with the following non-functional requirements (RNF) defined in the SRS:

|  |  |  |
|:--:|:--:|:--:|
| **Code** | **Name** | **Description** |
| **RNF1** | Error messages | The system must show uniform error messages when the user enters data incorrectly or performs a procedure incorrectly. |
| **RNF2** | Responsive design | The design of the system must be displayed correctly from any device, whether a computer or a telephone. |
| **RNF3** | Security | Users must identify themselves through secure authentication mechanisms (email and password, and two-step authentication when applicable). |
| **RNF4** | Usability | The system must offer a friendly and intuitive interface that makes it possible to perform basic tasks without a steep learning curve. |
| **RNF5** | Compatibility | The system must be compatible with the main web browsers (Google Chrome) and with Android devices. |

# **9. Features Out of Scope**

In accordance with what is explicitly established in the SRS, the following features will not be developed within this project:

- The system will not implement live streaming of events or features related to augmented reality or virtual reality.

- An environment for creating or editing floor plans from the mobile application will not be developed; seat layout design will remain exclusive to the web version.

- An advanced dashboard for the detailed organization of events from mobile will not be offered; all the advanced administrative functions will be available only on the web platform.

- The system will not integrate real payment gateways; the payment is simulated. Stripe, PayPal and MercadoPago are out of scope in this version.

- Internal messaging services between users or real-time chat will not be implemented.

- Advanced customization of the purchase flow by the organizer (dynamic rules, special filters, customized templates) is not contemplated in this version.

- Support for multiple currencies, international payments or automatic currency conversion will not be included.

- The system will not offer advanced marketing tools, such as email automation, advertising segmentation or integrated promotional campaigns.

- Integration with social networks will be limited only to login and authentication; automatic publication of events or sharing content directly from the application is not contemplated.

- The platform will not manage exclusive presales, VIP memberships or advanced special access beyond what is defined in the functional requirements.

# **10. Project Deliverables**

The deliverables of the "TuEvento" project, supported by what is described in the SRS, are the following:

- Functional web application, compatible with the Google Chrome and Microsoft Edge browsers.

- Functional mobile applications for the Android (version 11 or later) and iOS operating systems.

- Backend developed as a RESTful API in Java (version 21) with Spring Boot, oriented to microservices.

- Relational database in PostgreSQL (version 17), designed under the Third Normal Form (3NF) schema.

- Software Requirements Specification (SRS) document, version 1.0.

- Project Scope Document (this document).

# **11. Project Constraints**

- Connectivity: the system requires an internet connection for all of its operations to work.

- Availability by platform: in the web version, the system must be compatible with modern Chromium-based browsers (Google Chrome and Microsoft Edge) and with Windows operating systems; in the mobile version, it must be available for Android (version 11 or later) and iOS, with equivalent features as defined in the functional requirements.

- Limitations in the mobile version: the mobile application will not allow designing the layout of events; it will only allow viewing events, selecting available seats, buying tickets and scanning QR codes (in the case of being an organizer).

- Security: all communication between client and server must be carried out ensuring the protection of the data through authentication and authorization mechanisms based on JWT.

- Access without authentication: the web version will allow events to be viewed without the need to log in.

- Payment gateway: the system will only integrate a sandbox payment gateway, without support for real payment platforms in this version.

- Backend and database technology: the backend will be developed in Java 21 with Spring Boot, and the database will use PostgreSQL 17 through Spring Data JPA.

# **12. Project Assumptions**

- It is assumed that users will have access to a stable Internet connection to use all the functions of the system.

- Users are expected to have basic skills in the use of computers and mobile devices, including browsing the Internet.

- The availability and correct operation of the external email service (SMTP) for sending notifications and verification codes is assumed.

- The operational availability of the sandbox payment gateway for processing the system's transactions is assumed.

# **13. Scope Acceptance Criteria**

The scope of the "TuEvento" project will be considered fulfilled when the following conditions are verified:

- All the functional requirements (RF1 to RF25) defined in the SRS have been implemented and validated according to their development priority.

- The non-functional requirements (RNF1 to RNF5) related to error messages, responsive design, security, usability and compatibility have been met.

- The web version is operational in the Google Chrome and Microsoft Edge browsers, including the layout design and management of events by the organizers.

- The mobile versions for Android and iOS are operational, allowing the viewing of events, the purchase of tickets, the selection of seats and the scanning of QR codes.

- The process of reservations, payments through the sandbox gateway and generation/validation of QR codes works correctly and consistently on both platforms.

- The excluded features, listed in section 9 of this document, are not part of the delivered version of the system.

# **14. Conclusions**

This Project Scope Document precisely establishes the functional and technical limits of the "TuEvento" project, based exclusively on the information contained in the SRS version 1.0. The correct delimitation of the scope constitutes a determining factor for the success of the project, since it makes it possible to direct the efforts of the development team, adequately manage the expectations of the stakeholders and establish an objective basis for evaluating the fulfilment of the stated objectives.

Adopting this document as a formal reference throughout the life cycle of the project will help minimize the risks associated with the uncontrolled expansion of the scope (scope creep), thus facilitating an efficient and coherent delivery aligned with the defined requirements.


---

## Headers and footers of the original

- **Footer** (`word/footer1.xml`): text «Página {PAGE} de {NUMPAGES}»
- **Header** (`word/header1.xml`): text «CapySoft — TuEvento — Alcance del Proyecto v1.0»

---

<a id="doc-te-0009"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Metodologia_Seleccionada.md
id: TE-0009
title: "Metodología Seleccionada"
lang: en
source: 01_Especificacion_Requisitos/Metodología Seleccionada.docx
source_sha256: f56cc4bf712c00fc18019401a27abd1a8529c7705f820644c574733997bf0fdb
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles (everything is 'NormalWeb'); the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page."
  - "Translation: the name of the training centre («Centro de la industria, la empresa y los servicios») is kept in Spanish because it is a proper name."
status: borrador
reviewed_by: ""
translation_of: es/01_Documento_General_Proyecto.md#doc-te-0009
es_sha256: 26245f0920e380af2de4f4a7c79dbf07a4109cf90a055152e7a3adf285918e5f
-->

# Selected methodology

Plan Analysis Activities

According to the Selected Methodology

(SCRUM)

CapySoft – Development Team

Cristofer David Lozano Contreras

Jhampier Santos Ortiz

Centro de la industria, la empresa y los servicios

Servicio Nacional De Aprendizaje (National Learning Service)

SENA

10/09/2025

**Plan Analysis Activities According to the Selected Methodology**

**Introduction**

The planning of analysis activities is an essential stage for the development of logical projects, since it makes it possible to define a clear work plan, organize resources and guarantee that the objectives are met. In the case of Tu Evento, we intend to offer an innovative platform for the organization and customization of events thanks to interactive floor plans; the choice of an agile method is fundamental to respond to technological developments and user demands.

The analysis of the problem shows that the different platforms have limits regarding the customization of space, which affects organizers and participants. Given this situation, an approach that favours interaction, continuous feedback and progressive improvement is necessary.

In this context, the SCRUM methodology is the most suitable, where the project is divided into sprints that allow the progressive release of value, the constant validation of progress and active communication between the team and the parties present. This document explains why SCRUM is used in the planning of the analysis activities of Tu Evento, also establishing a solid methodological basis to obtain a flexible and interactive solution adapted to the users' attendees.

**Why use SCRUM**

The selection of the SCRUM methodology as the framework for the Tu Evento project responds to the need to adopt an agile approach that makes it possible to face the challenges inherent in the development of software oriented to event management. SCRUM offers significant advantages over traditional methodologies, since it is designed to work in changing environments, where requirements can evolve as the product is built.

First, SCRUM guarantees adaptability to change, which is essential in a project such as Tu Evento, where feedback from users and organizers can modify or extend the features initially planned.

Second, it promotes the incremental delivery of value, since development is organized in short cycles called sprints. In each sprint, tangible results are generated that allow the stakeholders to see the progress and make timely adjustments.

In addition, it encourages effective team collaboration, ensuring constant communication between developers, designers and stakeholders. This collaborative approach reduces misunderstandings and strengthens the alignment of the whole team with the project objectives.

**Why we use SCRUM in Tu Evento**

The *Tu Evento* project is developed in a highly complex context, in which the main challenge is to overcome the limitations of current event management platforms. The need to offer complete customization of spaces and interactive seat selection demands a methodology that provides order, flexibility and adaptability.

SCRUM responds to these demands by offering an agile framework that makes it possible to face the uncertainty of the project and maintain a constant delivery of value. Thanks to its iterative structure, each development cycle ensures that the results can be validated and adjusted according to the expectations of both organizers and attendees.

In this sense, SCRUM not only facilitates the construction of an innovative technological solution, but also guarantees that the product evolves consistently with the real challenges and needs of the events market.

**What we use SCRUM for**

The central purpose of applying the SCRUM methodology in *Tu Evento* is to guarantee that development is carried out in an organized and agile way, centred on the end user.

It is used, first, to structure the planning of the analysis activities, ensuring that the requirements are clearly defined and that the team works on achievable and prioritized goals. Second, it is applied to encourage iterative and progressive execution, in which each partial delivery can be reviewed, receive feedback and be improved before moving on to the next phase.

Likewise, SCRUM allows efficient project management, by promoting transparent communication, early identification of risks and continuous improvement through retrospectives. With this, the team maintains a sustainable pace, minimizes errors and ensures the quality of the final product.

In conclusion, we use SCRUM so that *Tu Evento* is built under an agile process that combines flexibility with control, guaranteeing a reliable, innovative platform oriented to providing real value to both organizers and attendees.

**Conclusion**

The SCRUM methodology is consolidated as a strategic pillar for the development of the *Tu Evento* system, by providing a clear structure for the planning of analysis activities, promoting adaptability to change and ensuring the progressive delivery of value at each stage of the project. Its application not only organizes the work, but also strengthens team collaboration and the active participation of the *stakeholders*, essential factors for building a solution adjusted to real needs.

Thanks to this agile approach, *Tu Evento* can evolve dynamically, incorporating continuous improvements that guarantee an innovative, flexible and customizable platform. In this way, the objective is achieved of offering organizers an efficient tool to design spaces adapted to their requirements, and attendees an interactive, intuitive experience with high added value.


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): no text<br>![Header of the original](../_assets/01_Especificacion_Requisitos/Metodologia_Seleccionada/header_footer/image1.jpeg)

---

<a id="doc-te-0010"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Planificaion_Scrum_TimeLine.md
id: TE-0010
title: "Planificaion Scrum (TimeLine)"
lang: en
source: 01_Especificacion_Requisitos/Planificaion Scrum (TimeLine).pdf
source_sha256: 058111931bd50d452fe2e6c91b0e355d24965ca91c0db6ca37177c9cbdd239a9
conversion: "pdfplumber 0.11.10 (text boxes) + page image at 100 dpi; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Design PDF (Canva): the text is grouped by text boxes (nearby lines that overlap) and ordered from top to bottom and from left to right; the reading order of the composition may differ and the image of each page is the faithful reference."
  - "Each visual line break inside a box is kept with <br>."
  - "Layout, colours, typefaces, shapes, arrows and decorative images are only in the image of each page (100 dpi)."
  - "The Canva characters are not linked to the tag tree of the PDF, so the tagged PDF method is not used."
  - "Translation: the line breaks (<br>) of the Spanish text are kept at approximately the same position; in English they do not match the line ends of the original."
  - "Translation: the text inside the page image is not translated."
  - "Translation: the original spelling «Mokup» is kept."
status: borrador
reviewed_by: ""
translation_of: es/01_Documento_General_Proyecto.md#doc-te-0010
es_sha256: 7df96af3be5c02dbd67a02da1850bddf5451bb07100b1e01fbefd290fb5f10e2
-->

# Scrum Planning (TimeLine)

## Page 1

![Page 1 of the original](../_assets/01_Especificacion_Requisitos/Planificaion_Scrum_TimeLine/pagina-1.png)

Scrum Planning

TU EVENTO

DOCUMENTATION AND<br>
PLANNING.

DOCUMENTATION AND<br>
MOKUP.

DOCUMENTATION,<br>
MOKUP AND<br>
ARCHITECTURE.

BACKEND<br>
DEVELOPMENT.

DEVELOPMENT OF THE<br>
BACKEND AND THE<br>
WEBSITE.

DEVELOPMENT OF THE<br>
ADAPTATION TO THE<br>
MOBILE APP.

DEVELOPMENT AND<br>
TESTING.

REVIEW,<br>
CORRECTION AND<br>
FINAL DELIVERY.

The documentation<br>
and the Mokup are<br>
completed in this<br>
sprint. Backend<br>
development<br>
continues and the<br>
development of the<br>
website begins,<br>
creating the first<br>
views and the<br>
integration with the APIs.

The three development<br>
branches<br>
(backend, website<br>
and mobile app)<br>
will be about to<br>
be completed. The<br>
initial integration<br>
tests are carried out<br>
to ensure that<br>
the whole system<br>
works.

The reviews and<br>
corrections<br>
begin. We will<br>
dedicate ourselves<br>
to fixing errors,<br>
optimizing<br>
performance and<br>
preparing the<br>
deliverables for the<br>
final delivery of the<br>
project.

The documentation tasks<br>
begin,<br>
focused on the<br>
requirements<br>
specification and the<br>
basis of the project.

The documentation<br>
continues. The<br>
Mokup phase begins,<br>
with the design of<br>
prototypes and the<br>
user interface<br>
in Figma.

Progress is made on the<br>
documentation and the<br>
Mokup. The definition<br>
of the technical<br>
architecture<br>
of the system<br>
and the design of the<br>
database begins.

The development<br>
of the backend<br>
begins,<br>
implementing the<br>
MVC architecture.<br>
The documentation and<br>
Mokup activities<br>
continue.

The adaptation<br>
to the mobile app<br>
begins. The development<br>
of the backend and the<br>
website progress<br>
in parallel.

FIRST SPRINT

SECOND SPRINT

THIRD SPRINT

FOURTH SPRINT

FIFTH SPRINT

SIXTH SPRINT

SEVENTH SPRINT

EIGHTH SPRINT

MARCH

APRIL

MAY

JUNE

JULY

AUGUST SEPTEMBER OCTOBER

---

<a id="doc-te-0017"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Tu_evento_SAS.md
id: TE-0017
title: "Tu evento SAS"
lang: en
source: 01_Especificacion_Requisitos/Tu evento SAS.docx
source_sha256: 39d0d12b6c82f51eab3f842e0d2581252ba4b96694691332cb7c80ba5dba027f
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the destinations of the table of contents links (#informaci%C3%B3n-corporativa…) are kept as in the Spanish version; only the visible text is translated."
  - "Translation: the text inside the organization chart image is not translated."
status: borrador
reviewed_by: ""
translation_of: es/01_Documento_General_Proyecto.md#doc-te-0017
es_sha256: e998127d9cf35de12da5054737351e7dd683ff4d8fa0900afcdd3a20806073d8
-->

# Tu Evento S.A.S. — business document

**TU EVENTO S.A.S**

Event Management and Digital Ticketing

Comprehensive Business Document Organizational Structure and

Technological Dependencies

Date: September 2025\
Version: 1.0\
Prepared by: General Management

CONTENTS

1.  [Corporate Information](#informaci%C3%B3n-corporativa)

2.  [Organizational Structure](#estructura-organizacional)

3.  [Description of Functional Areas](#descripci%C3%B3n-de-%C3%A1reas-funciona)

4.  [Critical Software Modules](#m%C3%B3dulos-de-software-cr%C3%ADticos)

5.  [Conclusions and Recommendations](#conclusiones-y-recomendaciones)

**CORPORATE INFORMATION**

**Company Name:**

Tu Evento S.A.S.

**Type of Company:**

Sociedad por Acciones Simplificada (simplified joint-stock company) dedicated to the comprehensive management of events and digital ticketing.

**Mission**

To facilitate the organization of and attendance at events through a modern technological platform, providing innovative tools that simplify the experience for both organizers and attendees.

**Vision**

To be the leading platform in Latin America for the comprehensive management of events and attendees, recognized for our technological excellence, customer service and contribution to the growth of the events industry.

Corporate Values

Innovation: Continuous development of cutting-edge technological solutions

Reliability: Guarantee of optimal operation at critical events

Accessibility: Ease of use for all users

Transparency: Clear and honest communication with clients and stakeholders

**ORGANIZATIONAL STRUCTURE**

The company has a functional organizational structure designed to optimize operational efficiency and specialization by areas of competence.

<img src="../_assets/01_Especificacion_Requisitos/Tu_evento_SAS/media/image1.png" style="width:6.12986in;height:1.80625in" alt="OrgChart_TuEvento" />

- **CEO**

The highest level. Responsible for the entire strategy of the company.

It is highlighted in light blue to mark its hierarchy.

- **Operations – in soft orange**

In charge of managing events, tickets, payment validation and support.

They are divided into:

**Organizers:** create and manage events.

**Support:** handle problems and inquiries.

**·Marketing** – in soft green

- **Area focused on promotion, communication and user engagement.**

It is made up of:

**Campaign Manager:** designs and executes campaigns.

**Community Manager:** manages networks and communities.

**IT & Development** (Technology and Development) – in soft violet

- **The area that supports the entire technological platform.**

Made up of:

**Software Engineers:** develop the platform.

**SysAdmin / DB Admin:** manage servers and databases.

**DESCRIPTION OF FUNCTIONAL AREAS**

**1. OPERATIONS**

Main Responsibilities:

Comprehensive management of the event life cycle

Administration of tickets and the ticketing system

Validation of payments and transactions

Access control and verification of attendees

Real-time monitoring of active events

Staff:

Organizers: Specialists in the creation, configuration and administration of events from their conception to their completion

Support: Team dedicated to resolving issues and providing technical assistance to users and organizers

Key Performance Indicators (KPIs):

Average event configuration time

First-contact issue resolution rate

Organizer client satisfaction

**2. MARKETING**

Main Responsibilities:

Development and implementation of promotional strategies

Management of automated communications

Administration of the presence on social networks

Analysis of user trends and behaviour

Optimization of digital campaigns

Staff:

Campaign Manager: Responsible for the design, execution and analysis of multichannel promotional campaigns

Community Manager: Specialist in managing digital communities, engagement and direct communication with users

Key Performance Indicators (KPIs):

Campaign open and conversion rate

Growth of the user base

Engagement on social networks

ROI of advertising campaigns

**3. IT & DEVELOPMENT (TECHNOLOGY AND DEVELOPMENT)**

Main Responsibilities:

Development and maintenance of the technological platform

Guarantee of information security and data protection

Optimization of performance and scalability

Implementation of new features

Management of technological infrastructure

Staff:

Software Engineers: Development team responsible for the programming, testing and deployment of technological solutions

SysAdmin / DB Admin (System and Database Administrators): Specialists in infrastructure, server maintenance and database management

Key Performance Indicators (KPIs):

System availability time (uptime)

Platform response time

Number of bugs reported vs resolved

Implementation time of new features

**CRITICAL SOFTWARE MODULES**

**1. CORE PLATFORM**

Function: Technological base that integrates all the modules

Criticality: HIGH - Without this module, operation stops completely

Dependents: All areas

**2. TICKETING & QR MODULE**

Function: Comprehensive management of tickets and access codes

Criticality: HIGH - Essential for the operation of events

Dependents: Operations mainly, Support secondarily

**3. NOTIFICATION SYSTEM**

Function: Automated multichannel communications

Criticality: MEDIUM-HIGH - Critical for retention and engagement

Dependents: Marketing mainly, Operations secondarily

**4. PAYMENT GATEWAY**

Function: Secure processing of financial transactions

Criticality: HIGH - Without payments there is no revenue

Dependents: Operations, indirectly all areas

**5. USER MANAGEMENT & SECURITY**

Function: Authentication, authorization and general security

Criticality: HIGH - Protects the entire platform

Dependents: IT & Development, all areas indirectly

**6. ANALYTICS & REPORTING**

Function: Business intelligence and operational metrics

Criticality: MEDIUM - Important for decision making

Dependents: Marketing and CEO mainly

**OPERATIONAL IMPACT ANALYSIS**

Critical Failure Scenarios

**1. Failure of the Ticketing Module:**

Impact: Impossibility of generating or validating tickets

Affected areas: Operations (100%), Support (80%), Marketing (30%)

Target recovery time: \< 15 minutes

Contingency plan: Manual backup system and emergency codes

**2. Failure of the Payment System:**

Impact: Total interruption of sales

Affected areas: Operations (100%), Marketing (70%), IT (100%)

Target recovery time: \< 5 minutes

Contingency plan: Automatic alternative payment processor

**3. Failure of the Notification System:**

Impact: Loss of communication with users

Affected areas: Marketing (90%), Operations (40%)

Target recovery time: \< 30 minutes

Contingency plan: Manual communication channels

Continuity Recommendations

Implementation of redundancy in critical modules

Proactive monitoring with automatic alerts

Regular testing of backup systems

Up-to-date documentation of emergency procedures

Continuous training of staff in contingency protocols

**CONCLUSIONS AND RECOMMENDATIONS**

Identified Strengths

Clear and specialized organizational structure

Precise definition of technological dependencies

Correct identification of critical modules

Adequate balance between operational and support areas

Opportunities for Improvement

Implement advanced monitoring systems to prevent failures

Develop interdependency metrics between areas

Create protocols for the automatic escalation of incidents

Establish internal SLAs between departments

Suggested Next Steps

Phase 1: Implementation of a unified monitoring dashboard

Phase 2: Development of integration APIs between modules

Phase 3: Automation of critical backup processes

Phase 4: Implementation of a predictive alert system

This document constitutes the basis for the comprehensive understanding of the operational and technological structure of Tu Evento S.A.S., providing the framework necessary for strategic decision making and the continuous optimization of processes.

Confidential document - Exclusive internal use of Tu Evento S.A.S.


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «0»<br>![Header of the original](../_assets/01_Especificacion_Requisitos/Tu_evento_SAS/header_footer/image2.png)

---

<a id="doc-te-0001"></a>

<!--
ruta_anterior: en/00_Informes/Analisis_de_Costos_TuEvento.md
id: TE-0001
title: "Analisis_de_Costos_TuEvento"
lang: en
source: 00_Informes/Analisis_de_Costos_TuEvento.pdf
source_sha256: 4006d0fd25d0ba572908fc683e35d2905f5a1210a11efa035598c82589027892
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–3: «{n}»."
  - "PDF generated without LaTeX: hyphens at the end of a line are real hyphens and are kept when joining lines (they are not syllabic line-break hyphens)."
  - "Cover page: highlighted lines that are not the title are written as paragraphs: «Proyecto Formativo Tecnólogo en Análisis y Desarrollo de Software “Tu Evento”»."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
  - "Translation: numbers keep the Spanish format (thousands separator «.», decimal separator «,»); for example, 1.750.905 COP is one million seven hundred fifty thousand nine hundred five pesos."
  - "Translation: the line breaks (<br>) of the Spanish text are kept at approximately the same position; in English they do not match the original line ends."
status: borrador
reviewed_by: ""
translation_of: es/01_Documento_General_Proyecto.md#doc-te-0001
es_sha256: 253526f19b77e860bdd9a1e529a7271c7e9769671b03f048929decaf70fba64b
-->

# Cost Analysis and Possible Remuneration for the Tu Evento Software

**Training Project, Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development), “Tu Evento”**

Team members:

Jhampier Santos Ortiz

Cristofer David Lozano Contreras

Sede de la Industria y los Servicios – Neiva, Huila

Ficha (training group): 3145556

October 2026

## Cost Analysis and Possible Remuneration for the Tu Evento Software

## Introduction

This document presents the cost analysis and explores, only as a possibility and without any agreement in this regard, an eventual remuneration for the software developed by a team of two apprentices, which includes a mobile application and a web application for managing events, users and ticket reservations, with cloud storage services.

## 1. Development cost

The team is made up of two apprentices (Jhampier Santos Ortiz and Cristofer David<br>
Lozano Contreras). The project lasts 12 months (October and November 2025,<br>
and January to October 2026; December 2025 was not worked due to holidays). The agreed<br>
salary is 1.750.905 COP per month. Table 1 details the cost.<br>
**Table 1**<br>
*Software development cost*

| **Role / Person** | **Time worked** | **Monthly payment (COP)** | **Total (COP)** |
|---|---|---|---|
| Apprentice 1 (Jhampier Santos Ortiz) | 12 months | 1.750.905 | 21.010.860 |
| Apprentice 2 (Cristofer David Lozano Contreras) | 12 months | 1.750.905 | 21.010.860 |
| Electricity and internet costs | 12 months | 200.000 | 2.400.000 |
| TOTAL | — | — | 44.421.720 |

The estimated total development cost, including electricity and internet, is 44.421.720 COP. This calculation does not include hosting or cloud storage costs.

## 2. Possible remuneration for the software

This section does not correspond to an agreement or a defined plan with the client; it is only a possible remuneration calculated from the development cost and the market value of similar solutions. On that basis, a reference figure could be around 70 million COP, which would be equivalent to a margin of approximately 58 % over cost. The estimated typical price range for software of this kind (mobile application, web, backend and cloud storage) in the Colombian market is 50 to 120 million COP.

The reference range, which has not been agreed, is between 50 and 70 million COP, depending on the level of support and customization that may eventually be defined.

## 3. Possible recurring remuneration channels

In addition to an eventual one-time remuneration for the software, there are business models that could be explored in the future, although none has been agreed so far, based on memberships, ticket commissions and additional services.

### *A. Monthly memberships*

Table 2 shows the reference ranges for organizer memberships.<br>
**Table 2**<br>
*Reference ranges for monthly memberships*

| **Plan** | **Monthly range (COP)** |
|---|---|
| Basic organizer | 150.000 – 250.000 |
| Pro organizer | 400.000 – 600.000 |

### *B. Ticket sales commissions*

A commission of 5 % would be charged per ticket sold. For example, if an event sells 1.000 tickets at 50.000 COP, the profit would be 2.500.000 COP in commissions.

## 4. Conclusion

The software development cost amounts to 44.421.720 COP. As a possible remuneration, and not as a defined agreement, a reference figure close to 70 million COP would be competitive in the market and would reflect the value of the work done and the functionality of the system. If membership or commission models were implemented in the future, the project could generate additional recurring revenue, although this has not yet been agreed.
