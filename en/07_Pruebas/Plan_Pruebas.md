---
title: "Test plan"
lang: en
documents: [TE-0153]
status: borrador
---
# Test plan — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Test plan](#doc-te-0153)

---

<a id="doc-te-0153"></a>

<!--
ruta_anterior: en/06_Pruebas/Plan_de_Pruebas_TuEvento.md
id: TE-0153
title: "Plan_de_Pruebas_TuEvento"
lang: en
source: 06_Pruebas/Plan_de_Pruebas_TuEvento.pdf
source_sha256: d3da5836fe35004eb6076e8aed53a6bd22d75309434a2be8cf7209aefee48040
conversion: "pdfplumber 0.11.10 following the structure tree of the tagged PDF; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Untagged text (pagination artifact) omitted on 17 of 17 pages: «Plan de pruebas Tu Evento · página {n}»."
  - "Header row repeated by a page break omitted in the table that starts with «Fase»."
  - "Header row repeated by a page break omitted in the table that starts with «Riesgo»."
  - "Header row repeated by a page break omitted in the table that starts with «Método»."
  - "Header row repeated by a page break omitted in the table that starts with «Método»."
  - "Header row repeated by a page break omitted in the table that starts with «Capacidad»."
  - "Header row repeated by a page break omitted in the table that starts with «Sistema»."
  - "Bold, italics and monospaced font (Courier) of the original are not kept."
  - "GFM tables with the first row as header; the paragraphs inside a cell are separated with <br>."
  - "Translation: endpoints, routes, error codes, enumeration values, field names, file names and the names of web routes and mobile screens (Inicio, Eventos, Perfil, Landing…) are kept as in the original."
  - "Translation: numbers keep the format of the original (for example, «100000» and «10 MB»)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Plan_Pruebas.md#doc-te-0153
es_sha256: 3133ab530ce773886bd0b467776175ad5a2090dd4ed3938ec4f6f27cd3e78f8f
-->

# Test plan

TEST PLAN

Tu Evento Platform

Team: CapySoft

Programme: Análisis y Desarrollo de Software (ADSO; Software Analysis and Development), SENA, ficha (training group) 3145556

Instructor: Karol Daniela Correa

Team leader: Cristofer David Lozano Contreras

Version: 1.0

Date: 9 October 2026

# 1. Introduction and objective

Tu Evento is a CapySoft platform to create, publish and operate events, with ticket sales per seat, payments, a credit wallet, notifications and entry validation by QR. This document defines how it will be verified that the system meets expectations before it is delivered.

General objective: to check that the features of the backend (Spring Boot), the web (React) and the mobile app (React Native/Expo) behave according to the business rules, that permissions by role are respected and that the critical purchase, payment and refund flows are reliable.

## Specific objectives

- Validate the registration, activation, login and access recovery flows.
- Validate the event life cycle, from DRAFT to PUBLISHED, CANCELLED or COMPLETED.
- Validate seat reservation, the order, the payment and the webhook, including concurrency.
- Validate refunds and the use of the wallet (wallet only, mixed and through the gateway).
- Verify authorization by role (USER, ORGANIZER, ADMIN) and detect known security gaps.

# 2. Scope

## In scope

- Authentication (32 cases)
- Users (9 cases)
- Administration (6 cases)
- Profile (5 cases)
- Events (21 cases)
- Media and layout (7 cases)
- Ratings and comments (6 cases)
- Categories and sites (7 cases)
- Sections and seats (9 cases)
- Orders and tickets (12 cases)
- Payments (16 cases)
- Wallet (5 cases)
- Notifications (4 cases)
- Themes and languages (6 cases)
- Security and storage (6 cases)

## Out of scope

- Load and extreme performance tests, except the basic verification of seat concurrency.
- Real payment gateway: the payment is made with the team's sandbox payment gateway, for testing the payment flow and connected to the backend; no real payments are processed.
- Native push notifications (FCM/APNs): they are not implemented.
- QR reader in the clients: there is no interface; check-in is tested through the API.
- DevOps pipeline (GitHub Actions, SonarQube Cloud, Kubernetes) and the Redis infrastructure.

# 3. Test types and strategy

| Type | What is verified | Tool |
|---|---|---|
| Functional | Each endpoint and screen with valid and invalid data | Postman or Swagger (/swagger-ui) and browser |
| Boundary | Extreme values (maximum attendance 1 and 100000, texts of 255 and 256 characters) | Postman |
| Integration | Backend with the sandbox gateway, MinIO, Gmail SMTP, LibreTranslate | Complete manual flow |
| Security | Roles, JWT, HMAC signature of the webhook, OAuth redirections | Postman with different tokens |
| Concurrency | Two users on the same seat | Two sessions or two simultaneous requests |
| Acceptance | End-to-end flows by role on web and mobile | Browser and Expo Go |

Approach: the tests are manual, on the API and the interface. The negative cases are mapped to the code field of the error response. Each case is run with the procedure described in the file Casos_de_Prueba_TuEvento.xlsx, which is the complementary document of this plan.

# 4. Test environment

| Component | Configuration |
|---|---|
| Backend | Spring Boot, monolith with the /api/v1 prefix, development profile |
| Database | PostgreSQL 17 with Liquibase |
| Storage | MinIO (S3 API) |
| Payment gateway | fake-payment-gateway on port 4001, with a webhook signed with HMAC (payment.gateway: fake) |
| Email | Gmail SMTP for activation, recovery and notifications |
| Translation | LibreTranslate in Docker |
| Image moderation | Local NSFW service and Sightengine |
| Web | React + Vite in a current desktop browser |
| Mobile | Expo / React Native with Expo Go |
| Test users | One USER, one ORGANIZER and one ADMIN with real @gmail.com emails to receive codes |

Note: the endpoint GET /auth/dev/activate-code/{email} is used to obtain the activation code without opening the email, only in the test environment.

# 5. Entry and exit criteria

## Entry criteria

- Backend, web and mobile deployed in the test environment and without startup errors.
- Sandbox gateway, MinIO, PostgreSQL and SMTP available.
- Test users created for each role and at least one active site and one active category.
- Test cases reviewed by the team.

## Exit criteria

- 100 % of the High priority cases executed.
- At least 95 % of the High priority cases passed.
- No open defect of critical severity in payments, orders or security.
- The remaining defects recorded with their priority and decision (fix or accept).

## Suspension criteria

Testing is stopped if the backend does not start, if the database does not respond or if the sandbox gateway is not available, since they block the purchase flows.

# 6. Roles and responsibilities

| Role | Responsibility |
|---|---|
| Team leader | Approve the plan, prioritize defects and decide the closure |
| Test designer | Write and maintain the test cases |
| Executor | Run the cases, record the actual result and evidence |
| Development (backend/web/mobile) | Fix defects and confirm the cause |
| Instructor | Academic review of the document |

As CapySoft is a two-person team, it is common for the same person to fulfil several roles. It is recommended that whoever runs a case is not the person who wrote the code being tested.

# 7. Schedule

| Phase | Activity | Estimated duration | Owner |
|---|---|---|---|
| 1 | Review of the plan and the cases | 1 day | Team |
| 2 | Authentication, user and profile tests | 2 days | Executor |
| 3 | Event, layout and seat tests | 2 days | Executor |
| 4 | Order, payment, wallet and refund tests | 3 days | Executor |
| 5 | Security, notification, theme and language tests | 1 day | Executor |
| 6 | Defect correction and regression | 2 days | Development |
| 7 | Final results report | 1 day | Leader |

The durations are estimates and must be adjusted to the SENA delivery dates.

# 8. Test case summary

The file Casos_de_Prueba_TuEvento.xlsx contains 151 cases distributed as follows:

| Module | Cases |
|---|---|
| Authentication | 32 |
| Users | 9 |
| Administration | 6 |
| Profile | 5 |
| Events | 21 |
| Media and layout | 7 |
| Ratings and comments | 6 |
| Categories and sites | 7 |
| Sections and seats | 9 |
| Orders and tickets | 12 |
| Payments | 16 |
| Wallet | 5 |
| Notifications | 4 |
| Themes and languages | 6 |
| Security and storage | 6 |
| Total | 151 |

Each case includes an identifier, a reference to the requirement or section of the technical inventory (traceability), type, priority, preconditions, steps, input data and expected result. The actual result, status and evidence columns are filled in when executing. The reference of each case points to a section of the technical inventory (Annex A).

# 9. Risks

| Risk | Impact | Mitigation |
|---|---|---|
| Sandbox gateway different from a real gateway | High | Document the difference and repeat the payment tests if a real gateway is integrated |
| Dependency on external services (SMTP, Google OAuth, Sightengine) | Medium | Test with test accounts and record network failures as blocked |
| Concurrency cases that are difficult to reproduce | Medium | Use two sessions and repeat several times |
| Mobile with fewer features than the web | Medium | Limit the mobile cases to the available flows |
| Known security gaps not fixed | High | Include specific cases and report them as defects |
| Account lockout of only 1 minute in development | Low | Take it into account when testing the attempt limit |

# 10. Known findings before execution

The analysis of the code identified behaviours that will probably fail in the security cases. They are included as cases to confirm them and record them as defects:

- GET /tickets/user/{userId} does not verify that the requester is the same user.
- POST /orders/{id}/cancel does not check the owner of the order.
- POST /tickets/{id}/checkin can be run by any authenticated user; there is no staff role.
- The storage routes are marked as public in SecurityConfig.
- The /auth/dev/activate-code endpoint exists and must be disabled in production.
- Actuator is public.
- The global list of pending translation jobs returns an empty list.

# 11. Defect management

Each defect is recorded with: identifier, associated test case, description, steps to reproduce it, expected and actual result, evidence (screenshot or API response), severity and status.

| Severity | Criterion | Example |
|---|---|---|
| Critical | It prevents a main flow or compromises data or money | A paid order leaves the seats free |
| High | An important function fails with a difficult workaround | A USER can perform check-in |
| Medium | Partial failure with a workaround | Incorrect error message |
| Low | Cosmetic or minor defect | Misaligned text |

Statuses of a defect: New, In correction, Fixed, Verified and Closed. Every fixed defect requires repeating the case that detected it and the related cases.

# 12. Results of the 2026-10-24 run

The 151 cases were run on 2026-10-24 against commit `2d259e7` of `develop`, in an isolated local environment. The environment, the procedure and the defect details are in [Ejecucion_Pruebas_2026-10-24.md](Evidencias/Ejecucion_Pruebas_2026-10-24.md). The result of each case is in [Casos_de_Prueba_TuEvento.md](Evidencias/Casos_de_Prueba_TuEvento.md).

| Result | Cases |
|---|---|
| Passed | 128 (84.8 %) |
| Failed | 18 |
| Blocked | 5 (Google OAuth, image moderation, machine translation and mobile app) |
| Pending | 0 |

The backend automated tests (`./mvnw verify`) ran 222 tests with no failures, with 15.0 % line coverage according to JaCoCo.

The most serious defects are the double booking of the same seat with simultaneous requests (critical) and the already known authorization gaps in orders, tickets, check-in, storage and the development activation endpoint (high). Five of the seven findings of section 10 were confirmed: tickets by user, cancelling other users' orders, check-in without a role, public storage routes and the development activation endpoint. Actuator today only exposes `health`, but Swagger UI and `/api-docs` are public. The pending translation jobs list could not be checked because LibreTranslate was not running.

Against the exit criteria of section 5: of the 72 High priority cases, 71 were run (CP-MED-02 was blocked) and 61 passed (84.7 %, below the required 95 %), and one critical defect remains open in seat reservation. The version does not yet meet the criteria to close the test cycle.

# 13. References

CapySoft. (2026). Inventario técnico de Tu Evento para pruebas [Internal document]. It is included in full as Annex A of this document.

CapySoft. (2026). Casos de prueba de Tu Evento (Casos_de_Prueba_TuEvento.xlsx) [Internal document].

# Annex A. Technical inventory of Tu Evento for testing

Survey of the current state of the system (backend, web and mobile), prepared with the support of an AI assistant from the analysis of the code. It describes what the system does today, not the original requirements, and it must be checked against the code and the requirements before being considered final. Date of the survey: October 2026.

Test document based on the current code of the backend, web and mobile. In most cases the API responses come in the envelope { success, message, code, data }. Payments (create and query) and some translation/admin endpoints do not use that envelope.

## 1. What Tu Evento is and main modules

CapySoft platform to create and publish events, sell tickets and operate events (layout, seats, payments, QR). The Spring Boot backend is the core. There is a web frontend (Vite/React) and a mobile app (Expo/React Native). The README still talks about Wompi and an API Gateway; in the development code the payment runs against a sandbox gateway (payment.gateway: fake).

Backend (modules)

Security, profile, event (media, layout, ratings/comments), category, geolocation, section, seat, ticket/order, payment, wallet, notification, theme, language/translation, storage.

Web

Landing, catalogue and event detail, creation wizard, layout editor, event management, checkout and payment confirmation, wallet, profile, notifications, organizer request, admin dashboards (requests and events). The venue design is exclusive to the web.

Mobile

Landing, registration/login/activation, password recovery, list and detail, checkout and pending payment, profile/themes, and admin screens for organizer requests. There is no creation wizard or layout editor. There is no QR entry scanner screen.

## 2. HTTP error convention (applicable to almost all endpoints)

| Code | When |
|---|---|
| 200 / 201 | Success (201 on creations: registration, event, order, payment, profile, site) |
| 400 | Bean Validation validation, malformed JSON, BusinessException, IllegalStateException |
| 401 | No JWT, invalid/expired JWT, invalid HMAC signature of the webhook, AuthenticationException |
| 403 | Authenticated without role/authority (Access denied) |
| 404 | Resource not found (NotFoundException) |
| 405 | HTTP method not supported |
| 409 | Integrity (ConstraintViolationException), duplicate site/profile, invalid payment or order transition |
| 422 | Image policy (moderation) or insufficient wallet balance |
| 500 | Unhandled error (An unexpected error occurred) |

In business 400 errors the code field is the identifier for mapping tests (e.g. EVENT_START_DATE_IN_PAST). Expired JWT: the web client tries to refresh; 403 does not trigger a refresh.

## 3. Endpoints and screens (method, route, parameters, responses, errors)

API prefix: /api/v1, except admin translation (/api/admin/translations). Authentication: header Authorization: Bearer &lt;accessToken&gt; except for public routes.

3.1 Authentication (/api/v1/auth) — public

| Method | Route | Parameters | Success | Typical errors |
|---|---|---|---|---|
| POST | /register | Body: email, password, fullName | 201. Account created; it must be activated by email | 400 INVALID_EMAIL (Gmail only), INVALID_PASSWORD, INVALID_NAME, EMAIL_ALREADY_EXISTS, EMAIL_NOT_ACTIVATED |
| POST | /activate | email, activationCode | 200 | 400 ACCOUNT_ALREADY_ACTIVATED, INVALID_ACTIVATION_CODE, ACTIVATION_CODE_EXPIRED |
| POST | /resend-activation | email | 200 | 400 EMAIL_ALREADY_ACTIVATED |
| POST | /login | email, password | 200: tokens, userId, alias, role | 404 USER_NOT_FOUND; 400 ACCOUNT_NOT_ACTIVATED, ACCOUNT_BLOCKED, ACCOUNT_DEACTIVATED, ACCOUNT_DELETED, INVALID_CREDENTIALS, ACCOUNT_LOCKED |
| POST | /logout | accessToken | 200 | 400 UNAUTHORIZED_LOGOUT |
| POST | /refresh | refreshToken | 200 new tokens | 400 REFRESH_TOKEN_REVOKED, REFRESH_TOKEN_EXPIRED, ACCOUNT_NOT_ACTIVE |
| POST | /recover-password | email | 200 (generic message; users are not enumerated) | — |
| POST | /reset-password | code + new passwords | 200 | 400 PASSWORD_MISMATCH, INVALID_RECOVERY_CODE, RECOVERY_CODE_USED, RECOVERY_CODE_EXPIRED |
| GET | /oauth/{provider} | Query: state, frontend_redirect_uri | 302 to the provider | 400 if the provider does not exist |
| GET | /oauth/{provider}/callback | code, state; response_format=json on mobile | 302 to the frontend (web) or 200 JSON (mobile) | OAuth failures |
| POST | /google | GSI ID token | 200 login | 400 GOOGLE_TOKEN_INVALID, GOOGLE_EMAIL_NOT_VERIFIED |
| POST | /reactivate-request | email | always 200 (anti- enumeration) | — |
| POST | /reactivate-confirm | reactivation token | 200 | 400 invalid/expired token |
| GET | /dev/activate-code/{email} | email | 200 code (tests only) | 404 EMAIL_NOT_FOUND; 400 NO_ACTIVATION_CODE |

Web screens: /login (includes registration, embedded forgot password, Google/Facebook OAuth), /verification, /reactivate-account.

Mobile screens: Landing, Login, Register, Terms, ForgotPassword, ResetPassword, Activate.

3.2 Authenticated users (/api/v1/users)

| Method | Route | Parameters | Notes / errors |
|---|---|---|---|
| POST | /change-password | current, new, confirmation | 400 PASSWORD_MISMATCH, INVALID_CURRENT_PASSWORD, PASSWORD_RECENTLY_USED |
| POST | /oauth/link | provider + code | 400 OAUTH_ALREADY_LINKED, OAUTH_PROVIDER_TAKEN |
| POST | /organizer-request | multipart: document, optional documentType | 400 ALREADY_ORGANIZER, PETITION_ALREADY_PENDING, DOCUMENT_READ_ERROR |
| GET | /organizer-petition | — | 200 or 404 without a request |
| DELETE | /me | password | 400 INVALID_PASSWORD, ACCOUNT_ALREADY_INACTIVE, ACCOUNT_DELETED |

Web: /organizer-petition-form, password change and account deactivation from the profile. Mobile: Settings, EditProfile; there is no organizer request flow for the user (there are admin screens).

3.3 Administration (/api/v1/admin) — ADMIN role

| Method | Route | Parameters | Errors |
|---|---|---|---|
| GET | /organizer-requests | — | 401/403 |
| PUT | /organizer- requests/{id}/approve | — | 400 PETITION_NOT_PENDING; 404 |
| PUT | /organizer- requests/{id}/reject | — | same |
| GET | /organizer- requests/{id}/document | — | 404 PETITION_NOT_FOUND, FILE_NOT_FOUND |
| GET | /events | optional status query | — |
| PATCH | /events/{eventId}/status | newStatus, reason (mandatory when rejecting) | see admin transitions |

Web: /admin-panel, /admin-events. Mobile: OrganizerRequests, OrganizerRequestDetail.

3.4 Profile (/api/v1/profiles)

GET by id or by userId is public according to SecurityConfig. POST/PUT require authentication.

| Method | Route | Body | Errors |
|---|---|---|---|
| POST | / | userId, fullName (max. 100), optional storedFileId | 201; 409 profile already exists; 400 name/bio |
| PUT | /{profileId} | cityId, storedFileId, fullName (max. 30), bio (max. 255) | 400 BIO_INAPPROPRIATE_LANGUAGE, INVALID_NAME |
| GET | /{profileId} | — | 404 |
| GET | /user/{userId} | — | 404 |

Web: /profile, /complete-profile. Mobile: Perfil, EditProfile.

3.5 Events (/api/v1/events)

Public (GET): /{id}, /public, /public/city/{cityId}, /public/category/{categoryId}, /public/date-range?from&to (ISO date), /status/{status}.

Organizer: POST create, PUT/DELETE/PATCH .../status. GET /user/{userId} authenticated.

Create body: eventName, description, siteId, startDate, finishDate, isPublic (default true), availableSeats (1–100000), categoryId.

Business errors: EVENT_DATES_REQUIRED, EVENT_START_DATE_IN_PAST, EVENT_START_DATE_TOO_FAR (more than 2 years), EVENT_END_BEFORE_START, EVENT_ALREADY_EXISTS (same name+date+site), CATEGORY_NOT_FOUND_OR_INACTIVE, SEATS_EXCEED_CAPACITY, EVENT_ACCESS_DENIED, EVENT_DELETE_NOT_ALLOWED, EVENT_INVALID_STATUS_TRANSITION, EVENT_PUBLISH_MEDIA_COUNT_INVALID (3–9 images), EVENT_SECTIONS_REQUIRED, EVENT_COMPLETE_TOO_EARLY, INVALID_DATE_RANGE.

Web: / landing, /events, /events/:eventId, /events/create, /events/manage.

Mobile: Inicio, Eventos, EventDetail.

3.6 Media, layout, ratings, comments

| Method | Route | Who | Notes |
|---|---|---|---|
| POST | /events/{eventId}/media | ORGANIZER/ADMIN | multipart; 400 EVENT_UPDATE_NOT_ALLOWED, EVENT_MEDIA_READ_ERROR; 422 image policy |
| GET | /events/{eventId}/media | public | — |
| GET/PUT | /events/{eventId}/layout | public GET; authenticated PUT | PUT: owner; 400 EVENT_LAYOUT_EDIT_NOT_ALLOWED, SEAT_REGENERATION_CONFLICT, LAYOUT_PARSING_ERROR |
| POST | /events/{eventId}/ratings | authenticated | mandatory comment max. 500; optional rating 1–5 |
| GET | /events/{eventId}/ratings | public | — |
| POST/GET | /ratings/{ratingId}/replies | authenticated POST; public GET | — |

Ratings: only PUBLISHED or COMPLETED and public events. One numeric rating per user (the rest are comments). The organizer does not leave a rating. Antispam: 1 comment every 10 s. Codes: EVENT_RATING_NOT_ALLOWED, COMMENT_RATE_LIMITED, COMMENT_BLANK, COMMENT_TOO_LONG.

Web: /events/:eventId/layout (ORGANIZER/ADMIN).

3.7 Categories

GET /categories, /active, /root, /{id}, /{id}/subcategories public.

POST/PUT/activate/deactivate/DELETE: ADMIN.

/category-events: public GET; POST/DELETE ORGANIZER or ADMIN.

Error: CATEGORY_NAME_ALREADY_EXISTS.

3.8 Geolocation (/api/v1/geolocation) — public GETs

Departments, cities, sites by city/department, site by id, nearby (latitude, longitude, radiusKm).

POST/PUT sites: ADMIN or ORGANIZER. Create: cityId, name (150), address (200), capacity &gt; 0, lat [- 90,90], lon [-180,180]. Error 409 duplicate site.

3.9 Sections and seats

| Method | Route | Auth | Body / notes |
|---|---|---|---|
| GET | /section-types | public | — |
| POST | /section-types | authenticated (admin in practice) | unique name; SECTION_TYPE_ALREADY_EXISTS |
| GET | /event- sections/event/{eventId} | public | — |
| POST/PUT/DELETE | /event-sections | ORGANIZER/ADMIN | capacity ≥ 1, price ≥ 0; EVENT_SECTION_ALREADY_EXISTS |
| GET | /seat-blocks/section/{id} | public | — |
| POST/DELETE | /seat-blocks | ORGANIZER/ADMIN | SEAT_BLOCK_ALREADY_EXISTS |
| GET | /seats/block/{id}, /seats/section/{id}, /seats/{id}/log | public | — |
| POST/PATCH/DELETE | /seats | ORGANIZER/ADMIN | SEAT_CODE_ALREADY_EXISTS, SEAT_STATUS_UNCHANGED |
| POST | /seats/{seatId}/reserve | authenticated | 10 min TTL; SEAT_NOT_AVAILABLE |
| POST | /seats/{seatId}/release | authenticated | owner or ADMIN; SEAT_NOT_RESERVED, UNAUTHORIZED_RELEASE |

Seat statuses: AVAILABLE, RESERVED, SOLD, COURTESY. Types: regular and courtesy. Seat changes are published by WebSocket /topic/events/{eventId}/seats. WS handshake on /ws/** with JWT.

3.10 Orders and tickets

| Method | Route | Auth | Body | Errors |
|---|---|---|---|---|
| POST | /orders | authenticated | eventId, seatIds (min. 1) | seat not reserved by the user, expired reservation, nonexistent seat → 400 |
| GET | /orders/{orderId} | authenticated | — | 404 |
| GET | /orders/{orderId}/tickets | authenticated | — | 404 |
| POST | /orders/{orderId}/cancel | authenticated | — | 409 if it is not in DRAFT or PAYMENT_PENDING |
| GET | /tickets/{ticketId} | authenticated | — | 404 |
| GET | /tickets/user/{userId} | authenticated | does not verify that it is the same user | — |
| POST | /tickets/{ticketId}/checkin | authenticated | validatedBy | 400 if not PAID, expired or already used |

There is no ORGANIZER @PreAuthorize on check-in: any authenticated user who knows the id can try to validate. There is no scanner UI.

3.11 Payments (/api/v1/payments) and webhook

| Method | Route | Auth | Body | Response |
|---|---|---|---|---|
| POST | /payments | authenticated | orderId, optional paymentMethod (default QR), applyWalletCredit | 201 without the ApiResponse envelope; 400/422 if the gateway or the balance fails |
| GET | /payments/{id} | authenticated | — | 200 PaymentResponse |
| POST | /payments/{id}/refund | ADMIN or ORGANIZER | reason (mandatory, max. 500) | 200; only if the payment is APPROVED |
| POST | /webhooks/payment | public + X-Signature HMAC | raw JSON | 200; 401 invalid signature; 500 processing error |

Payment methods: CARD, PSE, NEQUI, CASH, QR.

Web: /checkout, /checkout/pending/:paymentId, /checkout/confirmed/:paymentId.

Mobile: Checkout, PaymentPending.

3.12 Wallet (/api/v1/wallet)

GET /me and /me/transactions: owner. 404 if there is no wallet.

POST /credit and /adjust: ADMIN. A positive adjustment adds, a negative one subtracts; it does not allow a negative balance. 422 InsufficientWalletBalance.

Web: /wallet. Mobile: there is no wallet screen.

3.13 Notifications (/api/v1/notifications)

GET /me?page&size&unreadOnly (page 0, size 20). GET /me/unread-count. PATCH /{notificationUserId}/read. PATCH /me/read-all. Only the authenticated user.

Web: /notifications and bell. Mobile: there is no dedicated inbox.

3.14 Themes (/api/v1/themes)

GET list: public. POST activate, GET my-active, PUT customize, DELETE customize/{property}, GET log: authenticated. Themes: light, dark, purple, blue.

3.15 Languages

GET /languages and /{id}: public (active ones). Admin: list all, create, update, activate/deactivate, set- default. Errors: LANGUAGE_CODE_EXISTS, CANNOT_DEACTIVATE_DEFAULT_LANGUAGE, LANGUAGE_ALREADY_ACTIVE/INACTIVE, LANGUAGE_NOT_ACTIVE, LANGUAGE_ALREADY_DEFAULT.

Translation: /api/admin/translations/request (entityType, entityId, sourceLanguageCode), jobs by entity, pending jobs (the global list returns an empty list: TODO in the repository). Provider: LibreTranslate.

3.16 Storage (/api/v1/storage)

Marked as public in SecurityConfig (internally the upload expects a user). POST /upload multipart. GET file, by owner, URL. DELETE. Errors: FILE_CATEGORY_NOT_FOUND, INVALID_FILE_EXTENSION, FILE_TOO_LARGE, UPLOAD_FAILED, S3_*, 422 inappropriate image. Global multipart: 10 MB file / 12 MB request.

3.17 Other web screens

/nosotros, /terminos-de-uso, /privacidad. Forgot password is not a route of its own. There is a ChangePassword.jsx and a layout demo, not exposed as main routes.

## 4. Business rules and validations

Account

Email only @gmail.com. Password: minimum 8, uppercase, lowercase, digit and special character. Name: 2 words, ≥3 letters each, maximum 30 characters, without numbers or symbols. Activation by email code. 5 failed attempts in 15 minutes lock the account (today 1 minute; TODO go back to 30). Access JWT 15 min, refresh 7 days. Password history prevents reusing recent ones. Recovery and reactivation do not reveal whether the email exists.

Event

Mandatory dates; start today or in the future; start ≤ 2 years; end ≥ start. Maximum attendance 1–100000 and it cannot exceed the capacity of the site. Unique (name + start date + site). Active category. Media 3–9 to send for review / publish. At least one section with seats. Complete only on the day after finishDate. Cancelling a published event does not revert tickets automatically (the UI warns about it: separate refund). Editing of layout and media restricted according to status (not under review). Regenerating seats conflicts if there are reservations/sales (SEAT_REGENERATION_CONFLICT).

Seats / stock

Temporary reservation of 10 min; afterwards it goes back to AVAILABLE. The order requires a valid reservation by the same user. Price = sum of section prices. When an order is cancelled (DRAFT or PAYMENT_PENDING), seats go to AVAILABLE. Paid: seats SOLD.

Event statuses

DRAFT, PENDING_REVIEW, PUBLISHED, REJECTED, CANCELLED, COMPLETED.

Organizer: DRAFT→PENDING_REVIEW; PENDING_REVIEW→DRAFT; REJECTED→DRAFT; PUBLISHED→CANCELLED or COMPLETED.

Admin: PENDING_REVIEW→PUBLISHED or REJECTED (mandatory reason); PUBLISHED→CANCELLED or COMPLETED. Nothing is published from DRAFT.

Order statuses

DRAFT → PAYMENT_PENDING or CANCELLED. PAYMENT_PENDING → PAID or CANCELLED. PAID → USED or REFUNDED. CANCELLED, REFUNDED, USED are terminal. Illegal transition: 409.

Ticket statuses

PENDING, PROCESSING, PAID, REFUNDED, USED, CANCELLED. Check-in: status PAID, not expired, without a previous check-in → USED.

Payment statuses

PENDING → APPROVED, REJECTED or ERROR. APPROVED → REFUNDED. The rest are terminal. Refund: REQUESTED, APPROVED, PROCESSED, FAILED. Wallet-only is closed locally; with the gateway it waits for the payment.refunded webhook.

Wallet

CREDIT / REVERSAL add; PAYMENT subtracts; ADJUSTMENT ±. Payment: without wallet, mixed (reservation + gateway) or 100% wallet. If the gateway fails, rollback of the reservation.

Payments

Currency COP. applyWalletCredit default false.

## 5. Roles and permissions

Roles in the JWT: USER, ORGANIZER, ADMIN. Anonymous on the web: catalogue, detail, categories, layout/seats for consultation, active themes and languages.

| Capability | Anonymous | USER | ORGANIZER | ADMIN |
|---|---|---|---|---|
| View public events | Yes | Yes | Yes | Yes |
| Buy / reserve / checkout / wallet (consultation) | No | Yes | Yes | Yes |
| Request to become an organizer | No | Yes | No (already is one) | — |
| Create/edit/delete their own events, layout, media, sections, seats | No | No | Yes (owner) | Layout/media/sections/seats yes; the admin changes the status of any event |
| Send for review / cancel published | No | No | Yes (their own) | Publish/reject/cancel any |
| Categories CRUD | No | No | No | Yes |
| Create sites | No | No | Yes | Yes |
| Approve organizers | No | No | No | Yes |
| Refund | No | No | Yes (endpoint) | Yes |
| Credit/adjust wallet | No | No | No | Yes |
| Languages and translation jobs | Consultation | Consultation | Consultation | CRUD / request |
| Own themes | No | Yes | Yes | Yes |

The web protects routes with ProtectedRoute and localStorage.role. Mobile: Inicio/Eventos/Perfil tabs; request admin in a stack.

There is no STAFF role. Check-in is not restricted to the organizer in security.

## 6. End-to-end flows

Registration / login

Gmail registration → activation email (or dev GET) → /activate or Verification screen → login → JWT. Google/Facebook OAuth: web 302 to /login?oauth=true&token=...; mobile JSON. If the OAuth name does not meet the rules → needsOnboarding → /complete-profile. 5 failures → short lockout. INACTIVE account → reactivate. Logout revokes the session; other tabs listen to storage and go to login. Access 401 → refresh; failed refresh → logout.

Create event

USER requests to be an organizer (PDF) → ADMIN approves. ORGANIZER: wizard /events/create (data, site, media) → DRAFT → layout editor (sections, blocks, seats, prices) → 3–9 photos → PENDING_REVIEW. ADMIN in /admin-events publishes or rejects. Published, it appears in /events and on mobile. The organizer can withdraw it to DRAFT, cancel it when published or complete it on the next day.

Buy a ticket and pay

PUBLISHED event → choose seats → RESERVED 10 min (WS) → POST order (DRAFT, tickets PENDING, QR generated) → POST payment. Without wallet: sandbox gateway, order PAYMENT_PENDING. With partial balance: wallet reservation + gateway. Total balance: payment APPROVED immediately. HMAC webhook approves/rejects: seats SOLD, tickets PAID, or the stock is released. UI: pending until confirmed.

Entry validation

PAID ticket + QR in the domain. POST check-in with validatedBy. There is no reader in the clients: it has to be tested through the API.

Cancellation / refund

Cancel order only DRAFT/PAYMENT_PENDING: tickets CANCELLED, seats AVAILABLE. Refund of an APPROVED payment (ADMIN/ORGANIZER + reason). Wallet-only: local closure (payment/order/tickets REFUNDED, credit returned). Gateway: webhook. Cancelling the event does not trigger an automatic refund.

## 7. External integrations

| System | Real use in the code |
|---|---|
| PostgreSQL 17 | Persistence; Liquibase; ddl-auto: validate |
| MinIO (S3 API) | Images, request documents, avatars; public/presigned URLs |
| Gmail SMTP | Activation, recovery, reactivation, email notifications |
| JWT + refresh | Own issuance; BCrypt factor 12 |
| OAuth2 | Google and Facebook (authorization code); GSI ID token |
| Gateway | fake-payment-gateway (port 4001); HMAC webhook. The README mentions Wompi; there is no active Wompi client |
| LibreTranslate | Asynchronous translations (3 retries, 10 min timeout) |
| Moderation | Local NSFW service + Sightengine (gore/nudity/weapon) |
| Redis / GitHub Actions / SonarQube Cloud / K8s | DevOps pipeline, not business logic |
| Email + in-app + WebSocket | Notifications; native push does not appear implemented as FCM/APNs |
| OpenStreetMap / geocoding | Web client for the map of sites |

Swagger: /swagger-ui, /api-docs. Public Actuator.

## 8. Errors and edge cases already covered

- User enumeration avoided in recover and reactivate-request.
- OAuth open redirect: whitelist of frontend_redirect_uri.
- Concurrent refresh on the web (a single promise).
- Logout across tabs.
- Expired seat reservation when creating the order.
- Order/payment state machine (409).
- Transactional rollback if the gateway fails with wallet credit.
- Wallet-only refund vs webhook.
- Lockout with automatic unlocking when it expires.
- Bio with a list of forbidden words and leetspeak normalization.
- Images rejected by NSFW/Sightengine (422).
- An event with an expired date cannot be sent for review or published.
- The admin does not publish from DRAFT.
- Completing an event too early.
- Single rating; organizer without a rating; rate limit 10 s.
- Single-use recovery code.
- The wallet is not left negative.
- Unique event constraint and date check in the DB.

Edge gaps to take into account when designing negative tests: GET tickets by another user's userId; cancel order without checking the owner; check-in without a staff role; storage in permitAll; /dev/activate-code endpoint; 1-minute lockout.

## 9. Pending or incomplete (impact on the test plan)

- README: Wompi, FR, microservices/API Gateway vs code: sandbox gateway, languages ES/EN/PT/JA, monolith.
- Frontend “will be integrated progressively”: web and mobile exist, but they do not cover the whole backend.
- No QR validation / check-in UI.
- Mobile without creating events, layout, wallet, in-app notifications, refund.
- Web without its own forgot password route; the terms still say Wompi.
- Translation: global pending jobs empty; TODO for more entities (sites).
- 1-min lockout and security cleanup at each short interval (production TODO).
- Development activation code endpoint.
- Storage public at the filter level.
- Native push (RF16) not evidenced.
- Staff role and QR reader (RF11/RF24) only in the API.
- Comment in RefundStatus: “future phase”; the refund flow is implemented.
- Payments create/get do not use ApiResponse (the client must handle the body differently).
- The refresh httpClient is not yet in all the web services.

With this, cases can be built: happy paths per flow, negatives for each code, authorization by role, seat concurrency, reservation expiry, payment webhook and wallet vs gateway refund. If you want, the next step can be a matrix of test cases (ID, precondition, steps, expected result) based on this inventory.
