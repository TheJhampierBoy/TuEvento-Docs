---
title: "Quality and improvements"
lang: en
documents: [TE-0157, TE-0156]
status: borrador
---
# Quality and improvements — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Software quality](#doc-te-0157)
2. [Corrective, preventive and improvement actions](#doc-te-0156)

---

<a id="doc-te-0157"></a>

<!--
ruta_anterior: en/08_Mejora_Software/Calidad_de_Software.md
id: TE-0157
title: "Calidad de Software"
lang: en
source: 08_Mejora_Software/Calidad de Software.docx
source_sha256: 6f4ac1a414fcad4453913c3fb834f79a859197cf7d5e06dea9fa4d22078a5bf7
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
status: borrador
reviewed_by: ""
translation_of: es/08_Calidad_Mejoras.md#doc-te-0157
es_sha256: 8d90d2e8afa09c95fa9541c74b014f5a956b65e2d294d5739ad2ec047eec25b1
-->

# Software quality

**Software Quality**

Lozano Contreras Cristofer David

Santos Ortiz Jhampier

Análisis y Desarrollo de Softwares (Software Analysis and Development)

\(3145556\)

Servicio Nacional de Aprendizaje (National Learning Service)

September 24, 2025

**Introduction**

Software quality is a fundamental aspect in the development of any application, since it guarantees that the system meets the stated requirements, is reliable and offers a satisfactory experience to users. Documenting the errors found and the solutions applied, both in the development stage and in the technical documentation, is essential to improve processes, prevent future failures and maintain the traceability of the project.

In this case, the **“Tu Evento”** application is presented, a system designed for the layout design of logistics spaces and the management of reservations. This type of tool requires a high level of quality, given that it handles key information in the organization of events and depends on precision in the allocation of spaces and resources. For this reason, the identification, analysis and solution of problems are crucial to ensure that the software not only works correctly, but also meets the standards of usability, efficiency and reliability that users demand.

**Error Log**

1.  **Process in the documentation**

| **Description** | **Consequence** | **Solution** |
|----|----|----|
| Spelling errors were found in some documents. | Decrease in the quality of the delivered files. | The spelling errors were corrected with the help of tools such as Quillbot. |
| Some documents did not follow the APA standards. | Repeated review and correction of documents, with loss of time. | Those documents were adjusted to the APA standards. |
| The UML diagram did not include all the necessary attributes or methods. | It was necessary to review and complete the UML diagram. | The UML diagram was reviewed and completed. |
| The anonymous user role was not described in the system. | There was a lack of clarity in the permissions and functions of this role, which could affect security and usability. | The functions and limitations of the anonymous role were defined and documented. |
| The system constraints were not described with the necessary level of detail. | There was a risk of misinterpretations during development. | The constraints were expanded with technical explanations and clear examples. |
| The procedures for handling abnormal situations in the system had not been specified. | Risk of uncontrolled errors that would affect the user experience | The error handling cases and validations were added to the requirements. |
| The requirements had not been reviewed in sufficient detail. | Possible inconsistencies and omissions that would affect the quality of the software. | The functional and non-functional requirements were reviewed, corrected and complemented. |
| The acceptance criteria were not well defined and were not measurable. | Difficulty in the validation tests of the system. | The acceptance criteria were adjusted with clear and verifiable metrics. |
| The flow for requesting and approving to become an organizer was not described. | It could generate confusion in the process and delays in event management. | The requirement and the corresponding flow for the request and approval of organizers were added. |

2.  **Process in the development.**

| **Description** | **Consequence** | **Solution** |
|----|----|----|
| The frontend tries to consume backend APIs, but it does not have cross-origin permissions. | The browser blocks the requests and the app cannot communicate with the backend. | Configure CORS in Spring Boot through a global filter that allows the authorized domains. |
| The backend exposes APIs that do not match what the frontend expects. | Failed requests and loss of time in testing. | Document the APIs with Swagger and keep frontend and backend synchronized. |
| Badly configured routes in React Router (web) or React Navigation (mobile). | Blank screens or incorrect navigation. | Configure the routes correctly and use parameters/stack according to the app architecture. |
| Access to resources according to roles (admin, user, anonymous) is not validated correctly. | Users access restricted information. | Implement Spring Security in the backend . |
| Poor handling of promises, fetch without catching errors (.catch). | The user does not receive feedback when something fails. | Handle network errors correctly with try/catch and show alerts or modals in the frontend. |
| Security rules that are too open or too restrictive. | Unauthorized access or blocking of legitimate functions. | Define roles, secure routes and test with different users. |


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «0»<br>![Header of the original](../_assets/08_Mejora_Software/Calidad_de_Software/header_footer/image1.png)

---

<a id="doc-te-0156"></a>

<!--
ruta_anterior: en/08_Mejora_Software/Acciones_Correctivas_Preventivas_Mejora_TuEvento.md
id: TE-0156
title: "Acciones_Correctivas_Preventivas_Mejora_TuEvento"
lang: en
source: 08_Mejora_Software/Acciones_Correctivas_Preventivas_Mejora_TuEvento.pdf
source_sha256: e8b79ac2c0e213e1a21375f61e23bff17ec158db8cb0fc08cefea160185abbab
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 2–21: «TuEvento - Acciones correctivas, preventivas y de mejoramiento»."
  - "Page header or footer omitted on pages 2–21: «{n}»."
  - "Tables split across pages joined into a single one: 5→7; 8→9."
  - "Header row repeated by a page break omitted on pages 6–7."
  - "PDF generated without LaTeX: hyphens at the end of a line are real hyphens and are kept when joining lines (they are not syllabic line-break hyphens)."
  - "Manual table of contents (pages 2): the page numbers of the original are kept and the leader lines are removed."
  - "Cover page: highlighted lines that are not the title are written as paragraphs: «Servicio Nacional de Aprendizaje (SENA)»; «Documentación de acciones correctivas, preventivas y de mejoramiento del software»; «Autores»; «Instructor»."
  - "Tables with merged cells in HTML (colspan/rowspan calculated from the geometry of the borders); column widths, backgrounds and border thickness are not kept."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 99.76%, precision 100.00%, order 99.76%; missing {'Estado': 2, 'Tipo': 2, 'ID': 2, 'Módulo': 2, 'Problema': 2, 'Evidencia': 2} (explained above)."
  - "Differences in the check explained: the words that are «missing» (Estado, Tipo, ID, Módulo, Problema, Evidencia…) are the header rows repeated by a page break, omitted when joining the tables."
  - "Translation: class, method, file, migration and branch names, commit hashes and commit messages are kept as in the original, including the words split by the width of the PDF cells (for example «Wo mpiPaymentGatewayAd apter»); «No evidenciado» is translated as «Not evidenced»."
  - "Translation: numbers keep the format of the original (for example, «100.000» with a dot as thousands separator)."
status: borrador
reviewed_by: ""
translation_of: es/08_Calidad_Mejoras.md#doc-te-0156
es_sha256: 1711bed2dd81c391443ca24856b8824cf04485405bed2d68203bdc3602a8ff13
-->

# Corrective, preventive and improvement actions

**Servicio Nacional de Aprendizaje (SENA; National Learning Service)**

Análisis y Desarrollo de Software (ADSO; Software Analysis and Development)

Ficha (training group) 3145556

# TuEvento

*Documentation of corrective, preventive and improvement actions of the software*

**Authors**

Jhampier Santos Ortiz

Cristofer David Lozano Contreras

**Instructor**

Carlos Julio Cadena

October 2026

## Table of contents

1. Introduction 2

2. Scope and methodology 2

3. Definitions and classification 2

4. General summary 3

5. Summary table of actions 4

6. Detail of the actions 7

7. Continuous improvement summary 19

8. Action plan for the open cases 20

9. Conclusions 20

## 1. Introduction

This document records the corrective, preventive and improvement actions applied, in progress or pending on the TuEvento system during its development. Its purpose is to leave traceability of each nonconformity or risk detected, the cause identified, the action taken, the evidence that supports it and the current status, so that the continuous improvement process of the software is verifiable.

## 2. Scope and methodology

The analysis covers the repositories of the backend (Spring Boot), the web frontend (React and Vite), the mobile application (React Native and Expo) and the auxiliary services (fake-payment-gateway and nsfw-service), as well as the integration and deployment infrastructure (GitHub Actions, SonarQube Cloud, Docker and Kubernetes).

The actions were identified from the following sources: git history of the repositories (commits, branches and reverts), CHANGELOG.md, docs/EVIDENCIAS.md, checklist, pipeline technical document, technical manuals, TODO comments in the code, database migrations and existing tests. Each case was verified against the repository; the fields marked as "Not evidenced" correspond to data that could not be checked in the sources.

## 3. Definitions and classification

| **Term** | **Definition** |
|---|---|
| Corrective action | Action aimed at eliminating the cause of a nonconformity or of an error that has already occurred, to prevent it from recurring. |
| Preventive action | Action aimed at eliminating the cause of a potential nonconformity or of a risk detected before it causes a failure. |
| Improvement action | Action aimed at increasing the performance, quality or consistency of the product and its documentation. |
| Status: Closed | The action was executed and there is evidence of its application. |
| Status: In progress | The action was started, but it has not been completed or verified. |
| Status: Pending | The action was identified, but it has not yet been executed. |

## 4. General summary

26 actions were documented: 16 corrective, 5 preventive and 5 improvement. Of them, 20 are closed, 1 in progress and 5 pending.

### 4.1 By type of action

| **Type** | **Quantity** | **IDs** |
|---|---|---|
| Corrective | 16 | AC-001, AC-002, AC-003, AC-004, AC-005, AC-006, AC-007, AC-008, AC-009, AC-010, AC-011, AC-012, AC-013, AC-014, AC-015, AC-026 |
| Preventive | 5 | AC-016, AC-017, AC-018, AC-019, AC-020 |
| Improvement | 5 | AC-021, AC-022, AC-023, AC-024, AC-025 |

### 4.2 By status

| **Status** | **Quantity** | **IDs** |
|---|---|---|
| Closed | 20 | AC-001, AC-002, AC-003, AC-004, AC-005, AC-006, AC-007, AC-008, AC-009, AC-010, AC-011, AC-012, AC-013, AC-014, AC-015, AC-016, AC-018, AC-019, AC-021, AC-022 |
| In progress | 1 | AC-024 |
| Pending | 5 | AC-017, AC-020, AC-023, AC-025, AC-026 |

## 5. Summary table of actions

| **ID** | **Type** | **Module** | **Problem** | **Status** | **Evidence** |
|---|---|---|---|---|---|
| AC-001 | Corrective | Backend - Security | Seven authentication vulnerabilities (activation without validating the email, user enumeration, logout without ownership, among others). | Closed | Commit 91d4ada: fix(security): fix critical security vulnerabilities and improve exception handling. |
| AC-002 | Corrective | Backend - Security | RegisterUserUseCase and OauthLoginUseCase assigned the ATTENDEE role, which does not exist; the user was left without an effective role. | Closed | Commits 688c187 and bff4cee; recorded in the CHANGELOG. |
| AC-003 | Corrective | Backend - Security | The endpoints with hasAuthority('ADMIN') returned 403 because of the ROLE_ prefix in the authorities. | Closed | Commit f8464f3: fix(security): resolve 403 on admin endpoints by fixing JWT authority extraction. |
| AC-004 | Corrective | Backend - Security | The lockout after failed attempts did not persist and the automatic unlock did not work. | Closed | Commits d8a3dbd and c8860ea. |
| AC-005 | Corrective | Backend - Security (OAuth) | Facebook might not provide the email and the code tried to save NULL, violating a NOT NULL constraint. | Closed | Commit 311f244: fix: OAuth Facebook null email fallback and secure redirect whitelist. |
| AC-006 | Corrective | Backend - Payments | The sandbox gateway and the backend signed the webhook differently; all the webhooks were rejected. | Closed | Commit c835d12: fix(payment): align webhook HMAC signature encoding between fake-gateway and backend. |
| AC-007 | Corrective | Backend - Tickets and Seats | After a failed or cancelled payment, the seats remained in RESERVED indefinitely. | Closed | Commit ab29589: fix(ticket,seat): sync seat status with payment outcome. |
| AC-008 | Corrective | Database - Seats | The CHECK constraints used lowercase but JPA saves in UPPERCASE; each insertion violated the constraint. | Closed | Migration 073-fix-seat-l og-status-constraints.ya ml, incorporated in commit ab29589. |
| AC-009 | Corrective | Database - Comments | The code used reply_to_user_id and reply_to_user_name without a migration; the application failed on startup. | Closed | Commit a5ea593: fix(comments): add missing Liquibase migration 090 for reply_to fields. |
| AC-010 | Corrective | Web frontend - Comments | The WebSocket message arrived before the POST resolved, inserting the same comment twice. | Closed | Commit 5538ec4 (documented in the CHANGELOG). |
| AC-011 | Corrective | Web frontend - Event images | The canvas dimensions resulted in NaN and generated blank images or errors when uploading. | Closed | Commits c663779 and 688cb70 (branch fix/event -media-zoom-crop). |
| AC-012 | Corrective | Mobile frontend - Seat map | Seats cut off at the edges, incorrect zoom and centring, and setState inside the render. | Closed | Commits baad416, 556ce89, 45e4b0c, e2f2309 and 90df241. |
| AC-013 | Corrective | NSFW service / Docker | The libgl1-mesa-glx package no longer exists in Debian Bookworm and the image build failed. | Closed | Commit d473708: fix(storage): fix OpenNSFW2 tensorflow compatibility and moderation cascade. |
| AC-014 | Corrective | CI/CD - Jenkins | The pipeline skips the tests with -Dmaven.test.skip=true, contradicting the pipeline technical document. | Closed | Commits c026dc0, 37e84ec, 1b7c4d9 and 4b12d99; commit aa93102 (PR #93): .github/workflows/ci.yml runs ./mvnw -B verify. |
| AC-015 | Corrective | Backend - General configuration | The merge of Feature/login introduced regressions in the configuration and was reverted. | Closed | Commit e7a4f29: Revert 'Feature/login' (PR #12). |
| AC-016 | Preventive | Database - Comments | rating NOT NULL prevented additional comments and replies without stars. | Closed | Migration 087-event-rati ng-allow-multiple-nullab le-rating.yaml. |
| AC-017 | Preventive | Backend - Security | LOCKOUT_MINUTES = 1 is a development value; in production it should be 30 minutes. | Pending | LoginUseCase.java, line 34; administrator manual, section 4.5. |
| AC-018 | Preventive | Database - Profile | full_name defined with 100 characters while the domain validates a maximum of 30. | Closed | Migration 063-shrink-fu ll-name-to-30.yaml. |
| AC-019 | Preventive | CI/CD - SonarQube | The Quality Gate is documented as mandatory, but the SonarQube stage only runs an echo. | Closed | Commit 4b12d99; commit aa93102 (PR #93): analysis in SonarQube Cloud from .github/workflows/ci.yml. |
| AC-020 | Preventive | Backend - Security | The token cleanup runs once a day; the TODO indicates every 30 minutes in production. | Pending | SecurityDataCleanupTas k.java, line 52; commit 126e1a9: feat(security): add scheduled cleanup task for expired tokens and codes. |
| AC-021 | Improvement | Performance - Mobile frontend | The render with one circle per seat blocked the application in very large venues. | Closed | Commit cb31723: perf(mobile): implement DOD for 100k+ seats with TypedArrays and batch rendering. |
| AC-022 | Improvement | Performance - Backend / Web | The list triggered an additional query per event to obtain its category. | Closed | Commit f61cf52: refactor(events): use embedded categoryId instead of N+1 fetch. |
| AC-023 | Improvement | Documentation - Database | Some documents cite Flyway, but the project uses Liquibase exclusively. | Pending | pom.xml, lines 78-80; directory db/changelog/changes/. |
| AC-024 | Improvement | Backend - Payments | Wompi appears as the real gateway, but only the enum value exists; the payments use the sandbox gateway. | In progress | PaymentGateway.java, line 8; absence of Wo mpiPaymentGatewayAd apter. |
| AC-025 | Improvement | Backend - Messaging | The spring-kafka dependency is in the pom.xml, but there are no producers, consumers or topics. | Pending | pom.xml, lines 82-83 and 150-151; search in src/main/java without results. |
| AC-026 | Corrective | Backend / Frontend - Languages | The multi-language support required by the SRS is not fully implemented. | Pending | Statement of the development team; language module of the backend without automated tests. |

## 6. Detail of the actions

### 6.1 Corrective actions

<table>
<tr>
<td colspan="2"><strong>AC-001</strong> Critical authentication vulnerabilities <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>7 vulnerabilities were identified: (a) activation code not validated against the email, (b) recovery code not validated against the email, (c) logout without verifying the ownership of the session, (d) login without verifying the BLOCKED/INACTIVE/DELETED statuses, (e) lockout message that exposed the exact timestamp, (f) password recovery that revealed whether the email existed, (g) refresh token without validating that the user was still active.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Initial implementation of the security module focused on the happy path, without an OWASP-type vulnerability review.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Correction in 11 security use cases, improvement of the GlobalExceptionHandler, standardization of messages to avoid enumeration and email validation in activation and recovery.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit 91d4ada: fix(security): fix critical security vulnerabilities and improve exception handling.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-04-13</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The commit modifies 11 use cases. There is no automated test that covers these negative security flows.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-002</strong> Nonexistent role assigned when registering users <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The use cases RegisterUserUseCase and OauthLoginUseCase assigned the role code ATTENDEE, which does not exist in the roles table. Registered users did not obtain an effective role.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The role changed its name from ATTENDEE to USER during the design and the code was not updated.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The role code was corrected to USER in both use cases. Updating the class diagrams that still show ATTENDEE remains pending.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commits 688c187 and bff4cee; recorded in the CHANGELOG.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-03-28</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>OauthLoginUseCaseOnboardingTest covers the OAuth flow; there is no explicit test of the role assigned after registration.</td>
</tr>
<tr>
<td colspan="2"><strong>AC-003</strong> 403 error on administrator endpoints <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The endpoints protected with hasAuthority('ADMIN') returned 403 because SecurityUser registered the authority as ROLE_ADMIN. In addition, the JWT filter used a manual Base64 parser instead of JJWT.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Confusion between hasRole() (adds a prefix) and hasAuthority() (without a prefix) in Spring Security 6.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The ROLE_ prefix was removed, the JWT filter was rewritten with TokenGeneratorPort and @EnableMethodSecurity was added in SecurityConfig.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit f8464f3: fix(security): resolve 403 on admin endpoints by fixing JWT authority extraction.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-03-28</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The /api/v1/admin/** endpoints operate with the ADMIN role according to the administrator manual.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-004</strong> Account lockout without transactional persistence <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The automatic lockout after 5 failed attempts was not saved because of a transactional propagation problem in AccountLockoutService. The automatic unlock on expiry did not work either.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>REQUIRES_NEW propagation applied incorrectly and an unlock job that did not query the expired lockouts.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The transactional flow was corrected, an @Scheduled job running every minute was created to expire lockouts and the login now checks the lockout before evaluating the user's status.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commits d8a3dbd and c8860ea.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-04-14 / 2026-04-15</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The behaviour is documented in section 4.5 of the administrator manual.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-005</strong> Null email in OAuth with Facebook <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security (OAuth)</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>Facebook does not always return the email (the user may not grant the permission). The code tried to save NULL in oauth_account.email, violating the NOT NULL constraint and throwing an unhandled exception.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The linked-account branch did not have the same synthetic fallback as the new-account branch.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>A synthetic email providerUserId@facebook.oauth was added when the email is null or empty.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit 311f244: fix: OAuth Facebook null email fallback and secure redirect whitelist.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-21</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>No specific test for this case is evidenced.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-006</strong> Inconsistent HMAC signature of the webhook <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Payments</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The sandbox gateway signed the webhook with an encoding different from the one the backend expected to verify HMAC-SHA256. All the payment webhooks arrived with an invalid signature and the payments were not completed.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Independent implementations of the gateway and the backend without a shared encoding contract.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The HMAC-SHA256 algorithm was aligned with HexFormat and StandardCharsets.UTF_8 on both sides.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit c835d12: fix(payment): align webhook HMAC signature encoding between fake-gateway and backend.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-21</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>No test that validates the HMAC signature is evidenced.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-007</strong> Seats not synchronized with the payment outcome <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Tickets and Seats</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>When a payment failed or was cancelled, the seats remained in RESERVED status, blocking their availability for other buyers.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The seat transition logic did not contemplate the rejected or cancelled payment flow.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>SeatService now transitions the seats to AVAILABLE when the payment is not approved.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit ab29589: fix(ticket,seat): sync seat status with payment outcome.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-21</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>No specific unit test; verified functionally in the improved checkout (commit e5209e6).</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-008</strong> seat_log constraints with a case difference <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Database - Seats</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The CHECK constraints of seat_log used lowercase values, but JPA with EnumType.STRING persists in UPPERCASE. Each insertion in seat_log violated the constraint.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The initial migrations were written in lowercase without considering the behaviour of EnumType.STRING.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Migration 073 removes the old constraints, updates the existing data to UPPERCASE and recreates the correct constraints.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Migration 073-fix-seat-log-status-constraints.yaml, incorporated in commit ab29589.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-21</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The Liquibase migrations run at startup; if the correction failed, the server would not start.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-009</strong> Missing migration for the reply_to columns <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Database - Comments</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The comments module used the columns reply_to_user_id and reply_to_user_name in entities, DTOs and queries, but the migration that creates them did not exist. The application failed on startup.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Migration 090 was omitted in the development branch and was not detected until the deployment attempt.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Migration 090-event-rating-add-reply-to-fields was created retroactively.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit a5ea593: fix(comments): add missing Liquibase migration 090 for reply_to fields.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-10-07</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The server starts correctly and the columns are available for the code that uses them.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-010</strong> Duplicate comments due to a race condition <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Web frontend - Comments</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>When a comment was published, the WebSocket message arrived before the POST resolved. The identifier was not yet in commentIdsRef, so the WS handler inserted the comment and then the POST inserted it again, generating two elements with the same key and two edit forms open.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Update of the local state without idempotency; the reference of known IDs was only updated after the POST.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Idempotency guard in all the setComments calls, a second guard in the WS handler and union (instead of replacement) of commentIdsRef when reloading through REST.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit 5538ec4 (documented in the CHANGELOG).</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-10-08</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>There are no automated frontend tests; functional verification only.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-011</strong> Image normalization canvas returned NaN <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Web frontend - Event images</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>When normalizing images for the event upload, the canvas dimensions resulted in NaN, generating a blank image or errors when uploading.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>.map() was used as a function reference instead of accessing the correct attribute, and URL.revokeObjectURL was called before toBlob finished.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The attribute access was corrected and revokeObjectURL was moved to the toBlob callback.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commits c663779 and 688cb70 (branch fix/event-media-zoom-crop).</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-22</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Not evidenced</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-012</strong> Visual clipping and incorrect navigation of the seat map <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Mobile frontend - Seat map</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The seats at the edges of the view were cut off, the zoom of the general view did not centre correctly and setState was called inside the render, causing re-renders.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Fixed sizing without considering margins, bounding box calculated over the complete section and state logic inside the render cycle.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Adaptive sizing with margins, bounding box per real seat, moving setState out of the render and correction of the pagination in irregular sections.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commits baad416, 556ce89, 45e4b0c, e2f2309 and 90df241.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-07 to 2026-09-15</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Not evidenced</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-013</strong> Failure when building the image of the NSFW classifier <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>NSFW service / Docker</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The libgl1-mesa-glx package was removed in Debian Bookworm and the Dockerfile of the NSFW service failed during apt-get install.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Change in the dependencies of the base operating system of the Docker image, without validating compatibility when updating.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>libgl1-mesa-glx was replaced by libgl1 in the Dockerfile.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit d473708: fix(storage): fix OpenNSFW2 tensorflow compatibility and moderation cascade.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-05-14</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The image builds correctly in the pipeline after the correction.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-014</strong> Unit tests disabled in the pipeline <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>CI/CD - Jenkins</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The pipeline technical document states that Stage 3 runs unit tests and that a Quality Gate requires coverage greater than 80%. The current Jenkinsfile uses -Dmaven.test.skip=true in the Unit Tests stage, so the tests are not run.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The PostgreSQL database was not accessible from the Jenkins container (Docker-in-Docker), so the tests were temporarily disabled.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Several commits iterated unsuccessfully on the configuration of Testcontainers and Docker-in-Docker; as a temporary solution the tests were disabled. Later, the Jenkins pipeline was deactivated and replaced by GitHub Actions, whose backend job runs the tests with ./mvnw -B verify.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commits c026dc0, 37e84ec, 1b7c4d9 and 4b12d99; commit aa93102 (PR #93): .github/workflows/ci.yml.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-05-05 (start); 2026-10-23 (closure)</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos; Cristofer Lozano (closure)</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The 13 test files of the backend run on every push or pull request; the run of the CI workflow on the develop branch (commit 33cd5ab) completed successfully.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-015</strong> Revert of the Feature/login merge <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - General configuration</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The merge of the Feature/login branch introduced regressions in the general configuration (pom.xml, application.yml, environment variables) and was completely reverted.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>git revert of the merge was run and the security module was reintegrated in separate branches with review.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit e7a4f29: Revert 'Feature/login' (PR #12).</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-04-09</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The security module was correctly reintegrated in later commits.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-026</strong> Languages module (multi-language) incomplete with respect to the SRS <strong>Pending</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend / Frontend - Languages</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The SRS requires support for multiple languages, but this functionality is not fully implemented. The backend has a language module, which has no automated tests.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Prioritization of other features during development.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Pending execution: complete the languages functionality in accordance with the requirements of the SRS.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Statement of the development team; language module of the backend without automated tests.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: validate compliance against the functional requirements of the SRS and add tests.</td>
</tr>
</table>

### 6.2 Preventive actions

<table>
<tr>
<td colspan="2"><strong>AC-016</strong> Rating model did not allow multiple comments <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Database - Comments</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>event_rating had rating NOT NULL between 1 and 5, which forced a rating to be included in each comment. The business rule evolved: only the first comment carries stars.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Insufficient anticipation of the multiple comments and replies model during the initial design of the database.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Migration 087 makes rating nullable, updates the CHECK to rating IS NULL OR rating BETWEEN 1 AND 5 and adds a composite index for the antispam control.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Migration 087-event-rating-allow-multiple-nullable-rating.yaml.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced (author of the changeset: capysoft)</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>AddEventRatingServiceTest includes 18 cases that cover the rating, antispam, organizer role and replies rules.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-017</strong> Account lockout time of 1 minute <strong>Pending</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The constant LOCKOUT_MINUTES = 1 is configured for development. In production it should be 30 minutes according to the administrator manual (section 4.5). If it is deployed without change, the protection against brute force is minimal.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Value reduced to facilitate development and testing.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>TODO documented in the code (restore to 30 for production). It has not been modified yet.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>LoginUseCase.java, line 34; administrator manual, section 4.5.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: externalize the value to an environment variable or configuration profile.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-018</strong> Inconsistency between VARCHAR(100) and the 30-character validation <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Database - Profile</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>full_name was defined as VARCHAR(100), but the domain validation limits the full name to 30 characters. The schema did not reflect the business rule.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The 30-character constraint was defined during development without updating the original migration.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Migration 063-shrink-full-name-to-30 reduces the column to VARCHAR(30).</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Migration 063-shrink-full-name-to-30.yaml.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced (author of the changeset: capysoft)</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The migration documents the previous validation: no existing row exceeded 30 characters (the longest had 21).</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-019</strong> Quality analysis (SonarQube) disabled <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>CI/CD - SonarQube</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>PIPELINE-TECHNICAL-DOCUMENT.md describes a Quality Gate with coverage greater than 80%, 0 critical bugs and 0 vulnerabilities. The Jenkinsfile replaces the SonarQube stage with an echo.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>The SonarQube server was not consistently available in the CI environment.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Stage disabled; the sonar-project.properties file exists in the repository as preparation. Later, the analysis was moved to SonarQube Cloud, run from GitHub Actions with the sonar-project.properties file at the root of the repository.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit 4b12d99; commit aa93102 (PR #93): .github/workflows/ci.yml and sonar-project.properties.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-05-05; 2026-10-23 (closure)</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Jhampier Santos; Cristofer Lozano (closure)</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>The SonarQube Cloud analysis runs in the backend job of the CI workflow; the run on the develop branch (commit 33cd5ab) completed successfully. Results: https://sonarcloud.io/project/overview?id=lozano2303_TuEvento.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-020</strong> Token cleanup frequency inadequate for production <strong>Pending</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Security</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The cron 0 0 2 * * * cleans expired tokens only once a day (2 AM). In production, revoked tokens and expired codes can accumulate for hours. The TODO indicates changing it to 0 0/30 * * * *.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Development value chosen to reduce noise in the logs during testing.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>TODO documented in the code. It has not been modified yet.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>SecurityDataCleanupTask.java, line 52; commit 126e1a9: feat(security): add scheduled cleanup task for expired tokens and codes.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-03-28</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: externalize the cron to an environment variable or Kubernetes profile.</td>
</tr>
</table>

### 6.3 Improvement actions

<table>
<tr>
<td colspan="2"><strong>AC-021</strong> Performance of the seat map with more than 100.000 seats <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Performance - Mobile frontend</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The seat selection canvas blocked with venues of more than 100.000 seats when rendering an individual circle per seat.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Object-oriented architecture for data that requires massive rendering.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>Data-Oriented Design pattern: seat data in TypedArrays (Float32Array, Uint8Array) and sceneFunc for batch rendering with Skia.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit cb31723: perf(mobile): implement DOD for 100k+ seats with TypedArrays and batch rendering.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-09-16</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>No benchmark is evidenced; the improvement is described in the commit message.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-022</strong> N+1 query in the event list <strong>Closed</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Performance - Backend / Web</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>The event list triggered an additional query for each event to obtain its category.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Use of a lazy JPA relationship for the category without a fetch join.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>The categoryId embedded in the entity is used instead of navigating the relationship.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>Commit f61cf52: refactor(events): use embedded categoryId instead of N+1 fetch.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>2026-08-04</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Cristofer Lozano</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>No benchmark or performance test is evidenced.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-023</strong> Documentary inconsistency between Flyway and Liquibase <strong>Pending</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Documentation - Database</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>Some documents mentioned Flyway as the migration manager, when the project uses Liquibase exclusively. This can cause confusion when configuring deployment environments.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Documentary inconsistency inherited from early versions of the technical manual.</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>It was verified that the project uses Liquibase (liquibase-core in pom.xml and 97 YAML change files) and that there is no Flyway dependency. The documents that mention Flyway remain to be corrected.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>pom.xml, lines 78-80; directory db/changelog/changes/.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: review overview.md, PIPELINE-TECHNICAL-DOCUMENT.md and the technical manual.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-024</strong> Wompi gateway documented but not implemented <strong>In progress</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Payments</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>overview.md, the technical manual and the technical proposal document Wompi as the real payment gateway. In the code, only WOMPI exists as an enum value in PaymentGateway.java (comment: real gateway not implemented yet). All the payments use fake-payment-gateway.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>It was defined that the platform uses the sandbox payment gateway fake-payment-gateway, for testing the payment flow and connected to the backend, instead of Wompi, and the project documentation was adjusted.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>PaymentGateway.java, line 8; absence of WompiPaymentGatewayAdapter; FakePaymentGatewayAdapter.java and application-dev.yml (payment.gateway, default value fake).</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: the README of the code repository and the terms and privacy texts of the web and the mobile app still mention Wompi.</td>
</tr>
</table>

<table>
<tr>
<td colspan="2"><strong>AC-025</strong> Apache Kafka declared but not implemented <strong>Pending</strong></td>
</tr>
<tr>
<td><strong>Module / component</strong></td>
<td>Backend - Messaging</td>
</tr>
<tr>
<td><strong>Problem or</strong> <strong>nonconformity</strong></td>
<td>overview.md and the technical manual list Spring Kafka as the messaging technology. The dependency is declared in pom.xml, but there is no producer, consumer or topic configured in the code.</td>
</tr>
<tr>
<td><strong>Root cause</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Action taken</strong></td>
<td>No implementation commit is evidenced.</td>
</tr>
<tr>
<td><strong>Evidence</strong></td>
<td>pom.xml, lines 82-83 and 150-151; search in src/main/java without results.</td>
</tr>
<tr>
<td><strong>Date</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Owner</strong></td>
<td>Not evidenced</td>
</tr>
<tr>
<td><strong>Verification of</strong> <strong>effectiveness</strong></td>
<td>Pending: verify in the SRS whether asynchronous messaging is a requirement; if it is, it must be implemented; if not, remove the dependency and adjust the documentation.</td>
</tr>
</table>

## 7. Continuous improvement summary

The history of the project shows a clear evolution in four dimensions.

**Security.** April concentrates the highest density of corrections: the critical authentication vulnerabilities (user enumeration, activation without validating the email, lockout without transactional persistence) were closed in a block of about three weeks, which indicates a systematic review after the implementation of the module. The OAuth integration with Facebook and Google generated additional corrections in September, in particular on null emails and redirections.

**Performance.** The most significant improvement occurred in the mobile application: the seat map went from object rendering to Data-Oriented Design with TypedArrays, which enables venues of more than 100.000 seats. In the backend, an N+1 pattern in the event list was corrected. Both improvements arose when testing with more realistic data.

**Testing.** The project went from having no tests to having 13 unit test files in the backend (around 40 cases), concentrated in the event, security and notification modules. The test pattern is solid and, since the migration to GitHub Actions, these tests run on every push or pull request; however, the scope covers 3 of 14 modules, which constitutes the main pending technical debt.

**Deployment.** The Jenkins pipeline required at least eight correction commits between April and May to stabilize, but it was left with the tests and the static analysis disabled. In October it was deactivated and replaced by GitHub Actions, which runs the backend tests, builds the web and the mobile app and sends the analysis to SonarQube Cloud; the Kubernetes manifests and the docker-compose constitute the basis for declarative deployment. Automating the building of images and the deployment remains pending.

## 8. Action plan for the open cases

The following actions are proposed to close the cases in progress and pending, ordered by priority.

| **ID** | **Proposed action** | **Priority** |
|---|---|---|
| AC-026 | Complete the languages module in accordance with the requirements of the SRS and add automated tests. | High |
| AC-017 | Externalize LOCKOUT_MINUTES to an environment variable with a value of 30 minutes in production. | High |
| AC-020 | Externalize the token cleanup cron and set it to 30 minutes for production. | Medium |
| AC-023 | Correct in the documentation every reference to Flyway, replacing it with Liquibase. | Medium |
| AC-024 | Remove the mentions of Wompi from the README of the code repository and from the terms and privacy texts of the web and the mobile app. | Medium |
| AC-025 | Verify in the SRS whether asynchronous messaging is a requirement; if it is, implement it; if not, remove the dependency and adjust the documentation. | Low |
| AC-002 | Update the class diagrams that still show the ATTENDEE role, replacing it with USER. | Low |

## 9. Conclusions

The record evidences an active continuous improvement process: most of the actions (20 of 26) are closed and supported by verifiable commits or migrations. The open cases are concentrated in the configuration of production-specific values, the completion of features required by the SRS and the alignment between the documentation and the implemented code. Closing them will reduce the technical risk of the system and will improve traceability with respect to the technical documentation.
