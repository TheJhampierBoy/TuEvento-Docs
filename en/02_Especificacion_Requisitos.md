---
title: "Requirements specification"
lang: en
documents: [TE-0016, TE-0007, TE-0005, TE-0006, TE-0011, TE-0008, TE-0015, TE-0012, TE-0014, TE-0013, TE-0019, TE-0018]
status: borrador
---
# Requirements specification — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Software requirements specification (SRS)](#doc-te-0016)
2. [User stories](#doc-te-0007)
3. [Functional requirements confirmation](#doc-te-0005)
4. [Requirements acceptance record](#doc-te-0006)
5. [Requirements presentation](#doc-te-0011)
6. [SRS evaluation report](#doc-te-0008)
7. [Data collection — survey](#doc-te-0015)
8. [Survey analysis](#doc-te-0012)
9. [Data collection — interview](#doc-te-0014)
10. [Interview analysis](#doc-te-0013)
11. [Technology watch](#doc-te-0019)
12. [Comparison table](#doc-te-0018)

---

<a id="doc-te-0016"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/SRS_Tu_Evento.md
id: TE-0016
title: "SRS_Tu_Evento"
lang: en
source: 01_Especificacion_Requisitos/SRS_Tu_Evento.pdf
source_sha256: 2bf89892d4c98fc91d67c97c45da27db6747045c9d9d83d9bf6da64c80605145
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Page header or footer omitted on pages 2–45: «Documento: Tu evento SRS | CapySoft, {n} Página {n} de {n}»."
  - "Page header or footer omitted on pages 2–45: «C o n f i d e n c i a l»."
  - "Page header or footer omitted on pages 1: «Tu evento»."
  - "Repeated header box (template with version, key and date) omitted on pages 2–45."
  - "Repeated template logo omitted on pages 2–45."
  - "Page 7: figure included as an image (pagina-07-figura-1.png); its text (35 words) goes in a non-visible HTML comment, grouped by box ([...]) from top to bottom and from left to right; arrows and relationships are only in the image."
  - "Page 10: figure included as an image (pagina-10-figura-1.png); its text (27 words) goes in a non-visible HTML comment, grouped by box ([...]) from top to bottom and from left to right; arrows and relationships are only in the image."
  - "Tables split across pages joined into a single one: 5→6; 12→13; 13→14; 14→15; 15→16; 16→17; 17→18; 18→19; 19→20; 20→21; 21→22; 22→23; 23→24; 24→25; 25→26; 26→27; 27→29; 29→30; 32→33; 33→34; 34→35; 35→36; 36→37; 37→38; 42→43; 44→45."
  - "Header row repeated by a page break omitted on pages 6, 43, 45."
  - "Manual table of contents (pages 3): the page numbers of the original are kept and the leader lines are removed."
  - "Cover page: highlighted lines that are not the title are written as paragraphs: «CapySoft»; «Versión 2.0»."
  - "Tables with merged cells in HTML (colspan/rowspan calculated from the geometry of the borders); column widths, backgrounds and border thickness are not kept."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 99.94%, precision 99.87%, order 99.75%; missing {'Descripción': 2, 'Término': 1, 'RF': 1, 'Sección': 1, 'Cambio': 1, 'Entidad': 1} (explained above)."
  - "Bullets: 447 drawn 3×3 pt squares (bullets) + 29 «•» characters = 476, the same as the Markdown; 26 arrowheads (pp. 7 and 10) and 1 3×3 dot inside the diagram on page 10 are not bullets."
  - "Requirement cards RF1-RF29: 29 of 29 with their 14 sections and the same words as the original; the ones that continue across pages are joined (including the Postcondition of RF17, which is a single-cell box on page 29)."
  - "Page 7: in an intermediate run the box «Clientes · Web · Android · iOS» was outside the crop and its text came out as a loose heading; the final version includes it (checked visually)."
  - "Translation: the status names written in uppercase in Spanish (PENDIENTE_PAGO, BLOQUEADA, CONFIRMADA, VÁLIDO, BORRADOR…) and the entity names of the data model (Usuario / Rol, SolicitudOrganizador, Sede…) are kept as in the original because they are identifiers of the specification."
  - "Translation: the interface texts and messages in quotation marks are translated and the Spanish literal is added in parentheses («…»), because the real English text of the interface is not known."
  - "Translation: the HTML comments with the text of the figures keep the original text and add the English translation after «EN:»; the text inside the figure images is not translated."
  - "Translation: some paragraphs keep the line division of the original; in English the line ends do not match those of the original."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0016
es_sha256: 40b76ee845fbed1c3b8137be3ad884adab9efc63074189070cf61d5fbc94dfdd
-->

# Requirements Specification

**CapySoft**

**Version 2.0**

# Revision History

| **Date** | **Version** | **Description** | **Author** |
|---|---|---|---|
| — | 1.0 | Initial version of the SRS of «Tu evento». | CapySoft |
| 09/10/2026 | 2.0 | Sandbox payment gateway with the Strategy pattern; correction of internal inconsistencies; new RF26 to RF29; alignment with the Web User Manual v3.1 (see Annex A). | CapySoft |

# Table of Contents

**1. Introduction 4**

1.1 Purpose 4

1.2 Scope 4

1.3 Definitions, acronyms and abbreviations 5

1.4 Personnel involved 6

**2. General description 7**

2.1 Product perspective 7

2.2 Product functions 7

2.3 User characteristics 8

2.4 Constraints 8

2.5 Assumptions and dependencies 9

**3. Specific requirements 10**

3.1 Common interface requirements 10

3.1.1 User interfaces (UI) 10

3.1.2 Hardware interfaces 10

3.1.3 Software interfaces 10

3.2 Functional requirements 11

3.3 Non-functional requirements 40

3.4 Data model and normalization 42

**Annex A. Changes in version 2.0 44**

**Annex B. Assumptions and points to be validated 45**

# Requirements Specification

## 1. Introduction

This document details the requirements of the «Tu Evento» application, describing the functional and non-functional requirements of the system. It facilitates communication between the stakeholders and reduces the risks associated with development.

### 1.1 Purpose

«Tu Evento» is a web and mobile application developed by CapySoft that offers a comprehensive platform for the creation, administration and operation of events: organizers manage floor plans, design the layout of spaces, configure seats and publish events; attendees view events, select and buy tickets, receive notifications, obtain tickets with a QR code and validate their entry.

The system seeks a fluid, accessible and cross-platform experience, with high standards of security, scalability and usability. In this version, the payment for the tickets is made through a sandbox payment gateway, decoupled from the rest of the system with the Strategy pattern, so that the integration with a real gateway (for example, Wompi) can be incorporated without changing the business logic.

### 1.2 Scope

The scope of the system includes:

- User management: registration with code verification, login and logout, authentication
with JWT and Refresh Token, password recovery, account deletion, profile customization (language and theme) and optional authentication with social networks (Google/Facebook).

- Event management: creation in three steps, layout design of the venue floor plan (web only) with
sections, capacity and prices, and publication subject to the administrator's review. The mobile version displays the events.

- Reservations, purchases and attendance: seat selection, temporary hold, payment through the sandbox
payment gateway, tickets with unique QR codes and attendance validation by reading the QR.

- Payments: sandbox payment gateway (CapySoft microservice) decoupled through the Strategy
pattern; refunds and internal wallet of compensatory balance.

- User interaction: ratings and comments, push notifications and automatic
reminders, search filters and notification preferences.

- Administration: review of organizer requests, review and publication of events, financial
control, reports and refunds.

- Cross-platform compatibility: web (Google Chrome and Microsoft Edge) and mobile (Android and iOS).
The layout design of events is exclusive to the web version.

- Security: JWT, Refresh Token with auditing of renewals, API Gateway, HTTPS and role
control.

Exclusions from the scope:

- Live streaming of events and augmented or virtual reality features.
- Creation or editing of floor plans from the mobile application; the advanced administrative functions
are exclusive to the web.

- Integration with real payment gateways in this version (Wompi, Stripe, PayPal, MercadoPago): the
payment is simulated. The architecture (Strategy pattern) makes it possible to incorporate them in the future.

- Internal messaging between users or real-time chat.
- Advanced customization of the purchase flow by the organizer (dynamic rules,
templates).

- Multiple currencies, international payments or currency conversion (it operates in Colombian
pesos, COP).

- Advanced marketing tools: email automation, segmentation or campaigns.
- Integration with social networks other than login: no content is published or shared
on them.

- Exclusive presales, VIP memberships or special access beyond those defined in the
requirements.

### 1.3 Definitions, acronyms and abbreviations

| **Term** | **Description** |
|---|---|
| User | Person who uses the system; they can be anonymous, an attendee, an organizer or an administrator. |
| SRS / ERS | Software Requirements Specification. |
| ADSO | Análisis y Desarrollo de Software (Software Analysis and Development). |
| RF / RNF | Functional / non-functional requirement. |
| Interface | Main design of the page or application. |
| Mockup | Static visual representation of a product. |
| JWT | JSON Web Token; signed credential to authenticate requests. |
| Refresh Token | Long-lived token used to renew the Access Token without asking for credentials. |
| QR | Quick response code used as the access ticket to the event. |
| DDD | Domain-Driven Design; design approach centred on the business domain. |
| Microservice | Small and independent service that fulfils a specific function. |
| Strategy pattern | Design pattern that encapsulates interchangeable algorithms behind a common interface. |
| Payment gateway | Service that processes online payments. In this version, our own sandbox gateway for testing the payment flow; Wompi is the planned real gateway. |
| Simulated payment | Payment process that reproduces the operation of a real gateway without connecting to it. |
| Webhook | Notification that the gateway sends to the backend to report the result of a payment. |
| Idempotency | Property by which processing the same notification several times produces a single effect. |
| Internal wallet | Compensatory balance generated by event cancellations, usable only within the platform. |
| Section | Zone of the venue (General, VIP, Box, Stand) with its own capacity and price. |

### 1.4 Personnel involved

| **Name** | Cristofer David Lozano Contreras |
|---|---|
| **Main role** | Database administrator |
| **Professional category** | Apprentice of the technologist in software analysis and development. |
| **Main** **responsibility** | Monitor the follow-up of the team; backend developer, database designer, support in the mobile display and documentation. |
| **Contact** | Cristofer_Lozano@soy.sena.edu.co |

| **Name** | Jhampier Santos Ortiz |
|---|---|
| **Main role** | Software development support |
| **Professional category** | Apprentice of the technologist in software analysis and development. |
| **Main** **responsibility** | Preparation and organization of the documentation; contribution to the design and construction of the frontend to achieve clear and intuitive interfaces. |
| **Contact** | Jham_santos@soy.sena.edu.co |

## 2. General description

### 2.1 Product perspective

The system is offered in web and mobile format. The web version allows organizers to design the layout of floor plans, configure seats, send events for review and manage attendance; it allows administrators to review requests and events and supervise the finances. The mobile version (Android and iOS) allows attendees to view events, select and buy tickets, receive notifications, access their tickets and, for organizers, scan QR codes.

The architecture is hybrid: a main modular N-tier backend with DDD (Java 21, Spring Boot, PostgreSQL 17) and an independent payment microservice (Payment Service) that implements the sandbox gateway. The backend consumes payments through the PaymentGatewayStrategy interface, so the behaviour of the system does not depend on the provider.

![Figure on page 7](../_assets/01_Especificacion_Requisitos/SRS_Tu_Evento/pagina-07-figura-1.png)

<!-- Texto dentro de la figura (página 7): [Backend N-capas + DDD Identidad · Eventos · Planos Reservas · Tickets · Cartera Notificaciones · Administración] [Clientes Web · Android · iOS] [API Gateway JWT · rate limit] [Payment Service pasarela simulada] [PostgreSQL 17] EN: Text inside the figure (page 7): [N-tier Backend + DDD Identity · Events · Floor plans Reservations · Tickets · Wallet Notifications · Administration] [Clients Web · Android · iOS] [API Gateway JWT · rate limit] [Payment Service simulated gateway] [PostgreSQL 17] -->

Figure 1. General architecture: modular backend and payment microservice.

### 2.2 Product functions

- Registration, authentication and management of accounts and profiles, with language (ES/EN/PT/JA) and theme (light,
dark, purple, blue).

- Creation, layout design and publication of events with the administrator's approval.
- Exploration and filtering of events, with access without a session on the web.
- Seat selection, temporary hold and purchase of tickets with simulated payment.
- Tickets with unique QR codes and attendance validation.
- Internal wallet of compensatory balance and refunds approved by the administrator.
- Ratings and comments on events.
- Push notifications, internal notifications and automatic reminders.
- Dashboard by role and administration module (requests, events, financial control, reports and
refunds).

### 2.3 User characteristics

<table>
<tr>
<td><strong>Type of user</strong></td>
<td>User (anonymous, web only)</td>
</tr>
<tr>
<td><strong>Activities</strong></td>
<td>• Create an account.<br>• Log in.<br>• Explore and search for events.</td>
</tr>
</table>

<table>
<tr>
<td><strong>Type of user</strong></td>
<td>User (attendee)</td>
</tr>
<tr>
<td><strong>Activities</strong></td>
<td>• Create an account, reset the password and delete the account.<br>• Explore and filter events; select seats and buy tickets.<br>• Consult My Events («Mis Eventos») and tickets with QR; use the wallet.<br>• Comment on and rate events.<br>• Request the organizer role.</td>
</tr>
</table>

<table>
<tr>
<td><strong>Type of user</strong></td>
<td>User (organizer)</td>
</tr>
<tr>
<td><strong>Activities</strong></td>
<td>• Create events and design the layout of the venue floor plan; save progress.<br>• Send events for review and consult the history and status of their events.<br>• Delete their own events that meet the conditions.<br>• Scan QR codes to validate attendance.</td>
</tr>
</table>

<table>
<tr>
<td><strong>Type of user</strong></td>
<td>Administrator</td>
</tr>
<tr>
<td><strong>Activities</strong></td>
<td>• Review, approve or reject organizer requests.<br>• Review, publish or reject events.<br>• Consult financial control and reports; manage refunds.</td>
</tr>
</table>

### 2.4 Constraints

- Connectivity: the system requires an internet connection for all its operations.
- Platforms: web on Chrome and Edge; mobile on Android 11 or later and iOS with equivalent
features.

- Access without authentication: the web version allows viewing events without logging in.
- Limitations on mobile: events cannot be laid out; only viewing events, selecting
seats, buying tickets and, for organizers, scanning QR codes.

- Payments: only the simulated payment method by QR code is supported; single currency (COP).
- Security: secure authentication, Refresh Token, password recovery and communication over
HTTPS.

### 2.5 Assumptions and dependencies

- Users have a stable internet connection and basic skills in the use of computers and
mobile devices.

- The Payment Service (sandbox gateway) and the external services (SMTP, Firebase Cloud Messaging
and OAuth) are operational.

## 3. Specific requirements

### 3.1 Common interface requirements

#### 3.1.1 User interfaces (UI)

The interface is intuitive and interactive, with navigation by role, support for four languages and four visual themes, and responsive design.

#### 3.1.2 Hardware interfaces

- Web: Windows operating system; Chromium-based browsers (Google Chrome and
Microsoft Edge).

- Mobile: Android 11 or later (full compatibility); iOS with the features defined in
RF12, subject to the restrictions of the operating system.

- Camera of the mobile device for reading QR codes.
#### 3.1.3 Software interfaces

- Backend (RESTful API) in Java 21 with Spring Boot; data exchange in JSON over HTTPS
(HTTP only in local development). The API covers authentication, users, events, reservations, payments, tickets, notifications and administration.

- PostgreSQL 17 database through Spring Data JPA.
- Payment Service (sandbox gateway): independent microservice accessed through a REST API via
the PaymentGatewayStrategy interface; it returns the result through signed notifications (webhook) to the backend.

- External services: email by SMTP, Firebase Cloud Messaging for push notifications
and OAuth 2.0 providers (Google/Facebook).

- Security: authentication and authorization with JWT and Refresh Token, API Gateway and role control.
![Figure on page 10](../_assets/01_Especificacion_Requisitos/SRS_Tu_Evento/pagina-10-figura-1.png)

<!-- Texto dentro de la figura (página 10): [SimulatedGateway Strategy · ACTIVA Payment Service CapySoft] [Reservas · Tickets Cartera · Notificaciones] [«interface» PaymentGatewayStrategy createPayment · getStatus processWebhook · refund] [WompiGateway Strategy · FUTURA requiere credenciales] EN: Text inside the figure (page 10): [SimulatedGateway Strategy · ACTIVE Payment Service CapySoft] [Reservations · Tickets Wallet · Notifications] [«interface» PaymentGatewayStrategy createPayment · getStatus processWebhook · refund] [WompiGateway Strategy · FUTURE requires credentials] -->

Figure 2. Strategy pattern: each strategy normalizes the response or the webhook of the provider to the internal PaymentResult model.

### 3.2 Functional requirements

#### List of functional requirements

#### User management

- **RF1:** User registration
- **RF2:** Authentication with social networks (OAuth)
- **RF3:** User login
- **RF4:** Profile management and customization
- **RF5:** Recover password
- **RF6:** Log out
- **RF7:** User account deletion
#### Administration

- **RF8:** System administration module
- **RF27:** Request for the organizer role
- **RF29:** Financial control, reports and refunds (administrator)
#### Events

- **RF9:** Editing and layout design of the event structure
- **RF19:** Layout design and management of events from the web version
- **RF23:** Event filters
- **RF28:** My events and tickets
#### Reservations, payments and attendance

- **RF10:** Seat reservation
- **RF11:** Generation and validation of a QR code per reservation
- **RF17:** Sandbox payment gateway with the Strategy pattern
- **RF18:** Buy tickets from the mobile application
- **RF24:** QR reader for attendance validation
- **RF25:** Management of the compensatory balance (internal wallet)
#### Interaction and customization

- **RF13:** Multi-language support (ES/EN/PT/JA)
- **RF14:** Dashboard by role
- **RF16:** Push notification and automatic reminder system
- **RF22:** Interface theme system
- **RF26:** Ratings and comments on events
#### Security, compatibility and architecture

- **RF12:** Functional iOS
- **RF15:** Refresh Token system
- **RF20:** Microservice-oriented architecture
- **RF21:** Backend in an N-tier architecture with DDD
<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF1</td>
<td colspan="2"><strong>Name:</strong> User registration</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Home page, user interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>User credentials (name, email and password).</td>
<td colspan="3"><strong>Output:</strong>The system reports that the account was created successfully and redirects to the login page.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The user enters their credentials (name, email and password).<br>• The system generates a 6-digit verification code and sends it to the email provided.<br>• The user enters the code in the system to validate their account.<br>• If the verification is successful, the system registers the account and redirects the user to the login page.<br>• If the verification fails, the system notifies that the email already exists or that the code is incorrect or expired.<br>• The password must meet the security requirements defined in RF5.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The system must be running and accessible to the user.<br>• The user must not have an account registered with the same email.<br>• The email sending service must be available.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the email is already registered, the system shows an error message.<br>• If the user enters an incorrect or expired code, the system shows an invalidation message and allows requesting a new code.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• If the data is correct, the system creates the account and redirects the user to the login screen.<br>• Every registered user receives the attendee role by default.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• If the verification is successful: the user is registered in the database with the attendee role.<br>• If the verification fails: the account is not registered and the error is notified (existing email or invalid/expired code).</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF2</td>
<td colspan="2"><strong>Name:</strong> Authentication with social networks (OAuth)</td>
</tr>
<tr>
<td><strong>Type:</strong> Optional</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> No</td>
</tr>
<tr>
<td><strong>Development priority:</strong> Medium</td>
<td colspan="4"><strong>Associated display documents:</strong> Home page, user interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user selects the option to log in or link their account with a social network (Google/Facebook) and authorizes access on the chosen platform.</td>
<td colspan="3"><strong>Output:</strong>The system associates the user's account with the selected social network and allows access.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The user can link their account with an external profile (Google or Facebook) through the OAuth 2.0 protocol.<br>• Once the linking is authorized, the system stores the relationship to allow future logins without additional credentials.<br>• The integration with social networks is limited to authentication; it does not include publishing or sharing content.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The system must be running and accessible.<br>• The user must have an active account on the selected social network.<br>• The social network must be available to respond to the authentication request.<br>• The user must be connected to the internet.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the user cancels the authorization on the social network, the linking is not completed and a notification message is shown.<br>• If the social network does not respond or there is an authentication error, an error message is shown with the option to retry.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong>In case of success, the account is associated and available for future logins.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• If the authentication is successful: the account is associated with the social network and the user can log in with it.<br>• If it fails or is cancelled: the linking is not performed, a message is shown and the account remains unchanged.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF3</td>
<td colspan="2"><strong>Name:</strong> User login</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Home page, user interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>Email and password of a previously registered user.</td>
<td colspan="3"><strong>Output:</strong>The system delivers the session tokens (Access Token and Refresh Token, see RF15) and redirects to the main page according to the user's role.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The user goes to the login page, where the email and password fields are shown.<br>• The system validates that the fields are not empty and queries the database to verify that the email is registered and the password matches.<br>• If the credentials are valid, the system issues an access JWT and a Refresh Token and redirects the user.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user must be registered in the system.<br>• The system must be available and online.<br>• The user must have internet access.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the email or the password are incorrect, the system shows a message (e.g. “Incorrect user or password” («Usuario o contraseña incorrectos»)) and allows retrying.<br>• The login endpoint applies a limit on attempts (rate limiting) to mitigate brute force attacks.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• With valid credentials, the system establishes an active session.<br>• The session persists as long as the interaction lasts and is renewed according to RF15.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The session remains active until the user logs out or the Refresh Token expires.<br>• The user accesses the features and permissions associated with their role.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF4</td>
<td colspan="2"><strong>Name:</strong> Profile management and customization</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface, user management</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Registration interface and user profile.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>Mandatory: first name, last name, email (already verified) and password. Editable: first name, last name, address, language, theme and notification preferences.</td>
<td colspan="3"><strong>Output:</strong>The system confirms the creation or update of the profile with a success message; the information is saved and available in the profile section.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• It allows the user to configure and manage their personal information: initial creation of the profile after registration and later editing of their data.<br>• The system stores the user's preferences (language, interface theme and notifications) to apply them in each session.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user completed the registration (by email or social network).<br>• If the registration was by email, it must be verified.<br>• The system is available and the user has internet access.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the user logged out, they cannot access their information until they log in again.<br>• If there is no connection, it is not possible to manage the profile.<br>• If the processing takes too long, the user is asked to retry with a generic message.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The user can edit their information at any time.<br>• The information is saved persistently in the database.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The profile is created or updated and available in future sessions.<br>• If a social network was linked, the association is saved.<br>• In case of failure the previous information is not altered and the user is notified.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF5</td>
<td colspan="2"><strong>Name:</strong> Recover password</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Password recovery page, user interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>User's email.</td>
<td colspan="3"><strong>Output:</strong>If the email exists, a verification code is sent to renew the password.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The user selects “Forgot your password?” («¿Olvidaste tu contraseña?») on the login page and enters their email.<br>• The system validates that the field is not empty and has a valid format, and searches for the email in the database.<br>• If it is registered, it generates a unique verification code and sends it to the email; if not, it shows an error message.<br>• With the valid code, the user defines a new password.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user has a registered account with a verified email.<br>• The system is online and has access to the email sending service.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the email is not registered, an error message is shown.<br>• If the code expires or is incorrect, the system asks to generate a new code.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The email must have a valid format.<br>• The new password must have a minimum of 8 characters, one uppercase letter, one number and one special character.<br>• The user receives confirmation that their password was updated.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The user has a new password.<br>• The code used is invalidated to prevent its reuse.<br>• The account can log in with the new password.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF6</td>
<td colspan="2"><strong>Name:</strong> Log out</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> User interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user selects the option “Log out” («Cerrar sesión»).</td>
<td colspan="3"><strong>Output:</strong>The system invalidates the active session and prevents access to protected functions until a new login.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• When “Log out” («Cerrar sesión») is selected, the system invalidates the Access Token and revokes the associated Refresh Token (see RF15).<br>• The user immediately loses access to the protected areas and is redirected to the home page or the login page.<br>• It guarantees security and privacy on shared or public devices.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user has an active session.<br>• The authentication service is available.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the connection is lost during logout, the following is shown: “The session could not be closed due to connection problems, please try again” («No se pudo cerrar la sesión por problemas de conexión, inténtelo nuevamente»).<br>• If the session had already expired, the system automatically redirects to login.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong>After logging out, the user is redirected to the login screen.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The session and the Refresh Token are invalidated.<br>• Private data and functions cannot be accessed until logging in again.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF7</td>
<td colspan="2"><strong>Name:</strong> User account deletion</td>
</tr>
<tr>
<td><strong>Type:</strong> Optional</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Account settings page, user interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user selects the option “Delete account” («Eliminar cuenta») in the settings and confirms the action in the pop-up window.</td>
<td colspan="3"><strong>Output:</strong>The system permanently and irreversibly deletes the user's personal data and redirects them to the home screen with a confirmation message.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• It allows the user to erase their profile and their personal information. The option is called “Delete account” («Eliminar cuenta») (not “Deactivate” («Desactivar»)), since the action is irreversible.<br>• The system requests explicit confirmation (e.g. “Are you sure you want to delete your account? This action cannot be undone” («¿Está seguro de que desea eliminar su cuenta? Esta acción no se puede deshacer»)) and reauthentication (password or code).<br>• The personal data is deleted; the transactional records (payments, reservations, wallet movements) are kept in anonymized form for financial traceability.<br>• An organizer with published events or a user with active reservations must resolve them before deleting the account.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Active session and reauthentication of the user.<br>• The user has no active reservations or published events with current sales.<br>• The system is online and has access to the database.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the connection is interrupted before completing the deletion, the following is shown: “The operation could not be completed, please try again” («La operación no pudo completarse, inténtelo nuevamente»).<br>• If someone tries to access with the deleted credentials, the system indicates that they do not exist.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Prior confirmation is requested.<br>• The personal data is deleted permanently.<br>• After the deletion the user is redirected to the home screen.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The account and its personal data no longer exist in the system.<br>• The financial records remain anonymized.<br>• The user is left without access to the system.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF8</td>
<td colspan="2"><strong>Name:</strong> System administration module</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Administrator interface; validation of organizer requests; review of events</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Administration interface (side menu: Dashboard, Financial Control, Events, Reports, Refunds and Requests).</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The administrator logs in with valid credentials.</td>
<td colspan="3"><strong>Output:</strong>The administrator accesses a dashboard exclusive to their role where they manage organizer requests, event review, financial control, reports and refunds.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• After authenticating, the system identifies the role and redirects to the administration dashboard.<br>• Requests: it lists the requests from users who want to be organizers, filterable by status (All, Pending, Approved, Rejected), with user, email, document, date, status and actions. The administrator reviews the attached document and approves or rejects. On approval, the user acquires the organizer role.<br>• Events: it lists the events sent for review (status “Under review” («En revisión»)). The administrator consults the modality, structure of sections with capacity and prices, organizer and available tickets, and decides “Publish” («Publicar») or “Reject” («Rechazar») (see RF9 and RF19).<br>• Financial Control, Reports and Refunds: see RF29.<br>• The administrator can also perform the common functions of any account (login/logout, password recovery).</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• There is a user with the administrator role.<br>• The system is online and has access to the database.<br>• To approve an organizer, the applicant previously sent their documents.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• With incorrect credentials, “Incorrect user or password” («Usuario o contraseña incorrectos») is shown.<br>• With an unstable connection, “Connection problems, please try again” («Problemas de conexión, inténtelo de nuevo») is shown.<br>• If the connection is lost when approving/rejecting, the action is not completed and “The operation was not processed correctly” («La operación no se procesó correctamente») is shown.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The administrator is automatically redirected to the dashboard after logging in.<br>• The system records the result (accepted/rejected) of each request and of each event review, with the date and the responsible administrator.<br>• After the approval, the organizer can access the event creation module.<br>• When rejecting a request or an event, the system allows recording the reason and notifies the interested party.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The administrator is authenticated in their management module.<br>• The approved organizers can create events.<br>• The approved events are published and visible to the attendees.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF9</td>
<td colspan="2"><strong>Name:</strong> Editing and layout design of the event structure</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Event development interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Event creation page and layout editor (web).</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The organizer selects the option to design the layout of the event venue floor plan within the editor.</td>
<td colspan="3"><strong>Output:</strong>The system allows creating and saving a digital floor plan of the venue associated with the event.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The editor offers a graphical interface with predefined elements to design a floor plan similar to the venue, starting from an already generated floor plan or from scratch.<br>• The floor plan is made up of sections (General, VIP, Box, Stand or others), each with its capacity and price.<br>• The organizer can save progress (draft) without publishing it and delete a floor plan as long as it has no active reservations.<br>• When the organizer finishes the design, they send the event for review; the floor plan is only available for reservations when the administrator publishes the event (RF8).</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Session started with the organizer role.<br>• There is a previously created event with which the floor plan will be associated.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong>If the connection is interrupted during the creation, the system notifies that the floor plan was not saved correctly.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Only the organizer role can create and modify event structures.<br>• The system allows saving layout design drafts.<br>• A floor plan can be deleted only if it has no active reservations.<br>• While the event is “Under review” («En revisión») it cannot be edited; the organizer can withdraw it from review to make changes.<br>• The published floor plan is displayed correctly in the seat selection.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The floor plan is stored and linked to the event.<br>• Once the event is published, the attendees can view the floor plan and select their seats.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF10</td>
<td colspan="2"><strong>Name:</strong> Seat reservation</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Scheduling and purchase interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Seat selection page, cart and purchase confirmation.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The attendee selects an event, indicates how many seats they need and chooses available seats by section on the floor plan.</td>
<td colspan="3"><strong>Output:</strong>The system temporarily blocks the chosen seats, adds them to the cart with their total and continues to payment.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The attendee views the published events, chooses one and selects available seats on the venue map; the selected ones go to the cart (“Your Cart” («Tu Carrito»)) with the total.<br>• When continuing to payment, the reservation is created in the PENDIENTE_PAGO status and the seats are temporarily BLOQUEADAS (stock hold) so that another user cannot select them. The cart shows a timer with the remaining time.<br>• The confirmation of the reservation is automatic: when the payment gateway (see RF17) reports the payment as APROBADO, the reservation goes to CONFIRMADA and the seats to OCUPADAS. No manual or “physical” validation by the organizer is involved.<br>• If the payment is rejected, cancelled or the hold time expires, the reservation goes to CANCELADA/EXPIRADA and the seats are released automatically.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user logged in.<br>• There is a published event enabled for reservations.<br>• There is a published seat floor plan for the event.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the seat was already taken by another user (blocked or occupied), the system notifies it and asks to choose another one.<br>• If the connection is interrupted during the reservation, the system indicates that the operation was not completed.<br>• If two users select the same seat simultaneously, only one obtains the block (concurrency control).</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The seat is blocked from the moment the user continues to payment.<br>• Seat statuses: DISPONIBLE, BLOQUEADA, OCUPADA. Reservation statuses: PENDIENTE_PAGO, CONFIRMADA, EXPIRADA, CANCELADA.<br>• The hold time is configurable by the system (suggested default value: 10 minutes).<br>• The confirmed seat is marked as occupied on the floor plan.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The reservation is stored and linked to the event.<br>• If it is confirmed, the seats are permanently occupied.<br>• If it is not confirmed within the defined time, the seats are released automatically.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF11</td>
<td colspan="2"><strong>Name:</strong> Generation and validation of a QR code per reservation</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Reservations (RF10), payments (RF17), attendance control (RF24)</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> “Payment approved” («Pago aprobado») screen with tickets, My Events («Mis Eventos»), event management.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The payment gateway notifies that the payment of a reservation was APROBADO.</td>
<td colspan="3"><strong>Output:</strong>The system generates a unique QR code per reservation (ticket), shows it to the attendee on screen and sends it to their email.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The QR is generated only when the payment is APROBADO; there is no QR for pending, rejected or expired reservations.<br>• The QR contains the essential information for its validation: unique ticket identifier, event, date, number and location of the seats.<br>• The QR serves as proof of purchase and access control. The organizer validates it through the reader of RF24.<br>• QR statuses: VÁLIDO (active), USADO (already validated at the entry), ANULADO (cancelled reservation or cancelled event) and CADUCADO (finished event).</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The reservation exists and its payment was approved.<br>• The reservation has assigned seats.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the payment is not approved, no QR is generated.<br>• If the sending of the email fails, the ticket remains available in “My Events” («Mis Eventos») and the system retries the sending.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The QR is unique per reservation, regardless of the number of seats.<br>• The QR includes the information needed for its validation and cannot be reused after its validation.<br>• The organizer can scan the QR from the application to validate the attendance.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The reservation is confirmed with a functional QR that allows access to the event.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF12</td>
<td colspan="2"><strong>Name:</strong> Functional iOS</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Mobile compatibility</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Mobile version of the application.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user accesses the application from an iOS device.</td>
<td colspan="3"><strong>Output:</strong>The system shows the features defined for the mobile platform.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• It guarantees that the system runs functionally on iOS devices: viewing events, seat selection, ticket purchase, tickets with QR, QR reading (organizer), profile and notifications.<br>• The limitations of the operating system itself are documented and do not affect the essential functions. A compatibility test must be carried out that confirms the operation.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Device with an updated iOS.<br>• Internet access and the system online.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If any functionality cannot be run, a partial incompatibility message is shown.<br>• If the connection with the server fails, the user is asked to check the internet connection.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The application opens, loads data and runs the essential functions on iOS.<br>• At least one documented compatibility test is run.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The operation of the essential functions on iOS is confirmed.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF13</td>
<td colspan="2"><strong>Name:</strong> Multi-language support (ES/EN/PT/JA)</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Design of the multi-language interface.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user selects a language: Spanish, English, Portuguese or Japanese.</td>
<td colspan="3"><strong>Output:</strong>The complete interface is shown in the selected language.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The system allows changing and showing the interface in four languages: Spanish (ES), English (EN), Portuguese (PT) and Japanese (JA).<br>• The translated content is loaded dynamically without reloading the application; the user can change the language at any time from the settings and the selection is saved in their preferences.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• There are translation resources for the 4 languages.<br>• Internet access if the translations are loaded from the server.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If a translation is missing, the text is shown in the default language (Spanish).<br>• If loading the language package fails, the user is notified that it was not possible to change it.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• It is possible to switch between the 4 languages without affecting the operation.<br>• All visible texts are shown in the chosen language.<br>• There are tests that validate the completeness of the translations per language.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The application remains in the chosen language, with consistency in all its texts.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF14</td>
<td colspan="2"><strong>Name:</strong> Dashboard by role</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface, administration module, event management</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Dashboard interface (attendee, organizer and administrator).</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user logs in with a valid role (attendee, organizer or administrator).</td>
<td colspan="3"><strong>Output:</strong>The system shows a dashboard with the information and access specific to the role.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The Dashboard is displayed after login and is dynamic according to the role:<br>• Attendee: available events, reserved events, status of their reservations (pending, confirmed), wallet balance and important notifications.<br>• Organizer: created events and their status (Draft, Under review, Published, Rejected), number of reservations per event, QR validation status and direct access to the creation and layout design of events.<br>• Administrator: pending organizer requests, events under review, active users, financial indicators and access to the validation, reports and refunds modules.<br>• The information is requested from the backend and rendered up to date.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• The user logged in and their role is identified.<br>• The server is available.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If loading fails, the following is shown: “The dashboard information could not be loaded, try again later” («No se pudo cargar la información del panel, intente más tarde»).<br>• If the role is not defined, an error is shown and the user is redirected to login.<br>• If the connection fails, a basic view without data is shown with the option to retry.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The Dashboard is shown immediately after login.<br>• The information is accurate and consistent with the role.<br>• It loads in less than 3 seconds with a normal network.<br>• It allows navigating directly to the main functions.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The user remains on their Dashboard with direct access to the functions of their role.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF15</td>
<td colspan="2"><strong>Name:</strong> Refresh Token system</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Persistent authentication, session security</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Token renewal flow, JWT authentication diagram, refresh endpoints.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The client has an expired Access Token and a valid Refresh Token.</td>
<td colspan="3"><strong>Output:</strong>The system generates a new Access Token (and a new Refresh Token with rotation), allowing the user to continue without a new login.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• When an Access Token expires, the client automatically sends the Refresh Token to the endpoint /auth/refresh.<br>• The Refresh Token has a longer lifetime (7 to 30 days) and allows renewing Access Tokens without asking for credentials.<br>• The system validates the integrity of the token, verifies that it is not revoked and issues new tokens with updated claims.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• User authenticated with initially valid JWT tokens.<br>• Refresh Tokens table (issued and revoked) in the database.<br>• Endpoint /auth/refresh implemented and automatic renewal logic in the web and mobile clients.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• Invalid or tampered token: it is rejected with a failed authentication message.<br>• Expired token: the user is redirected to login.<br>• Revoked or unregistered token: the session is closed and the user is asked to authenticate.<br>• Connection or server failure: the user is informed that it was not possible to renew.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The renewal is automatic and secure, and takes less than 2 seconds.<br>• The session is not interrupted as long as the Refresh Token is valid.<br>• Tokens can be revoked individually or in bulk.<br>• Rate limiting on the refresh endpoint.<br>• Complete auditing of renewals.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The user keeps the session without re-entering credentials.<br>• The renewal is recorded for security auditing.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF16</td>
<td colspan="2"><strong>Name:</strong> Push notification and automatic reminder system</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User engagement, reminders, transactional confirmations</td>
<td><strong>Critical?</strong> No</td>
</tr>
<tr>
<td><strong>Development priority:</strong> Medium</td>
<td colspan="4"><strong>Associated display documents:</strong> Firebase Cloud Messaging architecture, notification flow, reminder rules, notification icon (bell) on the web.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>A system event requires notifying the user (payment approved, upcoming event, change in reservation, approval of a request or event, reminder).</td>
<td colspan="3"><strong>Output:</strong>The user receives a push and/or internal (bell) notification with relevant information.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• Push notifications through Firebase Cloud Messaging (FCM) for mobile devices and web browsers; the backend registers the device tokens (DeviceToken model).<br>• Each notification includes title, message, icon, sound and data for deep linking.<br>• The user can enable or disable notification types from their preferences.<br>• Automatic reminders 48 hours and 2 hours before events with a confirmed reservation.<br>• Status change notifications: organizer request approved/rejected, event published/rejected, payment approved, refund.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Firebase project with FCM enabled.<br>• Mobile application with notification support (expo-notifications if Expo is used) and web application with the Firebase SDK.<br>• Notification permissions granted by the user.<br>• Events with scheduled dates and times.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• Invalid or expired token: it is deleted and a new one is requested.<br>• FCM not available: it is queued and resent with exponential backoff.<br>• User without notification permissions: an email is sent as a fallback.<br>• Offline device: FCM delivers when it reconnects.<br>• Failure in scheduling a reminder: it is recorded and retried in the next cycle.<br>• Cancelled reservation: the pending reminders are cancelled.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Automatic registration of the token when logging in.<br>• Payment notification processed in less than 5 seconds.<br>• Reminders 48 h and 2 h before the event.<br>• Immediate alerts of changes in reservations.<br>• Functional deep linking.<br>• Notification preferences per user.<br>• Delivery rate higher than 95 % in active push notifications.<br>• Delivery metrics and auditing of sent notifications.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• Users receive timely notifications and reminders.<br>• The notification metrics are available for analysis.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF17</td>
<td colspan="2"><strong>Name:</strong> Sandbox payment gateway with the Strategy pattern</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Reservations, tickets/QR, wallet, notifications</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Payment flow, PaymentGatewayStrategy contract, payment state diagram, internal notification (webhook), “Confirm purchase” («Confirmar compra») and “Payment approved” («Pago aprobado») screens.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The attendee, in “Confirm purchase” («Confirmar compra»), reviews the seats and the total, chooses the payment method (QR Code) and presses “Pay” («Pagar»).</td>
<td colspan="3"><strong>Output:</strong>Payment processed, reservation confirmed and tickets with QR available (“Payment approved!” («¡Pago aprobado!»)), or a message of rejected/cancelled/pending payment.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• In this version a real gateway is not integrated (no credentials are available). The payment is processed through a sandbox gateway, implemented as an independent microservice (Payment Service) developed by CapySoft, which reproduces the flow of a real gateway.<br>• The behaviour of the project is independent of the provider thanks to the Strategy pattern: the core defines the PaymentGatewayStrategy interface with the operations create payment, query status, process notification (webhook) and refund. Its implementations are SimulatedGatewayStrategy (active) and WompiGatewayStrategy (future, out of the scope of this version).<br>• The active strategy is selected by configuration. Each strategy translates the response or the webhook of its provider into a normalized internal model (PaymentResult: transaction identifier, reference, amount, currency COP, date and status PENDING, APPROVED, REJECTED, CANCELLED or EXPIRED).<br>• The Reservations, Tickets, Wallet and Notifications modules only know the normalized model; therefore, regardless of the origin of the response, the subsequent flow is identical and changing the provider does not require modifying them.<br>• Simulated flow: (1) the backend creates the transaction with a reference linked to the reservation; (2) the simulator presents the payment method by QR code; (3) when the simulated payment is completed (or rejected), the simulator sends a notification to the internal webhook endpoint, signed with a shared secret; (4) the backend validates the signature, applies idempotency and updates the reservation, tickets and notifications.<br>• The simulator must allow forcing results (approved, rejected, pending, expired) for tests and demonstrations.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Authenticated user.<br>• Reservation in the PENDIENTE_PAGO status with blocked seats and a valid hold.<br>• Gateway strategy configured and Payment Service available.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• Rejected or cancelled payment: the reservation is not confirmed; the user is informed, the seats are released when the hold expires or if the user cancels, and the user can retry while the hold is valid.<br>• Pending payment: the transaction remains “Pending” («Pendiente») until the result is received.<br>• Duplicate webhook: it is ignored due to idempotency (transaction identifier).<br>• Failed or unreceived webhook: retry with backoff and active query of the status.<br>• Payment approved after the hold expired and with seats already taken: the transaction is marked for refund (RF25) and the user is notified.<br>• Invalid webhook signature: it is rejected and audited.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The confirmation of the payment only occurs when a valid normalized notification is received.<br>• The QR is only generated if the status is APPROVED.<br>• Each payment is recorded with identifier, reference, status, amount and strategy used.<br>• Changing the active strategy does not require modifying the Reservations, Tickets or Wallet modules.<br>• There are automatic tests of the complete flow with the simulated strategy.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• Reservation confirmed and QR available for the entry.<br>• The transaction is recorded with traceability.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF18</td>
<td colspan="2"><strong>Name:</strong> Buy tickets from the mobile application</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Mobile module, ticket purchase, view of the event floor plan</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Mobile view of the floor plan, seat selection and purchase screen.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user opens an event from the mobile application.</td>
<td colspan="3"><strong>Output:</strong>The floor plan of the event, the available seats and the option to buy tickets are shown, without layout design tools.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• In the mobile version the user only views the layout of the event: they can see the floor plan, identify available seats, select them and pay through the configured payment gateway (RF17).<br>• The ticket with a QR code is available after the payment is approved.<br>• The creation, editing or layout design of events is exclusive to the web version.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Event created, laid out and published from the web version.<br>• Authenticated user.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the floor plan does not load, an error message is shown.<br>• If a seat is already occupied, the availability is updated before continuing.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The floor plan is displayed correctly on mobile.<br>• The user can select available seats and complete the purchase without editing options.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The ticket is purchased and the ticket/QR is available to the user.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF19</td>
<td colspan="2"><strong>Name:</strong> Layout design and management of events from the web version</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Organizer dashboard, floor plan editor, event creation</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> “Create event” («Crear evento») screen (3 steps), layout editor and “My Events” («Mis Eventos») (web).</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The organizer accesses the platform from the web version.</td>
<td colspan="3"><strong>Output:</strong>The system shows the event creation, layout design and management tools.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The complete creation, layout design and editing of the event are available only in the web version.<br>• Creation in three steps with a progress bar: (1) General information: name, description, start and end dates, public visibility, category, department and city; (2) Venue: selection of an existing venue or creation of a new one (name, address, maximum capacity and location on the map); (3) Images of the event.<br>• Then the organizer designs the floor plan in the layout editor (sections, seats, areas, capacity and price per section).<br>• Life cycle of the event: BORRADOR → EN_REVISIÓN → PUBLICADO or RECHAZADO. From “My Events” («Mis Eventos») the organizer sends the event for review; the administrator decides to publish or reject it (RF8). While it is under review it cannot be edited, and the organizer can withdraw it from review at any time.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Organizer authenticated in the web version.<br>• Active permissions for creating and editing events (role approved by the administrator).</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If a layout design tool fails, an error message is shown.<br>• If the event cannot be saved, the user is notified to retry.<br>• If the editor elements do not load, the view is reloaded or the failure is indicated.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The organizer creates, edits and saves events completely from the web.<br>• The editor allows adding, moving or deleting elements without restrictions.<br>• The mobile version does not allow access to creation or editing tools.<br>• The published changes are reflected in the mobile application.<br>• The publication requires the administrator's approval.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The event is created or updated.<br>• Once published, the floor plan is available on web and mobile.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF20</td>
<td colspan="2"><strong>Name:</strong> Microservice-oriented architecture</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Payments, notifications and future separation of domains</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Architecture diagram, API contracts, communication flows between services.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The system receives an operation that requires coordination between domains (user + event + payment).</td>
<td colspan="3"><strong>Output:</strong>The components process the request in a coordinated way through REST APIs and events.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The architecture of this version is hybrid: a main modular N-tier backend with DDD (RF21) and independent services where they are already justified. The Payment Service (sandbox gateway, RF17) runs as an independent microservice, with its own deployment and communication through a REST API and notifications (webhook).<br>• The complete separation of the other domains (Users, Events, Notifications, Administration) into microservices is an evolutionary goal; the modular design of RF21 enables it without rewriting the business logic.<br>• The API Gateway manages authentication, rate limiting and routing. The services use contracted APIs, circuit breakers and retries.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Modular N-tier backend implemented (RF21).<br>• Containerized infrastructure (Docker) available.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the Payment Service fails, the system activates a circuit breaker and shows a message to the user; the blocked reservations are released when the hold expires.<br>• If the communication is interrupted, retries with backoff are used.<br>• In the face of inconsistencies between services, compensation actions are applied.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The independent services are deployed and scaled separately.<br>• The communication is carried out through contracted APIs and events.<br>• The Payment Service has its own persistence.<br>• A change in one service does not affect the operation of the others.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The services operate in a decoupled way.<br>• The system is prepared to scale by functional domain.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF21</td>
<td colspan="2"><strong>Name:</strong> Backend in an N-tier architecture with DDD</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Java backend, modularization of the domain, preparation for microservices</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Package structure by module, domain diagrams, layer design.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>Spring Boot backend that must be organized by domains and layers.</td>
<td colspan="3"><strong>Output:</strong>Modular backend organized by domains and layers following DDD principles.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The backend is organized into modules by domain (Identity, Events, Venues/Floor plans, Reservations, Payments, Tickets, Notifications, Wallet and Administration).<br>• Each module keeps layers: Domain (entities and central logic), Application (use cases), Infrastructure (repositories, external adapters such as email, FCM and payment strategies) and Presentation (controllers with DTOs).<br>• The Strategy pattern for payment gateways (RF17) is placed as a port in Application/Domain and its implementations as adapters in Infrastructure.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Spring Boot environment (Java 21) and PostgreSQL 17 database configured.<br>• Docker available for packaging.<br>• Modular design approved.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• An error in one module is isolated without affecting the others.<br>• Infrastructure failures are handled with controlled exceptions.<br>• The loss of access to data generates clear and secure error responses.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Modules organized by domain and layers without incorrect dependencies.<br>• The business logic is concentrated in Domain; Application contains the use cases without duplication.<br>• Infrastructure implements repositories and adapters; Presentation exposes controllers with DTOs.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The backend is modularized and maintainable.<br>• The project is prepared to separate modules into microservices.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF22</td>
<td colspan="2"><strong>Name:</strong> Interface theme system</td>
</tr>
<tr>
<td><strong>Type:</strong> Improvement</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> UI customization, accessibility</td>
<td><strong>Critical?</strong> No</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Colour palette per theme, mockups of each theme, implementation guide.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user selects a theme from the settings.</td>
<td colspan="3"><strong>Output:</strong>The complete interface changes to the selected theme while maintaining visual consistency.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• 4 themes are provided: Light, Dark, Purple and Blue, with colours defined for backgrounds, texts, buttons, icons and components, with adequate contrast.<br>• The theme is saved in the user's preferences and applied at startup; it is consistent between web and mobile and detects the preference of the operating system (light/dark).</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Design system with theme variables.<br>• Persistent user configuration.<br>• Palettes verified for accessibility.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• Unsupported theme: the light theme is applied with a notification.<br>• Corrupt configuration: it is reset to the light theme.<br>• If the change fails, the previous theme is kept and a temporary message is shown.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• 4 themes implemented.<br>• Instant change without reloading.<br>• Persistence between sessions.<br>• Detection of the system preference.<br>• Applied to buttons, modals, forms and navigation.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The user customizes the appearance according to their preference.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF23</td>
<td colspan="2"><strong>Name:</strong> Event filters</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Event exploration interface</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> Medium</td>
<td colspan="4"><strong>Associated display documents:</strong> Events page with search bar and filters.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user types the name of the event and/or applies filters: city, category, date, availability, budget and type of event.</td>
<td colspan="3"><strong>Output:</strong>The events that meet the indicated criteria are shown.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong>It allows searching and filtering published events, giving greater visibility to the organizers and better analysis of availability to the attendees. It is also available to anonymous users in the web version.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Stable connection.<br>• At least one search criterion is entered.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong>If there are connection problems, an error message is shown and retrying is allowed.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The user can combine several criteria.<br>• Only published events are listed.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The system shows the events filtered according to the terms entered.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF24</td>
<td colspan="2"><strong>Name:</strong> QR reader for attendance validation</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> QR validation page (mobile application)</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> Organizer's event details interface, scanning screen.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The attendee presents their QR code (generated in RF11) and the organizer of the event scans it with the camera from the mobile application.</td>
<td colspan="3"><strong>Output:</strong>The system validates the QR in real time and, if it is correct, records the attendance and authorizes access.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The reader verifies the authenticity of the QR codes of confirmed reservations: that it is valid, has not been used and belongs to the scanned event.<br>• The validation is carried out by the organizer of the event; in this version there is no separate “control staff” («personal de control») role.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• There is a generated QR (RF11) associated with a confirmed reservation.<br>• The device has access to the camera and a stable connection.<br>• The event is active and in the ticket validation period.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong>If the QR is invalid, expired, voided or already used, the system notifies the validator and denies access.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• It works in real time from mobile devices.<br>• It guarantees uniqueness and avoids duplications.<br>• It shows differentiated messages: access authorized, invalid QR, expired QR, QR already used.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The attendance is recorded and linked to the event; the QR changes to the USADO status.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF25</td>
<td colspan="2"><strong>Name:</strong> Management of the compensatory balance (internal wallet)</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Payments (RF17), reservations (RF10), purchase (RF18), Dashboard (RF14), refunds (RF29)</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> User dashboard, transaction history, purchase confirmation.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong><br>• Authenticated user.<br>• Purchase made through the payment gateway (RF17).<br>• Event cancelled by the organizer.<br>• Request to use the balance in a new purchase.<br>• Request for an external refund (optional).</td>
<td colspan="3"><strong>Output:</strong><br>• Compensatory balance credited and visible on the Dashboard.<br>• Record of the movement in the history.<br>• Notification of the result to the user.<br>• In an external refund: management through the refund operation of the active payment gateway.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• The wallet stores exclusively the values generated by cancellations of paid events. It is not a rechargeable wallet or an independent financial system.<br>• When an event is officially cancelled and the refund is approved, the system credits the amount as compensatory balance, which can be used in the purchase of tickets for other events.<br>• The user consults their balance and history, but cannot top up, transfer to other users or withdraw directly to bank accounts.<br>• An external refund must be approved by an administrator (Refunds module, RF29) and is executed through the refund operation of the active payment strategy (RF17); in the sandbox gateway the result is simulated, and with a real gateway it is subject to its policies.<br>• The balance is only generated by the official cancellation of the event, not by errors, changes of mind or non-attendance.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Authenticated user.<br>• The original purchase was made through the payment gateway.<br>• The event is officially cancelled and the refund approved by the system or the administrator.<br>• The system and the Payment Service are operational.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the gateway rejects or does not authorize the external refund, the balance remains in the wallet.<br>• If the balance is insufficient for a purchase, the system blocks it or asks to complete the payment for the difference.<br>• If the connection fails during the crediting, the status is validated before reflecting the balance.<br>• If the cancellation does not meet the refund policies, the user is notified.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The balance is credited correctly after the approved cancellation.<br>• The use of the balance is deducted in real time.<br>• Each movement is in the history.<br>• The balance is only used within the platform.<br>• There is no manual top-up or direct withdrawal.<br>• The balance is shown up to date on the Dashboard.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong><br>• The user has an available compensatory balance.<br>• The transactions are recorded with traceability.<br>• The system maintains financial consistency without operating as an electronic wallet.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF26</td>
<td colspan="2"><strong>Name:</strong> Ratings and comments on events</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Event detail, user interaction</td>
<td><strong>Critical?</strong> No</td>
</tr>
<tr>
<td><strong>Development priority:</strong> Medium</td>
<td colspan="4"><strong>Associated display documents:</strong> “Comments” («Comentarios») section of the event detail.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user writes a comment, assigns a star rating or replies to another comment.</td>
<td colspan="3"><strong>Output:</strong>The comment or reply is published on the event and the average rating is updated.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• Each event has a comments section where users write their opinion, rate with stars and reply to other comments.<br>• The comments of the organizer of the event are identified with the label “Organizer” («Organizador»).<br>• Authenticated users can comment; the restriction to buyers of the event is defined as a configurable rule.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Authenticated user.<br>• The event is published.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the connection fails when sending, the comment is not published and retrying is allowed.<br>• Empty comments or comments with inappropriate content are rejected.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Rating from 1 to 5 stars.<br>• The replies are nested under the original comment.<br>• The organizer appears identified.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The comment is stored and visible to the other users.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF27</td>
<td colspan="2"><strong>Name:</strong> Request for the organizer role</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> User interface, administration module (RF8)</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> “Organizer Request” («Solicitud Organizador») and “Request under review” («Solicitud en revisión») screens.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The attendee selects “Organizer Request” («Solicitud Organizador») and uploads their identity document.</td>
<td colspan="3"><strong>Output:</strong>The request is recorded in the “Under review” («En revisión») status.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• An attendee can request the organizer role by sending documentation. Mandatory: citizenship card or ID, valid passport (foreigners) or official identity document. Optional: certificate of background check, course certificates and work references.<br>• The user drags or selects the file and presses “Send request” («Enviar solicitud»). The administrator processes it within 24 to 48 business hours (RF8).<br>• The result (approved or rejected) is notified to the user (RF16); when approved, the option “+ Create Event” («+ Crear Evento») appears.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Authenticated user with the attendee role.<br>• They do not have a pending request.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the file does not meet the allowed format or size, an error message is shown.<br>• If the upload fails, retrying is allowed.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• At least one mandatory document is attached.<br>• The user sees the status of their request.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The request is available for review by the administrator.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF28</td>
<td colspan="2"><strong>Name:</strong> My events and tickets</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Dashboard, reservations, QR, event management</td>
<td><strong>Critical?</strong> Yes</td>
</tr>
<tr>
<td><strong>Development priority:</strong> High</td>
<td colspan="4"><strong>Associated display documents:</strong> “My Events” («Mis Eventos») screen (attendee and organizer).</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The user opens “My Events” («Mis Eventos»).</td>
<td colspan="3"><strong>Output:</strong>Attendee: purchased tickets with their QR. Organizer: events they work on, with their status and filters by status.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• For the attendee, “My Events” («Mis Eventos») lists their purchases, the status of each reservation and the tickets with a QR code.<br>• For the organizer, it lists their events (Draft, Under review, Published, Rejected), allows sending for review, withdrawing from review and accessing the editor and the QR validation functions.</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong>Authenticated user.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong>If loading fails, a message and the option to retry are shown.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• The information corresponds to the user's role.<br>• The filters by status work correctly.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The user accesses their tickets or events from a single place.</td>
</tr>
</table>

<table>
<tr>
<td colspan="3"><strong>Identifier:</strong> RF29</td>
<td colspan="2"><strong>Name:</strong> Financial control, reports and refunds (administrator)</td>
</tr>
<tr>
<td><strong>Type:</strong> Necessary</td>
<td colspan="3"><strong>Requirement that uses or</strong> <strong>specializes it:</strong> Administration module (RF8), payments (RF17), wallet (RF25)</td>
<td><strong>Critical?</strong> No</td>
</tr>
<tr>
<td><strong>Development priority:</strong> Medium</td>
<td colspan="4"><strong>Associated display documents:</strong> “Financial Control” («Control Financiero»), “Reports” («Reportes») and “Refunds” («Reembolsos») modules of the administration dashboard.</td>
</tr>
<tr>
<td colspan="2"><strong>Input:</strong>The administrator opens one of the financial modules from the side menu.</td>
<td colspan="3"><strong>Output:</strong>Consultation of transactions, reports and management of refund requests.</td>
</tr>
<tr>
<td colspan="5"><strong>Description:</strong><br>• Financial Control: consultation of transactions (approved, rejected, pending and refunded) with their reference and the payment strategy used.<br>• Reports: sales and attendance reports by event and by period.<br>• Refunds: the administrator reviews and approves or rejects the refund requests; when approved, it is credited to the wallet (RF25) or the external refund is managed through the active payment gateway (RF17).</td>
</tr>
<tr>
<td colspan="5"><strong>Precondition:</strong><br>• Session started as administrator.<br>• There are recorded transactions.</td>
</tr>
<tr>
<td colspan="5"><strong>Handling of abnormal situations:</strong><br>• If the gateway does not authorize the refund, the request is recorded with the reason and the balance is kept.<br>• If loading a report fails, a message is shown and retrying is allowed.</td>
</tr>
<tr>
<td colspan="5"><strong>Criteria:</strong><br>• Every refund decision is audited with date and owner.<br>• The amounts match the payment records.</td>
</tr>
<tr>
<td colspan="5"><strong>Postcondition:</strong>The administrator has financial traceability of the platform.</td>
</tr>
</table>

### 3.3 Non-functional requirements

| **Identification of the** **requirement:** | RNF1 |
|---|---|
| **Name of the requirement:** | Error messages |
| **Category:** | User experience |
| **Description of the** **requirement:** | Error messages must follow a uniform format throughout the system (web and mobile), clearly indicate the cause and the suggested action, and be available in the four languages (RF13). |
| **Priority of the** **requirement:** | Medium |

| **Identification of the** **requirement:** | RNF2 |
|---|---|
| **Name of the requirement:** | Responsive design |
| **Category:** | Design and adaptability |
| **Description of the** **requirement:** | The design must be displayed correctly from a computer or any mobile device, adapting to the screen size. |
| **Priority of the** **requirement:** | High |

| **Identification of the** **requirement:** | RNF3 |
|---|---|
| **Name of the requirement:** | Security |
| **Category:** | System security |
| **Description of the** **requirement:** | Users are identified through email and password (stored with a secure hash), with verification of the email through a 6-digit code in registration and password recovery. The session is managed with JWT and Refresh Token (RF15). With login through social networks no additional verification is applied. All client-server communication must be carried out over HTTPS in production (HTTP only in local development). Access is controlled by roles (attendee, organizer, administrator) and the endpoints are protected through an API Gateway. |
| **Priority of the** **requirement:** | High |

| **Identification of the** **requirement:** | RNF4 |
|---|---|
| **Name of the requirement:** | Usability |
| **Category:** | User experience |
| **Description of the** **requirement:** | The interface must be intuitive, so that a user can perform basic tasks (search for an event, buy tickets, create an event) without technical assistance or a steep learning curve. |
| **Priority of the** **requirement:** | High |

| **Identification of the** **requirement:** | RNF5 |
|---|---|
| **Name of the requirement:** | Compatibility |
| **Category:** | Compatibility |
| **Description of the** **requirement:** | Web: Chromium-based browsers (Google Chrome and Microsoft Edge) on Windows. Mobile: Android 11 or later and iOS (RF12). The experience must be consistent across platforms. |
| **Priority of the** **requirement:** | High |

| **Identification of the** **requirement:** | RNF6 |
|---|---|
| **Name of the requirement:** | Performance |
| **Category:** | Performance |
| **Description of the** **requirement:** | The Dashboard loads in less than 3 seconds (RF14); the token renewal takes less than 2 seconds (RF15); the payment notification is processed in less than 5 seconds (RF16); all with normal network conditions. |
| **Priority of the** **requirement:** | Medium |

| **Identification of the** **requirement:** | RNF7 |
|---|---|
| **Name of the requirement:** | Extensibility of the payment gateway |
| **Category:** | Maintainability |
| **Description of the** **requirement:** | The payment provider must be able to be changed (simulated or real) through the Strategy pattern without modifying the Reservations, Tickets, Wallet or Notifications modules (RF17 and RF21). |
| **Priority of the** **requirement:** | High |

| **Identification of the** **requirement:** | RNF8 |
|---|---|
| **Name of the requirement:** | Integrity and concurrency |
| **Category:** | Reliability |
| **Description of the** **requirement:** | The system must not sell the same seat twice: the seat block is atomic and the payment notifications are idempotent. Expired holds are released automatically (RF10, RF17). |
| **Priority of the** **requirement:** | High |

### 3.4 Data model and normalization

The database is designed under a relational schema in Third Normal Form (3NF), which guarantees referential integrity, avoids redundancy and improves consistency. The payment transactions are recorded independently of the provider, with the normalized status and the strategy used, so that the model does not change when moving from the sandbox gateway to a real one. Main entities:

| **Entity** | **Description** | **RF** |
|---|---|---|
| Usuario / Rol | Account, profile, role (attendee, organizer, administrator) and preferences (language, theme, notifications). | RF1–RF7 |
| RefreshToken | Issued, rotated and revoked tokens, with auditing of renewals. | RF15 |
| SolicitudOrganizador | Document sent, status (pending, approved, rejected), reviewer and reason. | RF8, RF27 |
| Sede | Venue with address, maximum capacity and location. | RF19 |
| Evento | General information, dates, category, city, organizer and status (draft, under review, published, rejected). | RF19 |
| Plano / Sección / Silla | Structure of the venue: sections with capacity and price, and seats with their status (available, blocked, occupied). | RF9 |
| Reserva / DetalleReserva | Purchase of the attendee with their seats, status and expiry of the hold. | RF10 |
| Ticket (QR) | Unique code per reservation, status (valid, used, voided, expired) and attendance record. | RF11, RF24 |
| TransaccionPago | Reference, amount, normalized status, strategy used and provider identifier. | RF17 |
| NotificacionWebhook | Idempotent record of notifications received from the gateway (auditing). | RF17 |
| Cartera / MovimientoCartera | Compensatory balance and history of movements. | RF25 |
| Reembolso | Request, approval by the administrator and result. | RF25, RF29 |
| Comentario | Text, rating, reply to another comment and author. | RF26 |
| Notificacion / DeviceToken / PreferenciaNotificacion | Sent messages, device tokens and preferences. | RF16 |

## Annex A. Changes in version 2.0

| **Section** | **Change** |
|---|---|
| **Cover page** | Version 2.0 and revision history completed. |
| **1.2 / RF17 / RF25 /** **RF29** | The Wompi gateway is replaced by a sandbox payment gateway (CapySoft microservice) decoupled through the Strategy pattern; Wompi remains as a future strategy. The refund and wallet flows are redefined on the generic payment operation. |
| **1.2 Exclusions** | «solo Wompi» (“Wompi only”) is removed; the integration with real gateways is excluded in this version. «sistema de compartir eventos» (“event sharing system”) is removed from the scope (it contradicted the exclusions). |
| **2.1 / RF20 / RF21** | The contradiction microservices vs. N-tier is resolved: hybrid architecture (modular DDD monolith + independent Payment Service); total separation is an evolutionary goal. |
| **2.2** | The “Product functions” section is completed (it was empty). |
| **2.3 / RF24** | The roles are unified with the user manual; the QR validation is carried out by the organizer («personal de control», “control staff”, is removed). The erroneous reference to RF12 in RF24 is corrected (correct: RF11). |
| **3.1.3 / RNF3** | HTTP is corrected to HTTPS in production; the scope of the “two-step authentication” is clarified (verification by email code). |
| **RF7** | «Eliminar cuenta» (“Delete account”) is clarified (before, it mixed «Desactivar» and «Eliminar»): permanent deletion of personal data with anonymization of financial records. |
| **RF10 / RF11** | The “physical” validation of the payment by the organizer is removed; the confirmation is automatic according to the payment result. The seat, reservation and QR statuses are unified. |
| **RF13** | The title said ES/EN/PT/FR; it is corrected to ES/EN/PT/JA. |
| **RF16** | The reminders (48 h and 2 h before), which the description and the criteria had as different, are unified. |
| **RF8 / RF9 / RF19** | The publication flow with the administrator's approval, the event statuses, the creation in three steps and the administration dashboard modules described in the user manual are incorporated. |
| **RF26–RF29 (new)** | The requirements that were in the scope or in the manual but without an RF are added: ratings and comments, request for the organizer role, My Events and tickets, and financial control/reports/refunds. |
| **RNF1–RNF8** | They are ordered and RNF5 is corrected (it only mentioned Chrome and Android); RNF6 to RNF8 are added with metrics already present in the RFs. |
| **3.4** | The data model is updated (generic payment transactions, new entities). |

## Annex B. Assumptions and points to be validated

Decisions taken when consolidating this version that the team must confirm:

- Seat hold time: the manual shows a timer but not its duration; 10 minutes, configurable,
is suggested.

- QR validation: it is assumed that it is only carried out by the organizer of the event; if delegated
staff is required, a role must be added.

- Comments: any authenticated user is allowed; it remains to be decided whether it is limited to those who
made a purchase.

- Financial Control and Reports: the manual only mentions the modules; their scope in RF29 is a
proposal to be validated.

- Reason for rejection (requests and events): it is proposed to record it and notify it; the manual leaves the
point pending.

- The development framework of the web and mobile frontend is not defined in the SRS; only
expo-notifications is mentioned in RF16 as a conditional dependency.

---

<a id="doc-te-0007"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Historias_Usuario_TuEvento.md
id: TE-0007
title: "Historias_Usuario_TuEvento"
lang: en
source: 01_Especificacion_Requisitos/Historias_Usuario_TuEvento.docx
source_sha256: 1ce8926a6162ef66f4d62e25a06e8fe2e167b863727db1eef5ab0982cabc6e07
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "«Tabla de Contenido» is a manual table of contents: it keeps the page numbers of the original, which do not apply in Markdown; the indentation of the subentries is lost (pandoc converted it into a quotation)."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "The tables with merged cells or with lists/several paragraphs in the cells are written in HTML (pandoc), because GFM does not support them."
  - "Translation: the texts of the headers and footers of the original are kept in Spanish because they are literal texts of the original files."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0007
es_sha256: cc1a2bdee2be547308d7104138c8d65bdeedf83d2e065844312b7b5f2ca938d8
-->

# User stories

**CapySoft**

**User Stories Specification**

**TuEvento Project**

Project: TuEvento

Document: User Stories

Version: 1.0

**Team members**

Jhampier Santos Ortiz

Cristofer David Lozano Contreras

Ficha (training group): 3145556

# Version Control

| **Version** | **Date** | **Description** | **Authors** |
|----|----|----|----|
| 1.0 | July 2026 | Initial version of the User Stories, reviewed and validated for consistency with the Requirements Specification Document (SRS) of the TuEvento system. | Jhampier Santos Ortiz, Cristofer David Lozano Contreras |

# Table of Contents

**1. Introduction 4**

**2. Objective 4**

**3. Scope 4**

**4. Glossary 4**

**5. User Stories 6**

5.1. Epic: Account Management and Authentication 6

5.2. Epic: User Profile Management 9

5.3. Epic: Administration Management 10

5.4. Epic: Event Management and Layout Design 11

5.5. Epic: Reservations and Ticketing 12

5.6. Epic: Payments and Balance Wallet 14

5.7. Epic: Attendance Validation 16

5.8. Epic: Notifications 17

5.9. Epic: Dashboard and Control Panel 18

5.10. Epic: Customization and Accessibility 19

5.11. Epic: Search and Filters 20

5.12. Epic: Architecture and Platform 21

# 1. Introduction

This document contains the User Stories (HU) of the “TuEvento” system, developed by CapySoft. Each story describes a functional need from the perspective of an actor of the system (user, attendee, organizer, administrator or development team) and is directly linked to one or more Functional Requirements (RF) defined in the project's Software Requirements Specification (SRS) Document.

This document has been prepared and reviewed following good Requirements Engineering practices, the guidelines of the IEEE 830/29148 standard and the Scrum framework, guaranteeing full traceability between each User Story and its corresponding Functional Requirement.

# 2. Objective

To define and document the User Stories of the TuEvento system in a clear, verifiable and traceable way, so that they serve as direct input for the planning, estimation and development of the project's sprints, ensuring their complete consistency with the SRS.

# 3. Scope

This document covers all the Functional Requirements (RF1 to RF25) established in the SRS of the TuEvento system, grouped into the following epics:

- Account Management and Authentication

- User Profile Management

- Administration Management

- Event Management and Layout Design

- Reservations and Ticketing

- Payments and Balance Wallet

- Attendance Validation

- Notifications

- Dashboard and Control Panel

- Customization and Accessibility

- Search and Filters

- Architecture and Platform

The Non-Functional Requirements (RNF) of the system, which are defined in the SRS, as well as any functionality not contemplated in that document, are outside the scope of this document.

# 4. Glossary

**HU:** User Story: brief description of a functionality from the perspective of an actor of the system.

**RF:** Functional Requirement defined in the project's SRS.

**SRS:** Software Requirements Specification (Especificación de Requerimientos de Software).

**JWT:** JSON Web Token, mechanism used for the secure authentication and authorization of users.

**Refresh Token:** Long-lived token used to renew the Access Token without requiring new credentials.

**QR:** Quick Response code used as digital proof of reservation and access control.

**OAuth 2.0:** Standard authorization protocol used for authentication through social networks.

**Sandbox payment gateway:** Payment gateway for testing the payment flow, connected to the backend, that processes transactions without real charges.

**DDD:** Domain-Driven Design, a software design approach oriented to the business domain.

**API Gateway:** Component that centralizes the routing, authentication and traffic control of the requests to the backend.

# 5. User Stories

## 5.1. Epic: Account Management and Authentication

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-001 — User registration with email verification</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF1</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to register in the system by entering my name, email and password, and verify my account through a code sent to my email, in order to create a valid account and access the features of the platform.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must request name, email and password to complete the registration.</p></li>
<li><p>The system must generate and send a 6-digit verification code to the email provided.</p></li>
<li><p>If the code entered is correct, the system must register the account and redirect the user to the login screen.</p></li>
<li><p>If the email already exists or the code is incorrect or has expired, the system must notify the corresponding error.</p></li>
<li><p>The system must not allow registration with a previously registered email.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-002 — Authentication through social networks</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF2</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to link my account with Facebook or Gmail through OAuth 2.0, in order to log in to the system without the need to enter additional credentials.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow selecting Facebook or Gmail as the authentication provider.</p></li>
<li><p>The system must request the permissions corresponding to the selected provider.</p></li>
<li><p>If the linking is successful, the account must remain associated for future logins.</p></li>
<li><p>If the user cancels the authorization or the provider does not respond, the system must show an error message or notification without altering the account.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-003 — User login</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF3</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a registered user, I want to log in by entering my email and password, in order to access the protected features of the system according to my role.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must validate that the email and password fields are not empty.</p></li>
<li><p>The system must verify that the email is registered and that the password matches the stored one.</p></li>
<li><p>If the credentials are correct, the system must establish an active session and redirect to the main page.</p></li>
<li><p>If the credentials are incorrect, the system must show an error message and allow retrying the login.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-004 — Password recovery</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF5</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a registered user, I want to request the recovery of my password through my email, in order to restore my access to the system in case I forget it.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must validate the format of the email entered before processing the request.</p></li>
<li><p>If the email is registered, the system must send a unique verification code.</p></li>
<li><p>If the email is not registered, the system must show an error message.</p></li>
<li><p>The new password must meet the security requirements: minimum 8 characters, one uppercase letter, one number and one special character.</p></li>
<li><p>The verification code used must be invalidated after its use to prevent reuse.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-005 — Logout</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF6</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an authenticated user, I want to close my active session from the system, in order to protect my information and avoid unauthorized access on shared devices.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>When “Log out” («Cerrar sesión») is selected, the system must invalidate the user's active token or session.</p></li>
<li><p>The system must redirect the user to the login screen.</p></li>
<li><p>The system must not allow access to protected features after logout.</p></li>
<li><p>If a connection error occurs during logout, the system must notify it and allow retrying the action.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-006 — Permanent account deletion</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF7</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an authenticated user, I want to permanently delete my account and all the associated information, in order to stop using the platform and guarantee that my data does not remain stored.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must request explicit confirmation before deleting the account.</p></li>
<li><p>The system must validate the identity of the user before proceeding with the deletion.</p></li>
<li><p>After the deletion, the system must irreversibly erase the account and its associated data.</p></li>
<li><p>The system must redirect the user to the home screen with a confirmation message.</p></li>
<li><p>The system must prevent later access with the deleted credentials.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-007 — Session renewal through Refresh Token</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Account Management and Authentication</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF15</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an authenticated user, I want the system to automatically renew my expired access token using a valid Refresh Token, in order to continue using the platform without the need to log in again.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must generate a new Access Token when the current one has expired and the Refresh Token is valid.</p></li>
<li><p>The token renewal must be completed in less than 2 seconds.</p></li>
<li><p>If the Refresh Token is invalid, expired or revoked, the system must close the session and request authentication again.</p></li>
<li><p>The system must record the use of Refresh Tokens for auditing purposes and allow their revocation.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.2. Epic: User Profile Management

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-008 — User profile creation</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>User Profile Management</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF4</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a registered user, I want to complete my personal information (first name, last name, verified email and password), in order to configure my initial profile within the system.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must request the mandatory fields: first name, last name, verified email and password.</p></li>
<li><p>The system must confirm the creation of the profile through a success message.</p></li>
<li><p>The information must be stored persistently in the database.</p></li>
<li><p>If a social network was linked, the association must remain recorded for future logins.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-009 — User profile editing</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>User Profile Management</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF4</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a registered user, I want to edit my personal data (first name, last name, date of birth and address) at any time, in order to keep my information within the system up to date.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow editing the profile information after the initial creation.</p></li>
<li><p>The changes must be saved persistently in the database.</p></li>
<li><p>If a failure occurs during the update, the system must not alter the previous information and must notify the error.</p></li>
<li><p>The user must have an active session to access the editing of their profile.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.3. Epic: Administration Management

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-010 — Review and approval of organizer requests</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Administration Management</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF8</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Administrator</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an administrator, I want to review the documents sent by the users who request to become organizers and accept or reject those requests, in order to enable the creation of events on the platform in a controlled way.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must show the list of organizer requests with their associated documents.</p></li>
<li><p>The administrator must be able to accept or reject each request.</p></li>
<li><p>The system must record the result of the review (accepted or rejected).</p></li>
<li><p>Once the request is accepted, the user must acquire permissions to create events.</p></li>
<li><p>If a connection error occurs during the operation, the system must notify it without completing the action.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.4. Epic: Event Management and Layout Design

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-011 — Design and publication of the event floor plan</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Event Management and Layout Design</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF9</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Organizer</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an organizer, I want to design and publish the digital floor plan of the site where my event will take place, being able to save progress without publishing it, in order to enable seat selection by the attendees.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow creating a floor plan from scratch or from an existing one.</p></li>
<li><p>The system must allow saving drafts of the design without publishing them.</p></li>
<li><p>The system must request confirmation before publishing the floor plan.</p></li>
<li><p>Only users with the organizer role must be able to create and publish floor plans.</p></li>
<li><p>Once published, the floor plan must be displayed correctly in the seat selection interface.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-012 — Deletion of the event floor plan</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Event Management and Layout Design</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF9</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Organizer</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an organizer, I want to delete a previously created event floor plan, in order to correct or discard designs that are no longer necessary.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow deleting floor plans that do not have associated active reservations.</p></li>
<li><p>The system must request confirmation before deleting the floor plan.</p></li>
<li><p>If the connection is interrupted during the process, the system must notify that the deletion was not completed.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-013 — Complete management of events from the web version</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Event Management and Layout Design</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF19</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Organizer</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an organizer, I want to create events, design the floor plan of the stage, add sections and distribute seats exclusively from the web version, in order to fully manage the structure of my events.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The organizer must be able to create, edit and save events completely from the web version.</p></li>
<li><p>The floor plan editor must allow adding, moving or deleting elements without restrictions.</p></li>
<li><p>The mobile version must not allow access to event creation or editing tools.</p></li>
<li><p>The saved changes must be reflected correctly when viewed from the mobile application.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.5. Epic: Reservations and Ticketing

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-014 — Seat reservation</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Reservations and Ticketing</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF10</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to select and reserve an available seat for an event of interest to me, in order to secure my place before it is taken by another user.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must block the selected seat from the moment the user chooses it.</p></li>
<li><p>The reservation must be recorded in the “pending confirmation” status until the payment is validated.</p></li>
<li><p>If the seat was already reserved by another user, the system must notify it and request the selection of another seat.</p></li>
<li><p>If the reservation is not confirmed within the defined time, the seat must be released automatically.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-015 — Generation of a QR code per reservation</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Reservations and Ticketing</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF11</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to receive a unique QR code associated with my confirmed reservation, in order to use it as proof of access to the event.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must generate a unique QR code per reservation, regardless of the number of seats.</p></li>
<li><p>The QR must contain the essential information of the event (name, date, number and location of the seats).</p></li>
<li><p>The QR must be sent to the user's email.</p></li>
<li><p>The QR must update its status to “valid” only when the payment is confirmed.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-016 — Purchase of tickets from the mobile application</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Reservations and Ticketing</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF18</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to view the floor plan of the event, select available seats and complete the purchase of tickets from the mobile application, in order to acquire my ticket without the need for layout design tools.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must display the floor plan of the event correctly in the mobile application.</p></li>
<li><p>The user must be able to select only available seats.</p></li>
<li><p>The user must be able to complete the purchase without access to editing or layout design options.</p></li>
<li><p>If a seat is already occupied, the system must update the availability before continuing with the purchase.</p></li>
<li><p>After the purchase, the ticket or QR code must be available to the user.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.6. Epic: Payments and Balance Wallet

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-017 — Payment for an event through the sandbox payment gateway</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Payments and Balance Wallet</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF17</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to pay for my reservation using the sandbox payment gateway, in order to confirm my attendance at the event and obtain my entry QR code.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must create the transaction and wait for the confirmation through the gateway webhook.</p></li>
<li><p>If the payment is approved, the reservation must be activated and the corresponding QR generated.</p></li>
<li><p>If the payment is rejected, the reservation must not be created.</p></li>
<li><p>If the payment remains pending, the system must record the “Pending” status.</p></li>
<li><p>The system must retry the processing if the webhook fails.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-018 — Consultation of the compensatory balance and its history</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Payments and Balance Wallet</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF25</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to consult my compensatory balance and the history of movements generated by event cancellations, in order to know the amounts available in my favour within the platform.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must automatically credit the balance when a paid event is officially cancelled by the organizer.</p></li>
<li><p>The updated balance must be shown on the user's Dashboard.</p></li>
<li><p>Each balance movement must be recorded in the transaction history.</p></li>
<li><p>The balance must not be generated by changes of mind or non-attendance of the user.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-019 — Use of the compensatory balance in new purchases</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Payments and Balance Wallet</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF25</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to use my available compensatory balance to pay for the purchase of tickets for other events, in order to take advantage of the value generated by a previous cancellation.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow using the balance only within the platform.</p></li>
<li><p>The balance used must be deducted in real time at the moment of the purchase.</p></li>
<li><p>If the balance is insufficient, the system must block the purchase.</p></li>
<li><p>The system must not allow manual top-up or direct withdrawal of the balance.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-020 — Request for an external refund of the compensatory balance</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Payments and Balance Wallet</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF25</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to request the external refund of my compensatory balance, in order to recover the corresponding value through the sandbox payment gateway.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The external refund request must be managed exclusively through the sandbox payment gateway.</p></li>
<li><p>The request must require prior approval from an administrator before being processed.</p></li>
<li><p>If the gateway rejects the refund, the balance must remain in the user's wallet.</p></li>
<li><p>The user must receive a notification with the result of the request.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-021 — Approval of external refund requests</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Payments and Balance Wallet</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF25</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Administrator</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an administrator, I want to review and approve the requests for the external refund of the compensatory balance, in order to authorize their processing through the sandbox payment gateway.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must show the administrator the pending refund requests.</p></li>
<li><p>The administrator must be able to approve or reject each request.</p></li>
<li><p>Only the approved requests must be sent to the sandbox payment gateway for processing.</p></li>
<li><p>The system must record the administrator's decision with traceability.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.7. Epic: Attendance Validation

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-022 — Attendance validation through a QR code reader</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Attendance Validation</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF24</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Organizer</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an organizer, I want to scan the QR code presented by the attendee at the moment of entering the event, in order to validate their reservation and authorize their access.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must validate the QR in real time from mobile devices.</p></li>
<li><p>If the QR is valid, is not duplicated and belongs to the corresponding event, the system must record the attendance and authorize the access.</p></li>
<li><p>If the QR is invalid, expired or already used, the system must deny access and notify the validator.</p></li>
<li><p>The system must show differentiated messages according to the result of the validation (authorized, invalid, expired, already used).</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.8. Epic: Notifications

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-023 — Reception of push notifications in real time</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Notifications</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF16</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to receive push notifications about relevant events (payment confirmed, changes in reservations, administrative communications), in order to stay informed in real time about the activity of my account.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must automatically register the device token when logging in.</p></li>
<li><p>Payment confirmation notifications must be processed in less than 5 seconds.</p></li>
<li><p>The user must be able to configure their notification preferences (enable/disable specific types).</p></li>
<li><p>If the user does not have push notification permissions enabled, the system must send the notification by email as an alternative.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-024 — Automatic reminders of reserved events</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Notifications</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF16</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to receive automatic reminders before the date of an event I have reserved, in order not to forget my attendance.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must send automatic reminders 48 hours and 2 hours before the reserved event.</p></li>
<li><p>If the user cancels their reservation, the system must automatically cancel the pending reminders.</p></li>
<li><p>If a reminder fails due to a scheduling error, the system must record it and retry in the next cycle.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.9. Epic: Dashboard and Control Panel

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-025 — Dashboard for attendees</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Dashboard and Control Panel</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF14</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Attendee</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an attendee, I want to view on a dashboard the available events, my reserved events, the status of my reservations and my notifications, in order to have a clear and centralized view of my activity on the platform.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The Dashboard must be shown immediately after login.</p></li>
<li><p>The Dashboard must load in less than 3 seconds under normal network conditions.</p></li>
<li><p>The information shown must be accurate and consistent with the attendee role.</p></li>
<li><p>If an error occurs when loading the data, the system must show a message indicating the failure.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-026 — Dashboard for organizers</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Dashboard and Control Panel</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF14</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Organizer</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an organizer, I want to view on a dashboard the events I have created, the number of reservations per event and the QR validation status, in order to manage my events efficiently.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The Dashboard must show the events created by the organizer and their associated reservations.</p></li>
<li><p>The Dashboard must allow direct access to the layout design and event creation module.</p></li>
<li><p>The information must be updated in real time according to the backend data.</p></li>
<li><p>The Dashboard must load in less than 3 seconds under normal network conditions.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-027 — Dashboard for administrators</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Dashboard and Control Panel</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF14</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Administrator</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As an administrator, I want to view on a dashboard the pending organizer requests, the general events of the system and the active users, in order to supervise and manage the general operation of the platform.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The Dashboard must show the pending organizer requests.</p></li>
<li><p>The Dashboard must allow direct access to the request validation and approval module.</p></li>
<li><p>The information must reflect the current status of the events and users of the system.</p></li>
<li><p>If the user's role is not correctly identified, the system must redirect to the login screen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.10. Epic: Customization and Accessibility

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-028 — Change of the interface language</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Customization and Accessibility</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF13</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to change the language of the interface between Spanish, English, Portuguese and Japanese, in order to use the platform in the language of my preference.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow changing the language at any time from the settings menu.</p></li>
<li><p>All visible texts must be updated immediately without completely reloading the application.</p></li>
<li><p>If there is no translation available for an element, the system must show it in the default language (Spanish).</p></li>
<li><p>If an error occurs when loading the language package, the system must notify the user.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-029 — Customization of the visual theme of the interface</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Customization and Accessibility</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF22</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to select between different predefined visual themes (light, dark, purple and blue), in order to customize the appearance of the application according to my preference.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must offer 4 predefined themes: light, dark, purple and blue.</p></li>
<li><p>The theme change must be applied instantly without reloading the application.</p></li>
<li><p>The selected theme must persist between sessions and be consistent between the web and mobile versions.</p></li>
<li><p>If the theme configuration is corrupt, the system must restore the light theme by default.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.11. Epic: Search and Filters

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-030 — Event filtering</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Search and Filters</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF23</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>Medium</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user, I want to filter events by location, name, city, availability, budget and type of event, in order to find more efficiently the events that match my interests.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The system must allow entering at least one search criterion (name, date or city) to run the filter.</p></li>
<li><p>The system must show the events that meet the conditions specified by the user.</p></li>
<li><p>If there are connection problems during the search, the system must show an error message and allow retrying.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 5.12. Epic: Architecture and Platform

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-031 — Basic operation of the application on iOS devices</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Architecture and Platform</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF12</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>User</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a user of an iOS device, I want to access the essential features of the system (viewing events, profile and reading QR codes), in order to use the platform from my device even if it does not have all the functions available on other platforms.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The application must allow opening, loading data and running the basic functions on iOS.</p></li>
<li><p>At least one compatibility test must be carried out that confirms the general operation of the system.</p></li>
<li><p>If the connection with the server fails, the system must notify the user to check their internet connection.</p></li>
<li><p>If any functionality cannot be run correctly, the system must show a partial incompatibility message.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-032 — Migration of the backend to a microservice-oriented architecture</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Architecture and Platform</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF20</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Development Team</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a development team, we want to separate the functionalities of the system into independent services (users, events, payments, notifications and administration) communicated through APIs and message queues, in order to guarantee the scalability, maintainability and fault tolerance of the platform.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The services must be able to be deployed and scaled independently.</p></li>
<li><p>The communication between services must be carried out through contracted APIs and asynchronous events.</p></li>
<li><p>Each service must have its own database while maintaining eventual consistency.</p></li>
<li><p>If a service fails, the system must activate a circuit breaker with a contingency response.</p></li>
<li><p>The API Gateway must manage authentication, rate limiting and routing of the requests.</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table style="width:99%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 73%" />
</colgroup>
<thead>
<tr>
<th colspan="2"><strong>HU-033 — Reorganization of the backend into an N-tier architecture with DDD</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Epic</strong></td>
<td>Architecture and Platform</td>
</tr>
<tr>
<td><strong>Associated RF</strong></td>
<td>RF21</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>Development Team</td>
</tr>
<tr>
<td><strong>Priority</strong></td>
<td><strong>High</strong></td>
</tr>
<tr>
<td><strong>User story</strong></td>
<td><em>As a development team, we want to reorganize the backend into modules by domain with Domain, Application, Infrastructure and Presentation layers, in order to achieve maintainable code prepared for a future migration to microservices.</em></td>
</tr>
<tr>
<td><strong>Acceptance criteria</strong></td>
<td><ul>
<li><p>The modules must be organized by domain (Users, Events, Payments, Notifications, Administration).</p></li>
<li><p>The business logic must be concentrated in the Domain layer, without incorrect dependencies between layers.</p></li>
<li><p>The Application layer must contain the use cases without duplicated logic.</p></li>
<li><p>The Presentation layer must expose the controllers using DTOs.</p></li>
<li><p>If an error occurs in a module, it must be isolated without affecting the operation of the others.</p></li>
</ul></td>
</tr>
</tbody>
</table>


---

## Headers and footers of the original

- **Footer** (`word/footer1.xml`): text «CapySoft · TuEvento — Página {PAGE} de {NUMPAGES}»
- **Header** (`word/header1.xml`): text «TuEvento — Historias de Usuario»

---

<a id="doc-te-0005"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento.md
id: TE-0005
title: "Confirmacion de RF - Tu Evento"
lang: en
source: 01_Especificacion_Requisitos/Confirmacion de RF - Tu Evento.docx
source_sha256: b5c6a09d7071c4bd5ed5915c57fc9d35f5877087520c41c37a34cae3392b32a8
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Translation: the text inside the screenshots is not translated."
  - "Translation: the name of the training centre («Centro de la empresa y los servicios- SENA sede industria») is kept in Spanish because it is a proper name."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0005
es_sha256: 72a088f58b3b3d5effe26b77bbab2d90eee8d8d9a755a13710e318a3b4cdc15f
-->

# Functional requirements confirmation

**Functional Requirements Confirmation\**

**Apprentices:\
Cristofer David Lozano Contreras**

**Jhampier Santos Ortiz**

**Capysoft-2025**

**Instructor:\
Carlos Julio Cadena Sarasty**

**Centro de la empresa y los servicios- SENA sede industria**

**Neiva – Huila**

**RF1 – User registration**

It allows the user to create an account by entering their name, email and password.\
The system sends a verification code to the email and, when it is validated correctly, registers the account and redirects the user to the login page.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image1.png" style="width:6.1375in;height:3.06319in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image2.png" style="width:6.1375in;height:3.23403in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image3.png" style="width:3.55208in;height:3.15764in" /><img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image4.png" style="width:6.1375in;height:2.86667in" />

### 

### 

### 

### 

### 

### 

### **RF2 – Authentication with social networks (OAuth)**

It allows the user to log in or link their account using social networks such as **Facebook or Gmail** through the **OAuth 2.0** protocol.\
When access is authorized, the system associates the account and allows future logins without entering credentials manually.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image5.png" style="width:4.36458in;height:3.32708in" /><img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image1.png" style="width:6.1375in;height:3.06319in" />

### **RF3 – User login**

It allows the user to access the system by entering their previously registered **email and password**.\
The system validates the credentials and, if they are correct, **starts the session** and redirects the user to the main page.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image6.png" style="width:6.1375in;height:2.97569in" />

### **RF4 – User profile management**

It allows the user to **create, edit and update their personal information**, such as their number, date of birth and address.\
The system saves the changes in the database and shows a confirmation message when the action is completed (It should be clarified that this is functional only in the mobile version; it will be added to the web version in later versions)

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image7.png" style="width:2.30208in;height:4.77083in" /><img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image8.png" style="width:2.21875in;height:4.75in" />

### **RF5 – Recover password**

It allows the user to **recover access to their account** by entering their registered email.\
The system sends a **verification code** to the email to allow them to **reset their password** and create a new one securely.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image9.png" style="width:5.66597in;height:2.57292in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image10.png" style="width:5.28125in;height:2.79167in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image11.png" style="width:3.41736in;height:3.34444in" />

### **RF6 – Log out**

It allows the user to **end their active session** by clicking the exit button.\
The system **invalidates the session** and redirects the user to the login screen, guaranteeing the **security and privacy** of their account. (Also available in the web version)

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image12.png" style="width:2.36458in;height:4.80278in" />

### **RF7 – Permanent deletion of the user account**

It allows the user to **permanently delete their account and all their data** from the system settings.\
The system requests **confirmation before deleting** and, once the process is completed, **redirects the user to the home screen** with a confirmation message.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image13.png" style="width:6.1375in;height:2.90972in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image14.png" style="width:6.1375in;height:2.94514in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image15.png" style="width:6.1375in;height:3.23333in" />

###  **RF8 – System administration module**

It allows the **administrator to access an exclusive dashboard** where they can **review, accept or reject organizer requests**.\
The system identifies the administrator role when logging in and shows the corresponding management options.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image16.png" style="width:6.1375in;height:2.60278in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image17.png" style="width:6.1375in;height:2.36597in" />

### **RF9 – Editing of the structure**

It allows the **organizer to create, edit or delete the floor plan of the event site** through a graphical interface.\
The system associates the design with the event and shows it to users for **seat selection** once it is published.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image18.png" style="width:6.1375in;height:2.88333in" />

### **RF10 – Seat reservation**

It allows the **user to select and reserve a seat** for an event from the scheduling interface.\
The system **temporarily blocks the seat** until the organizer validates the payment, guaranteeing that it cannot be reserved by another user.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image19.png" style="width:6.1375in;height:2.12847in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image20.png" style="width:6.1375in;height:3.15278in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image21.png" style="width:6.1375in;height:3.07153in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image22.png" style="width:6.1375in;height:2.97153in" />

### **RF11 – Generation and validation of a QR code per reservation**

It allows the **system to generate a unique QR code** for each reservation made.\
The code will contain the event information (name, date and seats) and will be sent to the user's email.\
The **organizer will validate the QR** when confirming the payment, changing its status from *pending* to *valid* to allow access to the event, this from the mobile app.

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image23.png" style="width:2.23958in;height:3.90556in" /><img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image24.png" style="width:6.1375in;height:2.99236in" />

<img src="../_assets/01_Especificacion_Requisitos/Confirmacion_de_RF_Tu_Evento/media/image25.png" style="width:2.3125in;height:3.88611in" />

---

<a id="doc-te-0006"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Documento_de_aceptacion_de_Requisitos.md
id: TE-0006
title: "Documento de aceptacion de Requisitos"
lang: en
source: 01_Especificacion_Requisitos/Documento de aceptacion de Requisitos.pdf
source_sha256: fea1c865dc9d3404db9fb02f0daa63d9f9e597e18f2df58d4b860c682e552cc1
conversion: "pdfplumber 0.11.10 following the structure tree of the tagged PDF; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "The structure-tree method does not extract images: the meeting image and the two signatures on page 5 are cropped from the original at 200 dpi and linked in their position; the repeated header logo (pages 1-5) goes in the final section."
  - "The «•» bullets of the original are inside the body of the list element (not in its label); they are written as the Markdown bullet «- » without repeating the character."
  - "Untagged text (pagination artifact) omitted on 5 of 5 pages: «{n}»."
  - "Bold, italics and monospaced font (Courier) of the original are not kept."
  - "GFM tables with the first row as header; the paragraphs inside a cell are separated with <br>."
  - "Translation: the text inside the images (meeting photo, signatures and logo) is not translated."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0006
es_sha256: bcdecd695ad925d3bcc7650f6aff9a21c30971190e92a9516bce49b0579604a9
-->

# Requirements acceptance record

Requirements acceptance record

Andrade Bermeo Carlos Francisco

Cano Narváez Keiner Andrés

Lozano Contreras Cristofer David

Rivera Suarez Ángel Farid

Santos Ortiz Jhampier

Análisis y Desarrollo de Software (Software Analysis and Development)

(2899747)

Servicio Nacional de Aprendizaje (National Learning Service)

September 10, 2025

Project: Tu evento

Record No.: 1

Date: 10/09/2025

Place: Neiva-Huila

Participants:

Cano Narváez Keiner Andrés (Stakeholder)

Lozano Contreras Cristofer David (Scrum Master)

Andrade Bermeo Carlos Francisco (Frontend Developer)

Rivera Suarez Angel Farid (Frontend Developer)

Santos Ortiz Jhampier (Frontend Developer)

Objective of the Record: The objective of this record is to formalize the start of the “Tu Evento” project, recording the meeting held with the work group, in which the previously established requirements were validated and accepted. This seeks to guarantee a mutual understanding of the scope, the initial guidelines and the responsibilities of the parties involved.

- Client Remarks:
- 1. It is suggested that events can be classified by category (example: cultural, sports, academic).
- 2. The client requests that notifications include both alerts within the application and via email.
- Feedback
- 1. The requirements meet the client's initial expectations.
- 2. Minor adjustments were identified that do not affect the main scope, but improve the user experience.
- 3. The client validates the record on the condition that the remarks are considered in later development phases.

Commitment:

The project participants commit to:

- Comply with the established requirements.
- Maintain constant and effective communication to ensure that the development meets expectations.
- Respect the roles assigned within the work team.

Boundary:

This project does not include in its development:

- Integration with online payment gateways
- The development will focus only on the features agreed in the initial requirements, without considering later changes or additions that are not formally approved.

Scope:

The scope of the “Tu Evento” project will be:

- The design, development and implementation of a web and mobile application that allows users to view, manage and participate in events.
- Integration of features such as: creation and viewing of events, user registration, authentication, role management and communication with the organizers.

Image of the meeting:

![Image of the meeting (page 5 of the original)](../_assets/01_Especificacion_Requisitos/Documento_de_aceptacion_de_Requisitos/pagina-05-imagen-reunion.png)

![Signature on the left line (page 5 of the original)](../_assets/01_Especificacion_Requisitos/Documento_de_aceptacion_de_Requisitos/pagina-05-firma-izquierda.png) ![Signature on the right line (page 5 of the original)](../_assets/01_Especificacion_Requisitos/Documento_de_aceptacion_de_Requisitos/pagina-05-firma-derecha.png)

_________________________ _________________________

Stakeholder's Signature Scrum Master's Signature

---

## Headers and footers of the original

- **Header** (pages 1-5): «TU EVENTO» logo in the top-left corner<br>![Header logo of the original](../_assets/01_Especificacion_Requisitos/Documento_de_aceptacion_de_Requisitos/logo-cabecera.png)

---

<a id="doc-te-0011"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Presentacion_de_requisitos.md
id: TE-0011
title: "Presentación de requisitos"
lang: en
source: 01_Especificacion_Requisitos/Presentación de requisitos.pdf
source_sha256: 8a992fe953674e77a209a848bd580c0948f54d4684a1b92227abdfa6390bcb36
conversion: "pdfplumber 0.11.10 (text boxes) + page image at 100 dpi; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Design PDF (Canva): the text is grouped by text boxes (nearby lines that overlap) and ordered from top to bottom and from left to right; the reading order of the composition may differ and the image of each page is the faithful reference."
  - "Each visual line break inside a box is kept with <br>."
  - "Layout, colours, typefaces, shapes, arrows and decorative images are only in the image of each page (100 dpi)."
  - "The Canva characters are not linked to the tag tree of the PDF, so the tagged PDF method is not used."
  - "Translation: the line breaks (<br>) of the Spanish text are kept at approximately the same position; in English they do not match the line ends of the original."
  - "Translation: the text inside the page images is not translated."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0011
es_sha256: 28883db45e50a570df9ea46940fc7e12d6e12ae0a60fb82b2b3e7bc7f5d8dbd8
-->

# Requirements presentation

## Page 1

![Page 1 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-1.png)

PRESENTATION OF THE

REQUIREMENTS REPORT<br>
“TU EVENTO”

## Page 2

![Page 2 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-2.png)

TU EVENTO

This requirements report corresponds to the<br>
“Tu Evento” project, a system designed to<br>
provide the layout design and logistics management of<br>
any type of event.

The purpose of the platform is to offer companies<br>
and organizers a digital tool that allows them<br>
to plan, structure and visualize the<br>
logistics of their events in an efficient and<br>
centralized way.

## Page 3

![Page 3 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-3.png)

SCOPE OF THE

SYSTEM

The main scope of the “Tu Evento” system will be the<br>
design and development of a platform that facilitates the<br>
layout design and logistics management of events, differentiating<br>
its features according to the environment:

Web Platform:<br>
It allows companies and<br>
organizers to carry out the complete<br>
layout design of the events, managing<br>
aspects such as location, resources,<br>
schedules, categories and other<br>
logistics elements.

Mobile Application:<br>
It allows users to view the<br>
events created on the web<br>
platform.<br>
It provides the option to reserve places<br>
in the available events.

## Page 4

![Page 4 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-4.png)

OTHER

FEATURES

USER<br>
MANAGEMENT

NOTIFICATIONS

RESERVATION<br>
SYSTEM

It sends alerts and<br>
reminders to the<br>
users about<br>
events.

It allows registering,<br>
administering and<br>
controlling the<br>
users of the<br>
platform, assigning<br>
roles and access according to<br>
the type of profile<br>
(organizer or<br>
attendee).

It makes it easy for users<br>
to reserve places in<br>
the available<br>
events,<br>
guaranteeing a<br>
fast, secure<br>
and simple process.

## Page 5

![Page 5 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-5.png)

CONCLUSION

The definition and validation of the requirements of the<br>
“Tu Evento” system make it possible to establish a solid basis for<br>
the development of the platform.

With the user management, reservation system<br>
and notification features. It is ensured that the<br>
application meets both the needs of the<br>
organizers, by providing layout design and logistics<br>
tools from the web, and those of the attendees, by<br>
offering from the mobile application a simple<br>
and efficient experience to view and reserve events.

## Page 6

![Page 6 of the original](../_assets/01_Especificacion_Requisitos/Presentacion_de_requisitos/pagina-6.png)

THANK

YOU VERY

MUCH!

---

<a id="doc-te-0008"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Informe_evaluativo_Tu_Evento.md
id: TE-0008
title: "Informe evaluativo Tu Evento"
lang: en
source: 01_Especificacion_Requisitos/Informe evaluativo Tu Evento.docx
source_sha256: ea815304ddc673108ab044d29bbbe38f8b234047ccd7019a9434fc8049a6ffa0
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "The hyphens «- » written as text at the start of 4 lines are escaped as «\\- » so that GFM does not turn them into bullets."
  - "The first paragraph has the Title style; pandoc moves it to the metadata and does not write it in GFM. It was restored by hand as a level-1 heading, with the exact text of the original."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0008
es_sha256: b9af7ded2431ada9ff88fc45d721c43b3dd5bbe729d3b3d05fdabe4bf60cc910
-->

# Evaluation Report on the SRS Document – “Tu Evento” Project

**Project:** Tu Evento

**Evaluated Document:** Software Requirements Specification (SRS) – Version 1.0

**Evaluator:** Keiner Andres Cano Narvaez

**Date:** 24/09/2025

# 1. Objective of the Evaluation

The purpose of this report is to analyse the SRS document delivered for the “Tu Evento” system and to determine whether it meets the clarity and quality aspects required in an analysis document. Improvement recommendations are also provided.

# 2. Scope of the Analysed Document

The SRS contains:\
\- Introduction (purpose, scope, definitions, personnel involved).\
\- General description (product perspective, functions, users, constraints).\
\- Specific requirements (functional and non-functional).

# 

# 

# 

# 

# 

# 3. Evaluation by Criteria

| **Evaluated Aspect** | **Remarks** | **Compliance** |
|----|----|----|
| **Clarity** | The functional requirements are well structured with inputs, outputs, pre/post conditions. | Yes |
| **Consistency** | No contradictions are detected. | Yes |
| **Non-Functional Requirements** | They include security, usability, compatibility and responsive design. | Yes |
| **Supporting Models** | Interfaces are mentioned, but there are no complementary diagrams such as sequence or activity diagrams. | Partial |

# 

# 

# 4. Conclusions

The SRS document for the “Tu Evento” system is quite complete regarding functional requirements, which are well structured and documented with preconditions, postconditions and error handling. However, it has one shortcoming:\
\- Lack of additional diagrams that help to understand the dynamics of the system (e.g. activity, class or sequence diagrams).\
\
In general, the document meets the basic standards of an SRS, but it requires adjustments to align better with good software engineering practices.

# 5. Improvement Recommendations

1\. Incorporate measurable acceptance criteria for each requirement (e.g. load times, availability percentage, security metrics).

2\. Detail performance requirements (e.g. concurrency, maximum user capacity).

3\. Include additional diagrams (activity, sequence, class) to support understanding.

---

<a id="doc-te-0015"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Recoleccion_de_datos/survey_Your_even.md
id: TE-0015
title: "survey-Your even"
lang: en
source: 01_Especificacion_Requisitos/Recoleccion de datos/survey-Your even.docx
source_sha256: d38372c19731ba48ffb929a7f75f2af24a52d01e59256cc643f1e45e3338bcde
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0015
es_sha256: a9013db9bcbeddd000f0ca92f787c2c0134d67d21632a3dc5a6db438f2c0c3a8
-->

# Data collection — survey

This is the link to take the survey created for collecting information:

https://docs.google.com/forms/d/e/1FAIpQLSdMdYqbBKMqqFJozL-J-no73syPJHUWpwO8kc5EwLKCrk9RIg/viewform

---

<a id="doc-te-0012"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento.md
id: TE-0012
title: "Análisis Encuesta TuEvento"
lang: en
source: 01_Especificacion_Requisitos/Recoleccion de datos/Análisis Encuesta TuEvento.docx
source_sha256: d95c4567150f67f35b820ee459d9189f46f8c4ca834efcd82a756f8d3feb69a1
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the text inside the charts (images) is not translated."
  - "Translation: the name of the training centre («Centro de la Industria la empresa y los Servicios») is kept in Spanish because it is a proper name."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0012
es_sha256: 73e9b3ef2545e39af46dfea2af907904baea24ad0b8390482f050f4db3857191
-->

# Survey analysis

**Survey Data Processing and Analysis**

**Training Project**

**Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development)**

**“Tu Evento”**

Team members:

**Cristofer David Lozano Contreras**

**Jhampier Santos Ortiz**

**Centro de la Industria la empresa y los Servicios**

**Neiva, Huila**

**Year 2025**

**Summary of Collected Data**

1.  **How old are you?**

- Under 18

- 18-24 years

- 25-34 years

- 35-44 years

- 45 or more years

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image1.png" style="width:6.1375in;height:2.58264in" />

Analysis:

**Main results:**

- The 18-24 years category (red) has most of the answers, with 71.4% of the total.

- The 35-44 years category (green) represents 28.6%.

- There are no answers in the other categories (Under 18, 25-34, and 45 or more years).

**Interpretation:**

- Most of the respondents are young adults (18-24 years), which could indicate that the survey was applied in an environment where this group predominates, such as a university or a youth group.

- The second most represented group (35-44 years) suggests the presence of a smaller number of middle-aged people, possibly teachers, professionals or relatives.

- The absence of answers in other categories suggests that the group of respondents is not very diverse in terms of age.

** 2. How often do you attend events (concerts, conferences, festivals, etc.)?**

- Never

- Rarely

- Sometimes

- Frequently

- Always

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image2.png" style="width:6.1375in;height:2.58264in" />

Analysis:

**Main results:**

- "Sometimes" (orange): 57.1% of the respondents attend events occasionally.

- "Rarely" (red): 42.9% attend infrequently.

- There are no answers in the categories "Never", "Frequently" or "Always", which indicates that nobody completely avoids events, but there are no very frequent attendees either.

**Interpretation:**

- Most of the respondents have some interest in events, but they do not attend regularly.

- This could be due to factors such as time availability, costs, interest in specific events or access to these events.

- There are no regular attendees or people passionate about events, which could indicate that events are not an essential part of their lifestyle.

**3. How do you find out about the events you attend?   **

- Social networks

- Friends

- Advertising

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image3.png" style="width:6.1375in;height:2.8125in" />

Analysis:

#### Key results:

- **Social networks (57.1%) and Friends (57.1%)** are the most common sources for discovering events.

- **Sports events (28.6%)** also play a role in spreading information.

- **Advertising (14.3%)** is the least used source for finding out about events.

#### Interpretation:

- Word of mouth and digital channels dominate: **Social networks and recommendations from friends are the main ways of discovering events, which suggests that social media marketing strategies and organic dissemination (personal recommendations) are effective.**

- Low influence of traditional advertising: **Only one person mentioned advertising as a source, which indicates that conventional advertisements may not be so effective for this group.**

- The impact of sports events: Although it is not the main source, some people find out about **other events through them.**

**4. How do you usually buy tickets for events?**

- Through a website

- Through a mobile app

- At the box office or point of sale

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image4.png" style="width:6.1375in;height:2.91806in" />

Analysis:

#### Key results:

- **42.9% buy tickets through a mobile app.**

- **42.9% prefer to buy at the box office or point of sale.**

- **Only 14.3% use a website to acquire their tickets.**

#### Interpretation:

- **Digital and in-person purchases are balanced:** Almost half of the respondents use mobile apps, while the other half prefer to buy physically at the box office.

- **Websites are not a popular option:** Only one person uses this method, which suggests that mobile apps have displaced traditional websites in the purchase of tickets.

- **Preference for practicality:** The use of mobile apps may be due to convenience and speed, while buying at the box office could reflect a preference for security in the purchase or habit.

### Recommendations based on the data:

- **Optimizing mobile apps** for ticket sales can improve the user experience and attract more buyers.

- **Improving the purchase experience on websites** could increase their use, with more intuitive interfaces and attractive promotions.

**5. Would you like to receive notifications from the platform about the event (schedule changes, reminders, etc.)?**

- Yes, I would like to receive notifications

- Only for important changes

- No, I prefer not to receive notifications

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image5.png" style="width:6.1375in;height:2.78333in" />

Analysis:

#### Key results:

- **57.1% (blue) want to receive notifications about the events.**

- **42.9% (red) only want to receive notifications in the case of important changes.**

- **There are no answers for the option "No, I prefer not to receive notifications" (orange), which indicates that all the respondents accept receiving some type of notification.**

#### Interpretation:

- **Notifications are well received:** All the participants are open to receiving information about events, although some prefer that it be only in important cases.

- **Balance between information and relevance:** While more than half want to receive regular notifications, almost half prefer to limit them to key changes.

### Recommendations based on the data:

- **Implement customizable notifications**, allowing users to choose the frequency and type of information they want to receive.

- **Differentiate between standard and urgent notifications**, ensuring that those who only want important notices are not saturated with unnecessary information.

- **Take advantage of the interest in notifications** to improve communication and attendance at the events.

**6. How satisfied are you with the way you currently buy tickets for events?**

- Very satisfied

- Somewhat satisfied

- Neutral

- Somewhat dissatisfied

- Very dissatisfied

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image6.png" style="width:6.1375in;height:2.58264in" />

Analysis:

#### Key results:

1.  **Opportunity for improvement**:

    - 42.9% of the respondents have a neutral opinion, which indicates that the current ticket purchase system does not offer them a remarkable experience.

    - 14.3% are somewhat dissatisfied, which shows that there are aspects that could be optimized in a new platform.

2.  **Demand for a better purchase experience**:

    - Although 42.9% are satisfied, there is no absolute majority that is completely happy with the current system, which opens an opportunity for a website that offers a more efficient and convenient process.

### Recommendations based on the data:

**Ease of use and speed:** The website must have an intuitive interface, with simple navigation and an agile purchase process.

**Differentiation from mobile apps:** As we saw in previous charts that many prefer to buy through apps, the website must offer features that mobile applications do not have, such as exclusive promotions or advanced search filters.

**Multiple payment methods:** Add options such as cards and transfers, which can make the purchase more accessible.

**Optimization for mobile devices:** Although it is a website, it must work perfectly on mobile devices to attract users who prefer apps.

** 7. What information would you like to receive before attending an event?  \***

- Schedules

- Location

- Recommendations

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image7.png" style="width:6.1375in;height:2.64583in" />

### Analysis: 

#### Key results:

- 57.1% (blue) want to receive notifications about the events.

- 42.9% (red) only want to receive notifications in the case of important changes.

- There are no answers for the option "No, I prefer not to receive notifications" (orange), which indicates that all the respondents accept receiving some type of notification.

###  Interpretation:

- **Notifications are well received**: All the participants are open to receiving information about events, although some prefer that it be only in important cases.

- **Balance between information and relevance**: While more than half want to receive regular notifications, almost half prefer to limit them to key changes.

- **Customization on the platform**: Including options for users to choose the type and frequency of notifications will improve the experience.

**8. Have you ever organized an event?**

- Yes

- No

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image8.png" style="width:6.1375in;height:2.58264in" />Analysis:

**Key Results:**

- 28.6% (blue) have organized an event.

- 71.4% (red) have not organized an event.

**Interpretation:**

- **Predominance of attendees over organizers**: Most of the respondents have not organized events, which indicates that the platform must focus mainly on facilitating the experience of the attendees.

- **Potential market for organizers**: Although it is a minority, there is a segment of users who have organized events, which represents an opportunity to include specific tools for them.

**Recommendations:**

- **Section for organizers:** Implement an option within the website where users can create, manage and promote events.

- **Resources and guides:** Offer tutorials or articles with advice on event planning and logistics.

- **Interaction between attendees and organizers:** Create a space where attendees can rate and recommend events, encouraging trust and improving the experience.

**9. What is the biggest challenge you face when planning an event?**

- Design and distribution of the space

- Ticket management

- Coordination with suppliers

- Attendance control

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image9.png" style="width:6.1375in;height:2.5625in" />

Analysis:

**Key Results:**

- **100% (3 answers)** identify **coordination with suppliers** as the main challenge.

- **33.3% (1 answer)** mentioned **attendance control** as a difficulty.

- **0%** of answers for **space design** and **ticket management**, which suggests that these aspects are not problematic for the organizers.

###  Interpretation:

- **Logistics with suppliers is the biggest challenge:** This indicates that organizers need better tools for communication, contracting and management of suppliers.

- **Attendance control is a secondary challenge:** This suggests that more efficient tools could be required to monitor participation in events.

- **Ticket management and space design do not represent great difficulties:** This means that the organizers already have adequate solutions or do not consider them priorities.

###  Recommendations:

1.  **Automation of attendance control:** Integrate QR codes or digital records to facilitate the supervision of attendees.

2.  **Organizer forum or community:** Create a space where organizers can share experiences, recommendations and contacts of reliable suppliers.

**10. Would you like to have an online tool to design the mockup of your event (with places, seats, stage, etc.)?**

- Yes, definitely

- Maybe, if it were easy to use

- No, I do not need it

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image10.png" style="width:6.42708in;height:2.40625in" />

Analysis:

**Key Results:**

- **33.3% (1 answer)** **definitely** want an online tool to design events.

- **66.7% (2 answers)** would consider using it **if it were easy to use**.

- **0%** indicated that they **do not need it**, which shows interest in the feature.

### Interpretation:

- **Moderate interest with conditions:** Although not everyone considers this tool essential, most would use it if it is intuitive and easy to handle.

- **There is no total rejection:** Nobody completely ruled out the idea, which suggests that a well-implemented feature could be useful.

### Recommendations:

1.  **Intuitive interface:** Design a visual and easy-to-use tool, with predesigned options and drag-and-drop.

2.  **Essential features:** Allow the placement of stages, seats and spaces with simple customization.

**11. What features do you consider most important in a tool for creating an event?**

- Ease of dragging and dropping elements

- Predesigned templates according to the type of event

- Options to customize the design

- 2D visualization of the event

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image11.png" style="width:6.1375in;height:2.6875in" />

Analysis:

**Key Results:**

- **66.7% (2 answers)** prioritize the **2D visualization of the event**.

- **33.3% (1 answer)** consider it relevant to have **predesigned templates according to the type of event**.

- **0%** mentioned the need to **drag and drop elements** or **customize the design**, which suggests that these features are not a priority for the respondents.

###  Interpretation:

- **Focus on visual representation:** Most consider the 2D view fundamental, which indicates that visualizing the event in a clear and organized way is a priority.

- **Structure over customization:** Instead of advanced customization options, the respondents prefer to have **predesigned templates** to facilitate planning.

###  Recommendations:

1.  **Implement a 2D viewer:** Integrate an interactive 2D view so that organizers can visualize the distribution of the event.

2.  **Offer practical templates:** Incorporate predefined models according to the type of event (conferences, concerts, fairs, etc.), speeding up the design process.

3.  **Simplicity over advanced features:** It is not a priority to include customization or detailed editing tools, but rather to facilitate a clear and structured visual experience.

**12. What aspect of the experience of attending events would you like to improve?**

- Organization of the event

- Ease of buying tickets

- Access to the venue of the event

- Availability of information before the event

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image12.png" style="width:6.10417in;height:2.4375in" />

Analysis:

### Key Results:

### 66.7% (2 answers) mentioned the availability of information before the event as the most important aspect to improve.

### 33.3% (1 answer) highlighted the importance of improving access to the venue of the event.

### 0% indicated problems with the organization of the event or the ease of buying tickets, which suggests that these aspects are not a main concern.

###  Interpretation:

### Key information before the event: Most of the respondents feel that they lack clear information before attending, which could generate uncertainty or difficulties in planning.

### Accessibility to the event: Although to a lesser extent, access to the event was also identified as an area for improvement, which may imply problems with routes, transport or signage.

###  Recommendations:

### Improve communication prior to the event: Implement a clear and accessible section on the website with key details such as schedules, locations and recommendations.

### Integrate reminders and notifications: Send emails or notifications with relevant information days before the event.

**13. What payment methods do you prefer for buying tickets for events? (You can select several options)**

- Credit/debit card

- Bank transfer

- Cash payment (at the box office)

- Other: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image13.png" style="width:6.1375in;height:3.12083in" />

Analysis:

**Key Results:**

- **66.7% (2 answers)** prefer to pay by **credit/debit card**.

- **33.3% (1 answer)** choose **bank transfer** as the payment method.

- **0%** of the respondents opt for **cash payment at the box office**, which suggests a trend towards digital payments.

### Interpretation:

- **Preference for electronic payments:** Most of the participants prefer digital payment methods, which indicates the need for a platform with secure integration of cards and transfers.

- **Low demand for cash payments:** The absence of answers in favour of cash payment suggests that users prefer to avoid in-person purchases and are looking for 100% online solutions.

###  Recommendations:

1.  **Implement multiple digital payment options:** Ensure that the platform accepts credit/debit cards and bank transfers simply and securely.

2.  **Optimize the purchase process:** Reduce unnecessary steps and ensure that the payment interface is fast and easy to use.

**14. Would you like to use an attendance verification system through QR codes or numeric identification in an application?**

- Yes, it would be very useful

- Maybe, if it is easy to use

- No, I would not like it

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image14.png" style="width:6.1375in;height:2.77986in" />

Analysis:

**Key Results:**

- 100% of the respondents **consider that this system** would be very useful**.**

- **There were no negative answers or doubts about its ease of use.**

###  Interpretation:

- High interest in digitalization: **All of the respondents view favourably the implementation of a system based on** QR codes or numeric identification**, which indicates a clear preference for technological solutions.**

- Potential to optimize event management: **The automation of attendance control could reduce waiting times, eliminate manual processes and improve the user experience.**

###  Recommendations:

1.  Implement a verification system with QR: **Develop a feature that generates unique QR codes for each user, allowing a quick scan at the entrance of the event.**

2.  Offer an alternative with numeric identification: **For those who cannot use QR codes, it would be useful to have a validation option by identification number or unique code.**

3.  Guarantee ease of use: **The application interface must be intuitive, with an agile and uncomplicated verification process.**

**15. How important is it to you that the platform is easy to use on mobile devices?**

- Very important

- Somewhat important

- It is not important

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image15.png" style="width:6.1375in;height:2.58472in" />

Analysis:

**Key Results:**

- **100% of the respondents** consider that ease of use on mobile devices is **very important**.

- There were no answers indicating lower importance.

###  Interpretation:

- **Priority on mobile accessibility:** All of the respondents highlight the need for a platform optimized for mobile devices.

- **Key user experience:** An adaptable and simple interface will guarantee a better interaction with the platform, avoiding navigation and functionality problems.

###  Recommendations:

1.  **Responsive design:** Ensure that the platform adapts perfectly to different screen sizes and resolutions.

2.  **Intuitive interface:** Prioritize fluid navigation with simple menus, accessible buttons and an attractive visual design.

3.  **Performance optimization:** Reduce loading times and avoid heavy elements that can slow down the experience on mobile devices.

4.  **Testing on multiple devices:** Verify the operation of the platform on different operating systems and screen sizes.

**16. Do you have any additional suggestions to improve our platform or the experience at events?**

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/media/image16.png" style="width:6.1375in;height:2.38542in" />

Analysis:

**Key Results:**

- All the answers indicate **"No", "Nothing" or "None"**, which suggests that the respondents have no additional recommendations at this time.

**Interpretation:**

- **General satisfaction:** The lack of suggestions could indicate that the participants are satisfied with the current proposal

- 


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): no text<br>![Header of the original](../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Encuesta_TuEvento/header_footer/image17.png)

---

<a id="doc-te-0014"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Recoleccion_de_datos/interview_Your_event.md
id: TE-0014
title: "interview-Your event"
lang: en
source: 01_Especificacion_Requisitos/Recoleccion de datos/interview-Your event.docx
source_sha256: efe72d294bc8bd8d2ae371c4f120a7f81113d67d8811583c3deed0a69415a3a5
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  []
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0014
es_sha256: 5f48844503ef4311cbba64cb10b13f4cecb6ae51d5e7508d8fc28780762f793b
-->

# Data collection — interview

<img src="../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/interview_Your_event/media/image1.jpeg" style="width:1.24578in;height:1.0047in" />

**Interview Title:** *Survey on the Event Management platform.*

**Date:** 24/02/2025\
**Interviewer:** Cristofer David Lozano\
**Interviewee:** Edwin Mauricio\
**Position or profile of the interviewee:** Event organizer

**Type of interview:** Semi-structured

### Good morning/afternoon \[name\], it is a pleasure to have you here today. I hope you are well. Before we begin, I want to thank you for your time and for sharing your experience with us. The objective of this interview is to learn your opinion about the event management platform, evaluating its usability, features and efficiency in planning and organization. We want to identify possible areas for improvement to optimize your experience. Your perspective is very valuable to us. How are you feeling today?"

### **Objective of the interview:**

To collect and analyse the opinion of event organizers about the event management platform, in order to evaluate its usability, features and efficiency in planning and organization. In addition, to identify areas for improvement that make it possible to optimize the user experience and strengthen the performance of the platform.

It should be mentioned that the interview will be recorded in order to better analyse the answers and ensure accuracy in the collection of information.

### **Interview questions**

**1. What type of events do you organize most often?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**2. Do you currently use any platform to manage events?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**3. What are the main challenges you face when organizing an event?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**4. Have you used other event management platforms? If so, what did you like and not like about them?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**5. What is the average size of the events you organize? (Example: fewer than 50 attendees, between 50-200, more than 500, etc.)**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**6. What features do you consider essential in an event management platform?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**7. How useful would it be to have a feature for automated sending of reminders and notifications?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**8. Would you like to be able to customize the appearance and image of the events within the platform?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**9. How do you currently handle attendee registration and what features would improve this process?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**10.** **Do you require the platform to generate QR codes or digital tickets for access to the events?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**11. Do you prefer to use the platform on a computer, a mobile device or both?**\
Answer: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Thank you very much for your time and for sharing your experience with us, \[name\]. Your opinion is very valuable and will help us improve the platform to offer a better experience to event organizers. If in the future you have any additional comments, do not hesitate to let us know. Have an excellent day!"

### **Additional remarks:**

*(Space to note additional comments, gestures, tone of the interviewee or relevant information not included in the answers.)*

### **Conclusion:**

*(Summary of the key points of the interview and possible reflections of the interviewer.)*

---

<a id="doc-te-0013"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Entrevista_TuEvento.md
id: TE-0013
title: "Análisis Entrevista TuEvento"
lang: en
source: 01_Especificacion_Requisitos/Recoleccion de datos/Análisis Entrevista TuEvento.docx
source_sha256: 15b322658407100df2452cf2d25659054af05f74f78d23e70ac1d55296f72cc2
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the name of the training centre («Centro de la Industria la empresa y los Servicios») is kept in Spanish because it is a proper name."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0013
es_sha256: f4fc8b4f108a2e40dce8e0052f229577ea3436eee6931e531788172949e21231
-->

# Interview analysis

**Interview Data Processing and Analysis**

**Training Project**

**Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development)**

**“Tu Evento”**

Team members:

**Cristofer David Lozano**

**Jhampier Santos Ortiz**

**Centro de la Industria la empresa y los Servicios**

**Neiva, Huila**

**Year 2025**

**Interview Data Processing and Analysis**

**Interview Title: Event Management Platform\
Date: 24/02/2025\
Interviewer: Cristofer David Lozano\
Interviewee: Edwin Mauricio\
Position of the interviewee: Event organizer\
Type of interview: Semi-structured**

**Questions, Answers and Analysis**

**1. What type of events do you organize most often?**

- **Answer: Specialized in hiking, nature and cultural tourism.**

- **Analysis: Their main focus is on outdoor activities, which indicates the need for the platform to adapt to tourist and recreational events.**

**2. Do you currently use any platform to manage events?**

- **Answer: Uses social networks such as Facebook and Instagram for announcements and WhatsApp for coordination.**

- **Analysis: They currently use common and easily accessible tools, but lack a centralized platform that facilitates registration and the complete management of the events.**

**3. What are the main challenges you face when organizing an event?**

- **Answer: Keeping to schedules and the attendance of the participants.**

- **Analysis: The lack of punctuality affects logistics. A platform with reminders and notifications could help reduce this problem.**

**4. Have you used other event management platforms? What positive or negative aspects did you find in them?**

- **Answer: Only social networks, because they are viral and accessible.**

- **Analysis: They have had no experience with specialized platforms, possibly due to their cost or lack of knowledge about them. This highlights the need for an economical and easy-to-use solution.**

**5. What is the average size of the events you organize?**

- **Answer: Between 5 and 63 people.**

- **Analysis: The platform must be flexible, so that it can adapt to both small and medium-sized groups.**

**6. What features do you consider essential in an event management platform?**

- **Answer: Knowing the interests and physical level of the participants.**

- **Analysis: It is important that the platform allows collecting personalized information to better plan the attendees' experience.**

**7. How useful would it be to have automatic reminders and notifications?**

- **Answer: Very useful, it would help reduce disorganization.**

- **Analysis: Automatic reminders would improve punctuality and confirmed attendance at the events.**

**8. Would you like to customize the appearance and image of the events on the platform?**

- **Answer: Yes, especially to reflect the natural aspect of tourism.**

- **Analysis: The option to customize with colours, icons and visual styles would make it possible to highlight the identity of each event and make it more attractive.**

**9. How do you currently handle attendee registration and what improvements do you consider necessary?**

- **Answer: By hand or through WhatsApp.**

- **Analysis: A digital system would facilitate the registration and confirmation of the participants, avoiding errors and improving organization.**

**10. Do you need the platform to generate QR codes or digital tickets for access to the events?**

- **Answer: It is not necessary for hiking, but it is useful for events in closed venues.**

- **Analysis: The platform should offer this feature as an additional option, depending on the type of event.**

**11. Do you prefer to use the platform on a computer, a mobile device or both?**

- **Answer: Web for organizers, mobile for users.**

- **Analysis: Compatibility with both devices is required, differentiating the features of the organizers and of the attendees for greater convenience.**

**Conclusion of the Interview**

**The interviewee reflects the need for a flexible, economical and easy-to-use platform that makes it possible to manage both small and medium-sized events. The most valued features are:**

- **Automatic notifications and reminders,**

- **Customization options,**

- **Digital management of attendees,**

- **Compatibility on mobile devices and the web.**

**These characteristics would help improve organization, increase punctuality and offer a better experience for both organizers and participants.**


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): no text<br>![Header of the original](../_assets/01_Especificacion_Requisitos/Recoleccion_de_datos/Analisis_Entrevista_TuEvento/header_footer/image1.png)

---

<a id="doc-te-0019"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Vigilancia_tecnologica/vigilancia_tecnologica.md
id: TE-0019
title: "vigilancia tecnologica"
lang: en
source: 01_Especificacion_Requisitos/Vigilancia tecnologica/vigilancia tecnologica.docx
source_sha256: 02659eab0cb56be24e5daa1f2bfa17881ed563745c38045020a51fedc2f9ca3a
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the source link points to a page in Spanish and is kept unchanged."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0019
es_sha256: 16d2c5b9d27774ac79804b950794937e3747e9f09a02639ac2165af41500867d
-->

# Technology watch

**Technology Watch**

Lozano Contreras Cristofer David

Jhampier Santos Santos Ortiz

Análisis y Desarrollo de Softwares (Software Analysis and Development)

\(3145556\)

Servicio Nacional de Aprendizaje (National Learning Service)

Instructor:

Jhon Corredor

Karol correa

Carlos Julio Cadena

February 26, 2025

# What is Technology Watch?

**Definition**

Technology watch is the systematic process of collecting and analysing information about the technological advances that currently exist, in order to know what strategy could take advantage of those innovation opportunities, which also helps to anticipate changes that the environment may generate.

This data collection instrument is vital for our development of the application, because we will be able to analyse the movements or strategies of what exists nowadays in web browsers, allowing us to identify the strengths and weaknesses in the market.

**Importance of Technology Watch**

The importance of this type of tool lies in the fact that most of the best-known applications, such as Facebook, Instagram, WhatsApp, etc., are constantly adapting to the changes that could arise in the future or, even better, anticipating them; this allows them to keep innovating continuously and to consolidate their dominant position in their respective sectors.

# Objectives Of The Application

The “Tu evento” application must be innovative, since it would be in charge of simplifying, optimizing and customizing events, while offering a satisfactory experience for both attendees and organizers.

Through this information collection tool, the application could be different from those that currently exist in today's market, in order to develop, analyse and detect the opportunities that may arise and at the same time have a significant impact through the use of the artifact.

As an expected result, the application will not just be one more application on the market, but a useful tool that would transform the way events are organized, allowing organizers to reduce costs and time; it would also allow new technologies and features to be incorporated.

**Importance**

In the digital era, efficient event management has become a fundamental pillar for companies and organizers, who seek to stand out in the competitive market, where event reservation applications are implemented that not only optimize internal processes, but also enhance the user experience.

The adoption of technologies in this kind of field shows that there has been notable growth; according to a recent study, 72% of organizations consider that event technologies play a crucial role in current planning and management.

It should also be stressed that 52% of attendees often use mobile devices; according to a recent Eventbrite survey, this event trend is expected to continue as more people get used to using mobile devices. These applications allow users to search for events, see event schedules and make reservations; this enables growth while becoming a trend in the events industry. If a given company or organizer did not apply this type of technology, it could mean that they are losing time and money. Recent research by Bizzabo shows that 72% of event organizations believe that applications of this type play a crucial role in event planning and management today. 

**Source of information:**

[**https://time.ly/es/blog/nuevas-tendencias-en-la-industria-de-eventos-que-debes-seguir/**](https://time.ly/es/blog/nuevas-tendencias-en-la-industria-de-eventos-que-debes-seguir/)

**Result of the Technology Watch**

As mentioned above, technology watch is a strategic tool that will be implemented in the development of the application, with the aim of innovating and remaining competitive in a dynamic and constantly evolving market. To achieve this, it will be based on a systematic process of collecting and analysing information, using various reliable sources that allow us to identify trends, opportunities and challenges in the event organization sector.

Next, it will be detailed how this process will be carried out, analysing each relevant aspect that is found, through a table comparing the platforms already analysed with “tu evento”.

**Source of the analysed applications:**

**Ticketmaster**:

*https://[www](https://www.ticketmaster.com/).ticketmaster.com/*

**SeatGeek**:

*<https://seatgeek.com/>*

**Conclusion**

After analysing the Ticketmaster and SeatGeek platforms, strengths and areas of opportunity were identified in their features, but they have limitations in key aspects such as integration with social networks, event customization and the possibility of receiving feedback from attendees after the event.

In contrast, our application will stand out by providing a more complete and adaptable experience for event users and organizers. Compatibility with Smart TV will allow greater accessibility and viewing of events on large screens. In addition, 100% event customization will guarantee that organizers can modify every aspect of their event according to their needs. Integration with social networks will facilitate dissemination and promotion, allowing users to share events and experiences quickly. Finally, the incorporation of a post-event feedback system will encourage interaction between attendees and organizers, improving the quality of future events.

With these competitive advantages, our application will offer a more complete solution oriented to the current market trends, positioning itself as an innovative alternative to the existing options


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «0»

---

<a id="doc-te-0018"></a>

<!--
ruta_anterior: en/01_Especificacion_Requisitos/Vigilancia_tecnologica/cuadro_comparativo_Tu_evento.md
id: TE-0018
title: "cuadro comparativo-Tu evento"
lang: en
source: 01_Especificacion_Requisitos/Vigilancia tecnologica/cuadro comparativo-Tu evento.xlsx
source_sha256: 491b5045ce15d9e8e8c4e4005a8b48526a68f0645b8b6aa2a63cb73b0c214b93
conversion: "openpyxl 3.1.5 (data_only + formulas); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The 2 images embedded in row 3 (H3:J3 and L3:N3) are extracted to _assets and linked below the table; in the original they overlap the cells."
  - "Visual formatting (colours, borders, widths, fonts and conditional formatting styles) is not kept."
  - "Merged cells are listed but not reproduced as a single cell."
  - "The formula values are the ones cached by Excel; they were not recalculated."
  - "Translation: the sheet name (Hoja1) and the names of the embedded images («Imagen 3», «Imagen 5») are kept because they are identifiers of the original workbook."
status: borrador
reviewed_by: ""
translation_of: es/02_Especificacion_Requisitos.md#doc-te-0018
es_sha256: 2376ebf0be95f24d02236584e4cac5bd6c30ff2f721c116a10252485cb9be46e
-->

# comparison table-Tu evento

> Conversion of `01_Especificacion_Requisitos/Vigilancia tecnologica/cuadro comparativo-Tu evento.xlsx`: 1 sheet (Hoja1), 0 formulas. The columns are named with the Excel letter and each row with its original number.

## Sheet: Hoja1

Used range: `A3:N19` · 19 rows × 14 columns · merged cells: 36

| Row | A | B | C | D | E | F | G | H | I | J | K | L | M | N |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 3 | Features |  | Tu evento |  |  |  |    ticketmaster |  |  |  |    SEATGEEK |  |  |  |
| 4 | Mobile compatibility |  | Meets for both mobile devices (iOS and  Android)  |  |  |  | Meets for both mobile devices (iOS and  Android)  |  |  |  | Meets for both mobile devices (iOS and  Android)  |  |  |  |
| 6 | TV compatibility |  | Meets  |  |  |  | Not available |  |  |  | Not available |  |  |  |
| 8 | Ease of use |  | Meets  |  |  |  | Meets  |  |  |  | Meets  |  |  |  |
| 10 | 100% event customization |  | Meets  |  |  |  | Not available |  |  |  | Not available |  |  |  |
| 12 | Social network integration |  | Meets  |  |  |  | Not available |  |  |  | Not available |  |  |  |
| 14 | Attendee registration and management |  | Meets  |  |  |  | Meets  |  |  |  | Meets  |  |  |  |
| 16 | Reminder automation |  | Meets  |  |  |  | Meets  |  |  |  | Meets  |  |  |  |
| 18 |  Post-event user feedback |  | Meets  |  |  |  | Not available |  |  |  | Not available |  |  |  |

**Merged cells** (the value appears only in the top-left cell): `A10:B11`, `A12:B13`, `A14:B15`, `A16:B17`, `A18:B19`, `A3:B3`, `A4:B5`, `A6:B7`, `A8:B9`, `C10:F11`, `C12:F13`, `C14:F15`, `C16:F17`, `C18:F19`, `C3:F3`, `C4:F5`, `C6:F7`, `C8:F9`, `G10:J11`, `G12:J13`, `G14:J15`, `G16:J17`, `G18:J19`, `G3:J3`, `G4:J5`, `G6:J7`, `G8:J9`, `K10:N11`, `K12:N13`, `K14:N15`, `K16:N17`, `K18:N19`, `K3:N3`, `K4:N5`, `K6:N7`, `K8:N9`

**Images embedded in the sheet** (extracted from `xl/media/`; position according to `xl/drawings/drawing1.xml`):

- «Imagen 3», anchored from `H3` to `J3`: ![Image 3 of the original (row 3, columns H–J)](../_assets/01_Especificacion_Requisitos/Vigilancia_tecnologica/cuadro_comparativo_Tu_evento/image1.jpeg)
- «Imagen 5», anchored from `L3` to `N3`: ![Image 5 of the original (row 3, columns L–N)](../_assets/01_Especificacion_Requisitos/Vigilancia_tecnologica/cuadro_comparativo_Tu_evento/image2.jpg)
