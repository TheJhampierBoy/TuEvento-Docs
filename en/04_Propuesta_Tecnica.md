---
title: "Technical proposal"
lang: en
documents: [TE-0080, TE-0079]
status: borrador
---
# Technical proposal — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Technical proposal](#doc-te-0080)
2. [Technical sheet](#doc-te-0079)

---

<a id="doc-te-0080"></a>

<!--
ruta_anterior: en/03_Propuesta_Tecnica/Propuesta_Tecnica_Tu_evento.md
id: TE-0080
title: "Propuesta Técnica-Tu evento"
lang: en
source: 03_Propuesta_Tecnica/Propuesta Técnica-Tu evento.docx
source_sha256: f3cf92828ddcc5f74a07c5a99edd437c583315f5631d1f1b3e73a03eebceca1c
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
status: borrador
reviewed_by: ""
translation_of: es/04_Propuesta_Tecnica.md#doc-te-0080
es_sha256: 6628ac575713de5c698f960866987e762cdfdd10702f31c0f8d11ef41491ae2b
-->

# Technical proposal

**CapySoft**

**Technical proposal**

**Tu evento**

**Cristofer David Lozano Contreras**

**Jhampier Santos Ortiz**

**(3145556)**

**Servicio Nacional De Aprendizaje (National Learning Service)**

**March 5 2025**

1.  **Executive Summary**

This document describes the technical proposal for the development of the “Tu Evento” system, an innovative platform aimed at the organization, management and customization of events. The system seeks to solve the current limitations of traditional ticket sales and space management platforms, which offer little flexibility for events with non-standard configurations

“Tu Evento” will allow organizers to design fully customized seat maps and attendees to interact with these designs in a visual and intuitive way, selecting their locations easily. In this way, the system improves the user experience, optimizes event management and offers a comprehensive solution adaptable to different types of venues.

2.  **Project objectives**

**2.1 Specific Objectives**

- Analyse the needs of organizers and attendees in event management.

- Design the system architecture (web, mobile and administrative module).

- Develop an intuitive graphical interface for creating customized seat maps.

- Implement an interactive visualization system for selecting locations.

- Create an administration module for managing events, users and spaces.

- Optimize the user experience with usability, accessibility and responsive design.

- Run validation tests and system adjustments

3.  **Project scope**

The “Tu Evento” system will offer a web and mobile platform that will allow:

Organizers to:

- Create events

- Design customized maps of spaces and seats.

- Manage users and event settings.

> Attendees to:

- View the seat maps.

- Select their location interactively.

- Consult event information.

> Administrators to:

- Supervise the operation of the system.

- Manage users, events and general settings

> **Platform scope.** Tu Evento is delivered as a web application (React) and a mobile application (React Native with Expo), both connected to the same backend. No desktop application is developed: the web application runs in desktop browsers and serves users who work from a computer, so a separate desktop application would duplicate features without adding to the project scope.

4.  **Technologies to be used**

> **4.1 Backend**

- Programming language: Java

- Framework: Spring Boot

- Database: PostgreSQL

**4.2 Frontend**

- Web application: React.js

- Mobile application: React Native

**4.3 Libraries and Tools**\
This section describes the main libraries, frameworks, APIs and tools that will be used in the development of the system, as well as their purpose within the project architecture.

- **Spring Boot:** Base framework for building the backend.

- **Spring Security:** Control of user authentication and authorization.

- **Hibernate / JPA:** Data persistence.

- **PostgreSQL:** Database management system.

- **Sandbox payment gateway:** Testing of the electronic payment flow, connected to the backend and without real charges.

- **Swagger:** Interactive API documentation.

5.  **System Architecture**

> The system will implement a client-server architecture, where the web and mobile applications will communicate with a central server. The backend will process the information on events, users and spaces, while the frontend will visually display the interactive maps. The architecture is designed to be modular, scalable and adaptable to different types of events.

6.  **Project Benefits**

- Greater flexibility in event customization.

- Visual and intuitive experience for attendees.

- Optimization in the management of spaces and users.

- Platform adaptable to different types of venues and events.

- Improvement in organization and control by the administrators.

7.  **Conclusion**

> “Tu Evento” represents an innovative solution compared with traditional platforms such as Ticketmaster or Eventbrite, since it offers a high level of customization and an interactive experience for organizers and attendees. Its implementation will make it possible to transform the way events are designed and managed, providing a modern, flexible and efficient tool


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «12»<br>![Header of the original](../_assets/03_Propuesta_Tecnica/Propuesta_Tecnica_Tu_evento/header_footer/image7.jpeg)

---

<a id="doc-te-0079"></a>

<!--
ruta_anterior: en/03_Propuesta_Tecnica/Ficha_Tecnica.md
id: TE-0079
title: "Ficha Tecnica"
lang: en
source: 03_Propuesta_Tecnica/Ficha Tecnica.xlsx
source_sha256: 2c3561b6fb2112367daae462fe20047e44bc7a00934757d2fb1ba5d407e7e5d5
conversion: "openpyxl 3.1.5 (data_only + formulas); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Visual formatting (colours, borders, widths, fonts and conditional formatting styles) is not kept."
  - "Merged cells are listed but not reproduced as a single cell."
  - "The formula values are the ones cached by Excel; they were not recalculated."
  - "Translation: the sheet names (R.Software, R.Hadware) are kept because they are identifiers of the original workbook."
  - "Translation: numbers keep the format of the original (for example, «6,56» uses a decimal comma and «1,366 x 768» a thousands comma)."
status: borrador
reviewed_by: ""
translation_of: es/04_Propuesta_Tecnica.md#doc-te-0079
es_sha256: c86bc44d3dd5d8e41ec8b060777fa4389c5b6a1afa7c84ab5e8bcc42a46341e8
-->

# Technical Data Sheet

> Conversion of `03_Propuesta_Tecnica/Ficha Tecnica.xlsx`: 2 sheets (R.Software, R.Hadware), 0 formulas. The columns are named with the Excel letter and each row with its original number.

## Sheet: R.Software

Used range: `A1:H17` · 17 rows × 8 columns · merged cells: 17

| Row | A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|---|
| 1 | Software requirements |  |  |  |  |  |  |  |
| 2 | VS Code or IDE | Version | Operating System | License | Minimum Requirements |  |  |  |
| 3 | Visual Studio Code | 1.x (regular updates) | Windows | Free license | Windows: Windows 7, 8, 10, 11 (64 bits) |  |  |  |
| 4 | Visual Studio | 2022 (latest stable version) | Windows | Community (free) | Windows 10 version 1909 or later (64 bits), 8 GB of RAM recommended |  |  |  |
| 5 | Database | Version | Operating System | License | Minimum Requirements |  |  |  |
| 6 | PostgreSQL | 15.x (latest stable version) | Windows | Open license | Windows 10 (64-bit), 2 GB of RAM, 200 MB of free disk space. |  |  |  |
| 7 | Programming Languages | Version | Operating System | License | Minimum Requirements |  |  |  |
| 8 | JavaScript | ES2023 (latest version) | Cross-platform | Free (Open Source) | Depends on the browser, but in general: 1 GHz processor, 2 GB of RAM, free disk space  |  |  |  |
| 9 | Java  | 11.0 (latest version) |   Windows | MIT License | Windows: Windows 10 or later, 2 GB of RAM, 2 GB of free disk space. |  |  |  |
| 10 | Frameworks | Version | Operating System | License | Minimum Requirements |  |  |  |
| 11 | React Native | Latest stable version (0.70.x or later) | Windows | MIT License | Windows 10 or later, 8 GB of RAM (recommended minimum), 10 GB of free disk space. |  |  |  |
| 12 | Fabric.js | Latest version | Cross-platform | MIT License | It has no specific requirements, only a modern browser |  |  |  |
| 13 |  Spring Boot | 3.2.x (latest stable version) | Cross-platform  | Apache License 2.0 | JDK 17 or later, 2 GB of RAM, 2 GB of free disk space, internet connection to manage dependencies with Maven or Gradle. |  |  |  |
| 14 | API | Version | Operating System | License | Minimum Requirements |  |  |  |
| 15 | Google Sign-In | Latest stable version | Cross-platform | Free (Google Cloud Platform) | Google account, register the app in Google Cloud Console, configure OAuth 2.0. |  |  |  |
| 16 | Facebook Login | Latest stable version | Cross-platform | Free (Facebook Developer Portal) | Facebook account, create an application in Facebook Developer Portal, configure OAuth. |  |  |  |
| 17 | Hosting /Domain | Version | Operating System | License | Minimum Requirements |  |  |  |

**Merged cells** (the value appears only in the top-left cell): `A1:H1`, `E10:H10`, `E11:G11`, `E12:G12`, `E13:G13`, `E14:H14`, `E15:G15`, `E16:G16`, `E17:H17`, `E2:H2`, `E3:H3`, `E4:H4`, `E5:H5`, `E6:H6`, `E7:H7`, `E8:H8`, `E9:H9`


## Sheet: R.Hadware

Used range: `A1:G63` · 63 rows × 7 columns · merged cells: 26

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | HARDWARE REQUIREMENTS |  |  |  |  |  |  |
| 2 | QUANTITY | COMPONENT | SPECIFICATIONS |  |  |  |  |
| 3 | 4 | Laptop or desktop computer | Brand | Acer | Acer | Corporativo HP | Corporativo HP |
| 4 |  |  | Model | Aspire 515-52 | Nitro AN515-55 | Elitedesk 800 G1 | Elitedesk 600 G2 |
| 5 |  |  | Colour | Black | Black | Black | Black |
| 6 |  |  | Performance components |  |  |  |  |
| 7 |  |  | Graphics Card | Integrated | GeForce GTX 1650 | Integrated | Integrated |
| 8 |  |  | Processor  | Intel core | Intel core | Intel core | Intel core |
| 9 |  |  | Model | i5 | i5 | i5 | i5 |
| 10 |  |  | RAM Memory |  |  |  |  |
| 11 |  |  | Capacity | 8GB | 8GB | 12GB | 8GB |
| 12 |  |  | Storage |  |  |  |  |
| 13 |  |  | Capacity | 475GB | 475GB | 475GB | 1TB |
| 14 |  |  | Screen and operating system |  |  |  |  |
| 15 |  |  | Size | 15.6" | 15.8" | 15.6" | 15.6" |
| 16 |  |  | Resolution | 1366 x 768 60,06Hz | 1920 x 1080, 144Hz | 1921 x 1080, 60,06Hz | 1922 x 1080, 60,06Hz |
| 17 |  |  | Touch input | No | No | No | No |
| 18 |  |  | Operating System | Windows 10 | Windows 11 | Windows 10 | Windows 10 |
| 19 | 3 | Android | Brand | Honor | Xiaomi | Xiaomi |  |
| 20 |  |  | Model | Honor x6a plus | RedmI Note 10 | Redmi Note 11 |  |
| 21 |  |  | Serial number | WDY-LX3 | 21061119AL | 2201117TL |  |
| 22 |  |  | Performance components |  |  |  |  |
| 23 |  |  | Processor  | mediatek | Qualcomm®  | Qualcomm®  |  |
| 24 |  |  | Model | Helio  |  Snapdragon™ | Snapdragon™ |  |
| 25 |  |  | Series | G36 | 678 | 680 |  |
| 26 |  |  | RAM Memory |  |  |  |  |
| 27 |  |  | Capacity | 6GB + HONOR RAM Turbo | 4GB | 6GB |  |
| 28 |  |  | Storage |  |  |  |  |
| 29 |  |  | Capacity | 256GB | 128GB | 128GB |  |
| 30 |  |  | Screen |  |  |  |  |
| 31 |  |  | Size | 6,56-inch LCD | 6,5″ inches | 6,43" |  |
| 32 |  |  | Resolution | 1612 x 720  | 1080 X 2040  | 1080 x 2400  |  |
| 33 |  |  | Android version | 14 | 13 | 14 |  |
| 34 | 1 | iOS | Brand | iphone  |  |  |  |
| 35 |  |  | Model | iphone 11  |  |  |  |
| 36 |  |  | Serial number | FFWLLRTRN73D |  |  |  |
| 37 |  |  | Performance components |  |  |  |  |
| 38 |  |  | Processor  |  Bionic |  |  |  |
| 39 |  |  | Model | A |  |  |  |
| 40 |  |  | Series | 13 |  |  |  |
| 41 |  |  | RAM Memory |  |  |  |  |
| 42 |  |  | Capacity | 4GB LPDDR4X |  |  |  |
| 43 |  |  | Storage |  |  |  |  |
| 44 |  |  | Capacity | 128GB |  |  |  |
| 45 |  |  | Screen |  |  |  |  |
| 46 |  |  | Size | 6.06" inches |  |  |  |
| 47 |  |  | Resolution | 1792 x 828 |  |  |  |
| 48 |  |  | iOS version | 18 |  |  |  |
| 49 | 3 | tv | Brand | LG |  |  |  |
| 50 |  |  | Model | 32 |  |  |  |
| 51 |  |  | Serial number | FFWLLRTRN73D |  |  |  |
| 52 |  |  | Performance components |  |  |  |  |
| 53 |  |  | Processor  |  Bionic |  |  |  |
| 54 |  |  | Model | A |  |  |  |
| 55 |  |  | Series | 14 |  |  |  |
| 56 |  |  | RAM Memory |  |  |  |  |
| 57 |  |  | Capacity | 500 MB |  |  |  |
| 58 |  |  | Storage |  |  |  |  |
| 59 |  |  | Capacity | 200GB |  |  |  |
| 60 |  |  | Screen |  |  |  |  |
| 61 |  |  | Size | 32 Inches |  |  |  |
| 62 |  |  | Resolution | 1,366 x 768 |  |  |  |
| 63 |  |  | webOs version | 22 |  |  |  |

**Merged cells** (the value appears only in the top-left cell): `A19:A33`, `A1:G1`, `A34:A48`, `A3:A18`, `A49:A63`, `B19:B33`, `B34:B48`, `B3:B18`, `B49:B63`, `C10:G10`, `C12:G12`, `C14:G14`, `C22:F22`, `C26:F26`, `C28:F28`, `C2:G2`, `C30:F30`, `C37:D37`, `C41:D41`, `C43:D43`, `C45:D45`, `C52:D52`, `C56:D56`, `C58:D58`, `C60:D60`, `C6:G6`
