---
title: "Project article"
lang: en
documents: [TE-0002]
status: borrador
---
# Project article — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Project article](#doc-te-0002)

---

<a id="doc-te-0002"></a>

<!--
ruta_anterior: en/00_Informes/Articulo_TuEvento.md
id: TE-0002
title: "Articulo_TuEvento"
lang: en
source: 00_Informes/Articulo_TuEvento.pdf
source_sha256: c1150ee006a6ef9e0e5a0c85d4669a6da163cc54a200d2c8fe54ba32739eb8a3
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–7: «{n}»."
  - "PDF generated without LaTeX: hyphens at the end of a line are real hyphens and are kept when joining lines (they are not syllabic line-break hyphens)."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
  - "Translation: numbers keep the Spanish format (thousands separator «.»): 71.000 is seventy-one thousand."
  - "Translation: the bibliographic references are kept as in the original (titles of cited works are not translated)."
status: borrador
reviewed_by: ""
translation_of: es/13_Articulo_Proyecto.md#doc-te-0002
es_sha256: ed122b421f6c8749f60debd531929cb0c4077cf8ed21fde68ae0dde7b8cf7c84
-->

# Project article

## TuEvento: a web and mobile platform for event management and ticket sales with real-time seat selection

Jhampier Santos Ortiz and Cristofer David Lozano Contreras

Servicio Nacional de Aprendizaje (National Learning Service) (SENA)

Análisis y Desarrollo de Software (ADSO; Software Analysis and Development), ficha (training group) 3145556

Instructor: Karol Daniela Correa

October 2026

## TuEvento: a web and mobile platform for event management and ticket sales with real-time seat selection

## Abstract

TuEvento is a web and mobile platform that seeks to make event organization and ticket sales easier through tools for managing reservations and selecting seats in real time. The project was developed from the identification of the needs of organizers and attendees, using Scrum as the work methodology. The solution integrates technologies for managing events, users, payments and notifications. This article presents the development process, the main features of the system, the results obtained and some aspects that are still pending.

Keywords: event management, ticket sales, seat selection, Scrum, software architecture.

## TuEvento: a web and mobile platform for event management and ticket sales with real-time seat selection

## Introduction

Organizing events requires managing different processes, such as attendee registration, ticket sales and access control. When these activities are carried out manually or with separate tools, difficulties can arise in managing reservations and keeping information up to date.

TuEvento arises from this need: a platform that brings together tools so that organizers can manage their events and attendees can browse options, select seats and manage their tickets. The system also has administrative functions to control users, roles and organizers.

The goal of the project is to centralize these processes in a solution that can be used from the web and from mobile devices, making event management and the attendee experience easier.

## Methodology and development

To define the features, an interview was conducted with an event organizer and a survey with attendees. Existing platforms were also analysed to identify features that could serve as a reference. The results helped establish the main needs of the system although, because of the small sample sizes, they were used as guidance for the design and not as generalizable statistical evidence.

Development was organized with Scrum, with eight sprints between March and October 2026. During this period the work covered requirements documentation, interface design, backend construction, application development and system testing. This approach made it possible to divide the work into stages and to review progress during development (Schwaber & Sutherland, 2020).

As for the technologies, the backend uses Spring Boot and PostgreSQL, while the web application is developed with React and the mobile one with React Native. Communication between the components uses REST APIs and WebSocket, the latter to update information in real time, such as seat availability.

The current architecture is a modular monolith organized with Domain-Driven Design (DDD) and hexagonal architecture. This organization seeks to separate the business logic from the technical details and to make the system easier to maintain (Cockburn, 2005; Evans, 2003). As part of the evolution envisaged for the project, a possible migration to microservices is being considered, but this transition has not yet been carried out.

The main features include the creation and management of events, reservations, seat selection, notifications, user profiles and the digital wallet. Authentication and access control mechanisms are also implemented according to the defined roles.

## Results and limitations

As a result of the development, TuEvento has components for managing events, users, reservations and tickets, as well as web and mobile interfaces. According to the repository metrics, the project exceeds 71.000 lines of code and has 114 unit test methods in the backend.

However, there are still functions to be completed. The payment gateway is a sandbox for testing the payment flow and a real provider has not yet been integrated. In addition, the mobile application does not have the screen for scanning QR codes during attendee entry. Automated tests for the web and mobile applications are also pending, along with some administrative functions and security-related validations.

These aspects must be taken into account to keep improving the system. The next steps include integrating a real payment gateway, completing ticket validation, expanding the tests and evaluating the evolution of the architecture according to the future needs of the project.

## Conclusions

The development of TuEvento made it possible to build a platform that brings together different processes related to event organization and ticket sales. The application of Scrum and the use of technologies such as Spring Boot, PostgreSQL, React and React Native made it possible to develop the main features for the web and mobile platforms.

Although the system shows important progress, it still needs to complete some functions and strengthen its tests before it can be considered ready for a production environment. In the future, the integration of real payments, the improvement of validation mechanisms and the possible migration to microservices represent opportunities to continue its evolution.

# References

Cockburn, A. (2005). Hexagonal architecture.

https://alistair.cockburn.us/hexagonal-architecture/

Evans, E. (2003). Domain-driven design: Tackling complexity in the heart

of software. Addison-Wesley.

Schwaber, K., & Sutherland, J. (2020). The Scrum Guide.

https://scrumguides.org/

SeatGeek. (n.d.). SeatGeek. https://seatgeek.com/

Ticketmaster. (n.d.). Ticketmaster. https://www.ticketmaster.com/ Time.ly. (n.d.). Nuevas tendencias en la industria de eventos que debes

seguir. https://time.ly/es/blog/nuevas-tendencias-en-la-industria-de-eventos-que-debes-seguir/
