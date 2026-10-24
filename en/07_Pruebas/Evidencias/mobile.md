---
id: TE-0154
title: "mobile"
lang: en
source: 06_Pruebas/mobile.pdf
source_sha256: 97036e5b861058479eddc5cdffabffe99802e9785189ba8f8e4cc038bb863229
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–4: «{n}»."
  - "Tables split across pages joined into a single one: 3→4."
  - "Words split with a hyphen at the end of a line were joined: prin-cipales."
  - "Words split with a line-break hyphen inside cells were joined (without hyphen if a lowercase letter follows; with hyphen and without space if a digit or an uppercase letter follows): Esperado, AUTH-001, registrado, aplicación., Ingresar, válidos., pantalla, AUTH-002, contraseña, incorrectos., mensaje, AUTH-003, campos, Tocar, mensajes, validación, campos, Esperado, AUTH-001, registrado, aplicación., Ingresar, válidos., pantalla, AUTH-002, contraseña, incorrectos., mensaje, AUTH-003, campos, Tocar, mensajes, validación, campos, Esperado, AUTH-004, registrado, Register”., Ingresar, válidos., Ingresar, pantalla, AUTH-005, mensaje, AUTH-006, iniciado, código, mensaje, Esperado, AUTH-004, registrado, Register”., Ingresar, válidos., Ingresar, pantalla, AUTH-005, mensaje, AUTH-006, iniciado, código, mensaje, Esperado, AUTH-007, registrado, ”Forgot, Ingresar, contraseña., AUTH-008, registrado., mensaje, AUTH-009, iniciado, código, mensaje, Esperado, AUTH-007, registrado, ”Forgot, Ingresar, contraseña., AUTH-008, registrado., mensaje, AUTH-009, iniciado, código, mensaje, Esperado, EVENT-001, autenticado, disponibles., EVENT-002, Ingresar, eventos, EVENT-003, Esperado, EVENT-001, autenticado, disponibles., EVENT-002, Ingresar, eventos, EVENT-003, Esperado, EVENT-004, completo, información, EVENT-005, Esperado, EVENT-004, completo, información, EVENT-005, Esperado, PROF-001, autenticado, PROF-002, Esperado, PROF-001, autenticado, PROF-002, Esperado, autenticado, Escanear, válido., mostrar, mensaje, permiso., mensaje, Esperado, autenticado, Escanear, válido., mostrar, mensaje, permiso., mensaje."
  - "70 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 97.05%, order 98.50%; missing {} (explained above)."
  - "Differences in the check explained: the «extra» 001-006 are the numbers of the identifiers AUTH-001… which in the original are alone on a line of the cell; the reference (pdftotext) discards numbers that are alone on a line."
  - "Translation: the interface texts in quotation marks (”Login”, Register”, ”Forgot Password”) are already in English and are kept as in the original; the names of the tabs are translated with the Spanish name in parentheses."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/mobile.md
es_sha256: 0bb5e22b0056e59add10f0e09d6388f4721d1339d31960b24507198817582b8c
---
> **Historical document.** These tests are dated October 6, 2025 and belong to the mobile app of the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (folder `TuEventoFrontend (Mobile)`). The mobile app of the current repository (`lozano2303/TuEvento`) was added from March 24, 2026 onwards. It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# Test Manual - TuEvento Mobile

Development Team

6 October 2025

## 1. Introduction

This test manual describes the test cases for the TuEvento mobile application. The application allows users to authenticate, explore events, view event details, manage their profile and scan QR codes.

The purpose of this manual is to ensure that all the main features work correctly through manual tests.

## 2. Authentication Tests

### 2.1. Login

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| AUTH-001 | Successful login | User registered in the system | 1. Open the application. 2. Enter a valid email and password. 3. Tap the ”Login” button. | Navigate to the main screen (MainTabs). |
| AUTH-002 | Invalid credentials | None | 1. Enter an incorrect email and password. 2. Tap the ”Login” button. | Show an authentication error message. |
| AUTH-003 | Empty fields | None | 1. Leave the email and password fields empty. 2. Tap the ”Login” button. | Show validation messages for required fields. |

### 2.2. User Registration

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| AUTH-004 | Successful registration | Email not registered | 1. Tap Register”. 2. Enter valid data. 3. Tap - egister”. 4. Enter the verification code. 5. Confirm. | Navigate to the login or main screen. |
| AUTH-005 | Email already registered | Existing email | 1. Enter an existing email. 2. Complete the registration. | Show an error message. |
| AUTH-006 | Invalid verification code | Registration started | 1. Enter an incorrect code. 2. Confirm. | Show an error message. |

### 2.3. Password Recovery

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| AUTH-007 | Successful recovery | Email registered | 1. Tap ”Forgot Password”. 2. Enter the email. 3. Enter the code. 4. New password. 5. Confirm. | Navigate to login. |
| AUTH-008 | Email not registered | Invalid email | 1. Enter an unregistered email. 2. Send. | Show an error message. |
| AUTH-009 | Invalid code | Process started | 1. Enter an incorrect code. | Show an error message. |

## 3. Event Tests

### 3.1. Event List

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| EVENT-001 | Load event list | Authenticated user | 1. Navigate to the Home (Inicio) tab. | Show the list of available events. |
| EVENT-002 | Filter events | List loaded | 1. Use the search bar. 2. Enter a term. | Show filtered events. |
| EVENT-003 | Navigate to detail | Event visible | 1. Tap on an event. | Open the detail screen. |

### 3.2. Event Detail

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| EVENT-004 | Show complete detail | Navigated from list | 1. View the screen. | Show the event information (title, description, date, etc.). |
| EVENT-005 | Return to list | In detail | 1. Use the back button. | Return to the event list. |

## 4. Profile Tests and Other Features

### 4.1. Profile Screen

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| PROF-001 | Show profile information | Authenticated user | 1. Navigate to the Profile (Perfil) tab. | Show the user's data (name, email, etc.). |
| PROF-002 | Log out | In profile | 1. Tap the logout button. | Log out and return to login. |

### 4.2. QR Reader

| **ID** | **Description** | **Preconditions** | **Steps** | **Expected Result** |
|---|---|---|---|---|
| QR-001 | Scan valid QR | Authenticated user | 1. Navigate to the QR Reader (Lector QR) tab. 2. Allow the camera. 3. Scan a valid QR. | Process the code and show the result. |
| QR-002 | Scan invalid QR | Camera active | 1. Scan an invalid code. | Show an error message. |
| QR-003 | Deny camera permission | First time | 1. Deny the permission. | Show a message to enable the camera. |
