---
title: "Test run of 2026-10-24"
lang: en
generated_on: 2026-10-24
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Ejecucion_Pruebas_2026-10-24.md
es_sha256: PENDIENTE_HASH
---
# Test run — Tu Evento

| Field | Value |
|---|---|
| Project | Tu Evento — CapySoft |
| Verified repository | lozano2303/TuEvento |
| Verified branch / commit | `develop` / `2d259e7` |
| Run date | 2026-10-24 |
| Cases run | [Casos_de_Prueba_TuEvento.md](Casos_de_Prueba_TuEvento.md) (151 cases) |
| Status legend | Aprobado (passed) · Fallido (failed) · Bloqueado (blocked, could not be run) |

## 1. Scope

This document records two runs made on 2026-10-24 against commit `2d259e7` of the `develop` branch:

1. The backend automated tests (`./mvnw verify`), with their JaCoCo coverage report.
2. The 151 cases of [Casos_de_Prueba_TuEvento.md](Casos_de_Prueba_TuEvento.md), run against the system started locally. API cases were run with HTTP scripts. Web interface cases were run in headless Chrome with Puppeteer.

The result of each case is in columns K–O of [Casos_de_Prueba_TuEvento.md](Casos_de_Prueba_TuEvento.md). This document describes the environment, the summary, the defects and the limitations.

It is not a test of the cloud deployment: everything ran in an isolated local environment, with test data created for the occasion.

## 2. Run environment

| Component | Version or configuration |
|---|---|
| Backend | `tu-evento-0.0.1-SNAPSHOT.jar` built from `TuEventoBackend/tu-evento` (`2d259e7`), `dev` profile, port 18080 |
| Java / Maven | OpenJDK 21.0.11 / Apache Maven 3.9.14 (project wrapper) |
| Database | PostgreSQL 17.10 (`postgres:17-alpine`), schema created by the Liquibase changesets at startup |
| Cache | Redis 7.4.10 (`redis:7-alpine`) |
| Storage | MinIO `RELEASE.2025-09-07T16-13-09Z`, bucket `tuevento` |
| Payment gateway | `fake-payment-gateway` 1.0.0 from the same repository, with its own PostgreSQL database; webhooks signed with HMAC-SHA256 |
| Email | Mailpit v1.27 as local SMTP server: emails are captured, not sent to real mailboxes |
| Web frontend | `TuEventoFrontend/web` with the Vite 5.4.21 development server, pointing to the test backend |
| Browser | Google Chrome 151 in headless mode, driven with `puppeteer-core` 24.10.0 |

**Isolation.** All services were started on ports different from those in the project's `docker-compose.yml`, with credentials generated only for this run. The team's `.env` file, email accounts, Google and Sightengine keys and development database were not used. The code repository was not modified: the backend, the gateway and the web app were copied to a temporary folder before building them.

**Services not started.** The NSFW classifier (`nsfw-service`), Sightengine, LibreTranslate, real Google login and the mobile app were not started. The cases that depend on them were marked Bloqueado (section 4).

**Techniques used.** To check expirations without waiting days (activation codes, refresh tokens, seat holds), the expiration date was changed directly in the test database. Codes that arrive by email were read from Mailpit or from the test database. Every case where this was done says so in its Remarks column.

## 3. Backend automated tests

Command: `./mvnw -B verify` on a copy of `TuEventoBackend/tu-evento`.

| Result | Value |
|---|---|
| Test classes | 27 |
| Tests | 222 |
| Failures and errors | 0 |
| Skipped | 0 |
| Total test time | 43.4 s |
| Maven result | `BUILD SUCCESS` (exit code 0) |

**Coverage (JaCoCo, `target/site/jacoco/jacoco.csv`):**

| Metric | Covered | Total | Coverage |
|---|---|---|---|
| Lines | 1768 | 11755 | 15.0 % |
| Branches | 381 | 2898 | 13.1 % |
| Instructions | 7650 | 48759 | 15.7 % |
| Methods | 383 | 2070 | 18.5 % |

**Tests per class:**

| Test class | Tests | Failures | Time (s) |
|---|---|---|---|
| `TuEventoApplicationTests` | 1 | 0 | 36.0 |
| `modules.event.application.usecase.AddEventRatingServiceTest` | 28 | 0 | 0.2 |
| `modules.event.application.usecase.AdminChangeEventStatusUseCaseTest` | 12 | 0 | 0.5 |
| `modules.event.application.usecase.ChangeEventStatusServiceTest` | 14 | 0 | 0.1 |
| `modules.event.application.usecase.DeleteEventRatingServiceTest` | 7 | 0 | 0.0 |
| `modules.event.application.usecase.EditEventRatingServiceTest` | 10 | 0 | 0.4 |
| `modules.event.application.validator.EventDateValidatorTest` | 14 | 0 | 0.0 |
| `modules.event.infrastructure.EventRatingTranslatableContentHandlerTest` | 2 | 0 | 0.4 |
| `modules.event.infrastructure.websocket.EventCommentWebSocketListenerTest` | 5 | 0 | 0.4 |
| `modules.event.infrastructure.websocket.EventRatingDeletedWebSocketListenerTest` | 2 | 0 | 0.0 |
| `modules.language.application.service.TextMaskingServiceTest` | 17 | 0 | 0.0 |
| `modules.language.application.service.TranslationProcessorTest` | 4 | 0 | 0.5 |
| `modules.language.application.service.TranslationServiceTest` | 5 | 0 | 0.1 |
| `modules.language.domain.model.TranslationJobTest` | 7 | 0 | 0.0 |
| `modules.notification.application.NotificationMessageFactoryTest` | 21 | 0 | 0.2 |
| `modules.notification.application.SendNotificationUseCaseIdempotencyTest` | 2 | 0 | 0.6 |
| `modules.notification.infrastructure.messaging.EventStatusChangedListenerTest` | 4 | 0 | 0.0 |
| `modules.notification.infrastructure.messaging.OrganizerRoleRevokedListenerTest` | 4 | 0 | 0.1 |
| `modules.profile.infrastructure.ProfileTranslatableContentHandlerTest` | 1 | 0 | 0.3 |
| `modules.security.application.ActivateAccountUseCaseTest` | 3 | 0 | 0.4 |
| `modules.security.application.usecase.ApproveOrganizerRequestUseCaseTest` | 9 | 0 | 0.3 |
| `modules.security.application.usecase.GetOrganizersUseCaseTest` | 8 | 0 | 0.4 |
| `modules.security.application.usecase.OauthLoginUseCaseOnboardingTest` | 6 | 0 | 0.6 |
| `modules.security.application.usecase.RevokeOrganizerRoleUseCaseTest` | 6 | 0 | 0.0 |
| `modules.security.infrastructure.JavaMailEmailNotificationTest` | 4 | 0 | 0.3 |
| `modules.security.interfaces.rest.AdminControllerTest` | 7 | 0 | 1.3 |
| `shared.domain.valueobject.ValidationUtilsTest` | 19 | 0 | 0.3 |

Class names omit the `com.capysoft.tuevento.` prefix. The tests mainly cover events, ratings, translation, notifications and security. There are no automated tests for payments, tickets, seats, wallet or storage, which account for most of the defects in section 5.

## 4. Test case summary

| Module | Total | Passed | Failed | Blocked | % Passed |
|---|---|---|---|---|---|
| Authentication | 32 | 25 | 5 | 2 | 78.1 % |
| Users | 9 | 9 | 0 | 0 | 100.0 % |
| Administration | 6 | 5 | 1 | 0 | 83.3 % |
| Profile | 5 | 5 | 0 | 0 | 100.0 % |
| Events | 21 | 19 | 2 | 0 | 90.5 % |
| Media and layout | 7 | 5 | 1 | 1 | 71.4 % |
| Ratings and comments | 6 | 5 | 1 | 0 | 83.3 % |
| Categories and sites | 7 | 7 | 0 | 0 | 100.0 % |
| Sections and seats | 9 | 8 | 1 | 0 | 88.9 % |
| Orders and tickets | 12 | 9 | 3 | 0 | 75.0 % |
| Payments | 16 | 15 | 1 | 0 | 93.8 % |
| Wallet | 5 | 5 | 0 | 0 | 100.0 % |
| Notifications | 4 | 4 | 0 | 0 | 100.0 % |
| Themes and languages | 6 | 5 | 0 | 1 | 83.3 % |
| Security and storage | 6 | 2 | 3 | 1 | 33.3 % |
| **Total** | **151** | **128** | **18** | **5** | **84.8 %** |

**Blocked cases (5):**

| Case | Reason |
|---|---|
| CP-AUT-27 | Requires a real Google account and valid OAuth credentials. |
| CP-AUT-30 | Depends on the real Google login. |
| CP-MED-02 | Neither the NSFW service nor Sightengine was configured, and no inappropriate images were used. According to `NsfwClientAdapter` and `SightengineAdapter`, without configuration moderation lets any image through. |
| CP-TEM-05 | LibreTranslate was not running: the backend accepted the request, but the translation cannot complete. |
| CP-SEG-06 | Requires running the mobile app (Expo) on a device or emulator. |

**Cases run through the API instead of the screen.** CP-USR-05, CP-MED-07 and CP-EVT-13 describe web steps, but they were run by calling the same API the screen uses. The web cases that were actually walked through in the browser are CP-AUT-21, CP-AUT-22, CP-PAG-16 and CP-SEG-05.

## 5. Defects found

Severity follows the table in section 11 of the [test plan](../Plan_Pruebas.md).

| # | Case | Severity | Defect | Evidence in the code |
|---|---|---|---|---|
| D-01 | CP-SIL-05 | Critical | Two users who reserve the same seat at the same time both get «Silla reservada». In the DB only the last one remains as `reserved_by`. Reproduced in 5 of 5 attempts. | `modules/seat/application/usecase/SeatReservationService.java` (`reserveSeat` reads the status and then saves, with no row lock or version control) |
| D-02 | CP-ORD-07 | High | Any authenticated user can cancel another user's order. Known gap, confirmed. | `modules/ticket/interfaces/rest/OrderController.java` (`/{orderId}/cancel`) |
| D-03 | CP-ORD-08 | High | `GET /tickets/user/{userId}` returns any user's tickets. Known gap, confirmed. | `modules/ticket/interfaces/rest/TicketController.java` |
| D-04 | CP-ORD-12 | High | Any USER can check in someone else's ticket, which becomes USED. Known gap, confirmed. | `TicketController.java`, `/{ticketId}/checkin` without `@PreAuthorize` |
| D-05 | CP-SEG-02 | High | `POST /storage/upload` does not require a token. Without a user it fails when saving, but the 400 response includes the internal SQL statement. | `shared/infrastructure/security/SecurityConfig.java`, `modules/storage/interfaces/rest/StorageController.java` |
| D-06 | CP-SEG-03 | High | `GET /auth/dev/activate-code/{email}` returns the activation code of any account without authentication. It is not restricted to a profile. | `modules/security/interfaces/rest/AuthController.java:290` |
| D-07 | CP-AUT-23 | Medium | `POST /auth/recover-password` returns 404 «This email is not registered in the system» for unregistered emails, which allows user enumeration. | Password recovery use case |
| D-08 | CP-AUT-16 | Medium | When the failed-attempt lock expires, the first correct login returns `ACCOUNT_BLOCKED` although the DB is already ACTIVE. The second attempt works. | `modules/security/application/usecase/LoginUseCase.java` (`checkLockout` and the user re-read) |
| D-09 | CP-AUT-22 | Medium | With an expired access token, the web app sends two `POST /auth/refresh` in parallel. The second fails with the already rotated refresh token and the session is closed. | `services/httpClient.js`, `hooks/useTokenRefresh.js` and `context/NotificationContext.jsx` (three refresh implementations) |
| D-10 | CP-MED-03 | Medium | An 11 MB file returns 500 «An unexpected error occurred»: `MaxUploadSizeExceededException` has no handler. | `shared/infrastructure/advice/GlobalExceptionHandler.java` |
| D-11 | CP-PAG-13 | Medium | A refund reason of exactly 500 characters passes validation, but the INSERT into `payment_log.reason` (varchar 500) fails and returns 500. | Refund use case and `payment_log.reason` column |
| D-12 | CP-SEG-04 | Medium | Swagger UI (`/swagger-ui`) and the OpenAPI specification (`/api-docs`) are public. They are also enabled in `application-prod.yml` («Cambiar a false cuando el proyecto pase a producción real»). Actuator only exposes `health`. | `application-dev.yml`, `application-prod.yml` |
| D-13 | CP-AUT-14, CP-AUT-19, CP-ADM-04 | Low | 404 responses do not include the `code` field expected by the cases (`USER_NOT_FOUND`, `PETITION_NOT_FOUND`), and refresh after logout returns 404 instead of `REFRESH_TOKEN_REVOKED`. The behavior is safe; only the format differs. | `GlobalExceptionHandler.java` (`NotFoundException` handling) |
| D-14 | CP-EVT-05, CP-RAT-05 | Low | Bean Validation checks (`@NotNull`, `@NotBlank`, `@Size`) respond before the business rules, so the codes `EVENT_DATES_REQUIRED`, `COMMENT_BLANK` and `COMMENT_TOO_LONG` do not appear. The limits are enforced. | DTOs `CreateEventRequest`, `AddEventRatingRequest` |

**Case with an outdated expected result.** CP-EVT-17 expected tickets not to be reverted when a published event is cancelled. In the current code, `EventCancelledListener` (`payment` module) automatically refunds every APPROVED payment of the event. The paid ticket became REFUNDED and the balance returned to the wallet. It was recorded as Fallido because it does not match the expectation, but what needs fixing is the case, not the system.

**Other findings outside the cases:**

| # | Severity | Finding |
|---|---|---|
| H-01 | Medium | The backend accepts any special character in the password (`ValidationUtils.PASSWORD_PATTERN`: `[^a-zA-Z0-9]`), but the web forms only accept `@$!%*?&`. An account created from the API or the mobile app with, for example, `#` in the password cannot log in from the web. |
| H-02 | Medium | The API allows reserving seats of events that are still DRAFT (confirmed in CP-MED-05). |
| H-03 | Low | If a required request parameter is missing (`MissingServletRequestParameterException`), the backend returns 500 instead of 400. |
| H-04 | Low | In the web wallet, a credit made by the administrator with the reason «Bono de bienvenida» shows up as «Crédito por cancelación», with «ID: N/A». |
| H-05 | Low | On the pending payment screen, the «Evento» field is empty. When the payment is approved, the confirmation is shown on the same `/checkout/pending/:id` route, without going through `/checkout/confirmed/:id`. |
| H-06 | Low | The web app switches the interface language to the profile's preferred language a few seconds after loading, even if the user chose another one in the selector. |

## 6. Evidence

Evidence for the web interface cases (headless Chrome, 1440 × 900):

| Case | Evidence |
|---|---|
| CP-AUT-21 | Tab B redirected to `/login` after logout in tab A: [`aut21_pestana_b.png`](../../../_assets/07_Pruebas/Ejecucion_2026-10-24/aut21_pestana_b.png) |
| CP-AUT-22 | Session closed after the duplicate refresh: [`aut22_wallet.png`](../../../_assets/07_Pruebas/Ejecucion_2026-10-24/aut22_wallet.png) |
| CP-PAG-16 | Pending payment and approved payment: [`05_pago_pendiente.png`](../../../_assets/09_Manuales/Manual_de_usuario/Manual_web/capturas_2026-10-24/en/05_pago_pendiente.png) and [`06_pago_confirmado.png`](../../../_assets/09_Manuales/Manual_de_usuario/Manual_web/capturas_2026-10-24/en/06_pago_confirmado.png) |

The full web purchase walkthrough, with screenshots in Spanish and English, is in the [user manual](../../12_Manual_Usuario.md#ticket-purchase).

The run logs (Maven output, backend and gateway logs, and HTTP responses) stayed in the run's temporary folder and are not versioned.

## 7. Contradictions found

| # | Statement | Source A | Source B | What is correct according to the evidence | Suggested action |
|---|---|---|---|---|---|
| 1 | When an event is cancelled, tickets are not reverted automatically | Case CP-EVT-17 in [Casos_de_Prueba_TuEvento.md](Casos_de_Prueba_TuEvento.md) | `modules/payment/infrastructure/messaging/EventCancelledListener.java` | The system automatically refunds approved payments | Update the expected result of CP-EVT-17 |
| 2 | The check-in `validatedBy` is the validator's name | Input data of CP-ORD-09 | `CheckinTicketRequest.validatedBy` (`Long`) | It is the numeric ID of the validating user | Fix the case input data |
| 3 | A profile is created with `POST /profiles` | CP-PRF-01 | Run: registration already creates the profile | The profile is created on registration; `POST /profiles` returns 409 | Adjust the precondition of CP-PRF-01 |
| 4 | The case activation code is «000000» | CP-AUT-08 | `ActivateAccountRequest` (8 characters) | The code has 8 characters | Use an 8-character code in the case |
| 5 | Special characters allowed in the password | `ValidationUtils.java` (any) | Web forms (`@$!%*?&`) | The two rules differ (H-01) | Unify the rule in backend, web and mobile |

## 8. Pending verification in the code repository

| Item | How to resolve it | Who to ask |
|---|---|---|
| CP-AUT-27 and CP-AUT-30 (Google OAuth) | Repeat them with real Google credentials in an environment with the authorized domain | Team (owner of the Google Cloud console) |
| CP-MED-02 (image moderation) | Start `nsfw-service` and configure Sightengine with test keys | Team |
| CP-TEM-05 (machine translation) | Start the `libretranslate` service from `docker-compose.yml` and repeat the case | Team |
| CP-SEG-06 (mobile flow) | Run the `TuEventoFrontend/movil` app with Expo on an emulator | Team |
| Behavior in the real deployment | Repeat the security cases (CP-SEG-02 to CP-SEG-04) against the deployed URL with the `prod` profile | Team (deployment URL) |
| CP-AUT-22 result with the production build | Repeat with `npm run build` + `vite preview`, without React development mode | Team |
