---
id: TE-0152
title: "Casos_de_Prueba_TuEvento"
lang: en
source: 06_Pruebas/Casos_de_Prueba_TuEvento.xlsx
source_sha256: 0cdad68243cc439bb95e6f354aa5a25ba754a54a4f111a0028815586c2871737
conversion: "openpyxl 3.1.5 (data_only + formulas); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Visual formatting (colours, borders, widths, fonts and conditional formatting styles) is not kept."
  - "Merged cells are listed but not reproduced as a single cell."
  - "The formula values are the ones cached by Excel; they were not recalculated."
  - "Translation: the sheet names (Resumen, Casos de prueba) and the values of column L (Estado: Pendiente, Aprobado, Fallido, Bloqueado) are kept in Spanish because the formulas, the data validation list and the conditional formatting of the workbook refer to these literal values; the formulas are kept as in the original."
  - "Translation: the test data (emails, passwords, names, reasons and values) are kept as in the original."
  - "Translation: numbers keep the format of the original (for example, «10.000» with a dot as thousands separator)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Casos_de_Prueba_TuEvento.md
es_sha256: 8740f207bf0f172f047bc428c24d3f6f0d388fa44ac748de9c19e29d141d81e9
---
# Test cases TuEvento

> Conversion of `06_Pruebas/Casos_de_Prueba_TuEvento.xlsx`: 2 sheets (Resumen, Casos de prueba), 102 formulas. The columns are named with the Excel letter and each row with its original number.

## Sheet: Resumen

Used range: `A1:H33` · 33 rows × 8 columns · merged cells: 1

| Row | A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|---|
| 1 | Execution summary — Tu Evento |  |  |  |  |  |  |  |
| 2 | The totals are calculated automatically from the «Casos de prueba» sheet. Only edit the columns Actual result, Status, Date, Owner and Remarks. The status is chosen from the list. |  |  |  |  |  |  |  |
| 4 | Module | Total | Passed | Failed | Blocked | Pending | % Passed |  |
| 5 | Authentication | 32 | 0 | 0 | 0 | 32 | 0.0% |  |
| 6 | Users | 9 | 0 | 0 | 0 | 9 | 0.0% |  |
| 7 | Administration | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 8 | Profile | 5 | 0 | 0 | 0 | 5 | 0.0% |  |
| 9 | Events | 21 | 0 | 0 | 0 | 21 | 0.0% |  |
| 10 | Media and layout | 7 | 0 | 0 | 0 | 7 | 0.0% |  |
| 11 | Ratings and comments | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 12 | Categories and sites | 7 | 0 | 0 | 0 | 7 | 0.0% |  |
| 13 | Sections and seats | 9 | 0 | 0 | 0 | 9 | 0.0% |  |
| 14 | Orders and tickets | 12 | 0 | 0 | 0 | 12 | 0.0% |  |
| 15 | Payments | 16 | 0 | 0 | 0 | 16 | 0.0% |  |
| 16 | Wallet | 5 | 0 | 0 | 0 | 5 | 0.0% |  |
| 17 | Notifications | 4 | 0 | 0 | 0 | 4 | 0.0% |  |
| 18 | Themes and languages | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 19 | Security and storage | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 20 | TOTAL | 151 | 0 | 0 | 0 | 151 | 0.0% |  |
| 22 | By test type |  |  |  |  |  |  |  |
| 23 | Type | Total |  |  |  |  |  |  |
| 24 | Positive | 42 |  |  |  |  |  |  |
| 25 | Negative | 66 |  |  |  |  |  |  |
| 26 | Boundary | 11 |  |  |  |  |  |  |
| 27 | Security | 22 |  |  |  |  |  |  |
| 28 | Concurrency | 2 |  |  |  |  |  |  |
| 29 | Integration | 8 |  |  |  |  |  |  |
| 32 | Cases that verify known gaps (they are expected to fail today) |  |  |  |  |  |  |  |
| 33 | See the Remarks column with the text «Known gap» in the cases sheet. |  |  |  |  |  |  |  |

**Merged cells** (the value appears only in the top-left cell): `A2:H2`


**Formulas of this sheet** (cell · formula · cached value):

| Cell | Formula | Cached value |
|---|---|---|
| B5 | `=COUNTIF('Casos de prueba'!$B:$B,A5)` | 32 |
| C5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Pendiente")` | 32 |
| G5 | `=IF(B5=0,0,C5/B5)` | 0.0% |
| B6 | `=COUNTIF('Casos de prueba'!$B:$B,A6)` | 9 |
| C6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Pendiente")` | 9 |
| G6 | `=IF(B6=0,0,C6/B6)` | 0.0% |
| B7 | `=COUNTIF('Casos de prueba'!$B:$B,A7)` | 6 |
| C7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G7 | `=IF(B7=0,0,C7/B7)` | 0.0% |
| B8 | `=COUNTIF('Casos de prueba'!$B:$B,A8)` | 5 |
| C8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Pendiente")` | 5 |
| G8 | `=IF(B8=0,0,C8/B8)` | 0.0% |
| B9 | `=COUNTIF('Casos de prueba'!$B:$B,A9)` | 21 |
| C9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Pendiente")` | 21 |
| G9 | `=IF(B9=0,0,C9/B9)` | 0.0% |
| B10 | `=COUNTIF('Casos de prueba'!$B:$B,A10)` | 7 |
| C10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Pendiente")` | 7 |
| G10 | `=IF(B10=0,0,C10/B10)` | 0.0% |
| B11 | `=COUNTIF('Casos de prueba'!$B:$B,A11)` | 6 |
| C11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G11 | `=IF(B11=0,0,C11/B11)` | 0.0% |
| B12 | `=COUNTIF('Casos de prueba'!$B:$B,A12)` | 7 |
| C12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Pendiente")` | 7 |
| G12 | `=IF(B12=0,0,C12/B12)` | 0.0% |
| B13 | `=COUNTIF('Casos de prueba'!$B:$B,A13)` | 9 |
| C13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Pendiente")` | 9 |
| G13 | `=IF(B13=0,0,C13/B13)` | 0.0% |
| B14 | `=COUNTIF('Casos de prueba'!$B:$B,A14)` | 12 |
| C14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Pendiente")` | 12 |
| G14 | `=IF(B14=0,0,C14/B14)` | 0.0% |
| B15 | `=COUNTIF('Casos de prueba'!$B:$B,A15)` | 16 |
| C15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Pendiente")` | 16 |
| G15 | `=IF(B15=0,0,C15/B15)` | 0.0% |
| B16 | `=COUNTIF('Casos de prueba'!$B:$B,A16)` | 5 |
| C16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Pendiente")` | 5 |
| G16 | `=IF(B16=0,0,C16/B16)` | 0.0% |
| B17 | `=COUNTIF('Casos de prueba'!$B:$B,A17)` | 4 |
| C17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Pendiente")` | 4 |
| G17 | `=IF(B17=0,0,C17/B17)` | 0.0% |
| B18 | `=COUNTIF('Casos de prueba'!$B:$B,A18)` | 6 |
| C18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G18 | `=IF(B18=0,0,C18/B18)` | 0.0% |
| B19 | `=COUNTIF('Casos de prueba'!$B:$B,A19)` | 6 |
| C19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G19 | `=IF(B19=0,0,C19/B19)` | 0.0% |
| B20 | `=SUM(B5:B19)` | 151 |
| C20 | `=SUM(C5:C19)` | 0 |
| D20 | `=SUM(D5:D19)` | 0 |
| E20 | `=SUM(E5:E19)` | 0 |
| F20 | `=SUM(F5:F19)` | 151 |
| G20 | `=IF(B20=0,0,C20/B20)` | 0.0% |
| B24 | `=COUNTIF('Casos de prueba'!$D:$D,A24)` | 42 |
| B25 | `=COUNTIF('Casos de prueba'!$D:$D,A25)` | 66 |
| B26 | `=COUNTIF('Casos de prueba'!$D:$D,A26)` | 11 |
| B27 | `=COUNTIF('Casos de prueba'!$D:$D,A27)` | 22 |
| B28 | `=COUNTIF('Casos de prueba'!$D:$D,A28)` | 2 |
| B29 | `=COUNTIF('Casos de prueba'!$D:$D,A29)` | 8 |

## Sheet: Casos de prueba

Used range: `A1:O152` · 152 rows × 15 columns · merged cells: 0

| Row | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | ID | Module | Requirement / reference | Type | Priority | Description | Preconditions | Steps | Input data | Expected result | Actual result | Status | Date | Owner | Remarks |
| 2 | CP-AUT-01 | Authentication | 3.1 /register | Positive | High | Successful registration with Gmail and valid data | Email not registered | 1. POST /api/v1/auth/register<br>2. Check the activation email | email: nuevo.usuario@gmail.com<br>password: Clave#2026<br>fullName: Cristofer Lozano | 201. Account created pending activation and email with code sent |  | Pendiente |  |  |  |
| 3 | CP-AUT-02 | Authentication | 3.1 /register | Negative | High | Registration with an email that is not Gmail | None | 1. POST /register with an email from another domain | email: ana@hotmail.com | 400 INVALID_EMAIL |  | Pendiente |  |  |  |
| 4 | CP-AUT-03 | Authentication | 4 Account | Negative | High | Registration with a password that does not meet the policy | None | 1. POST /register with a password without uppercase, digit or special character | password: clave1234 | 400 INVALID_PASSWORD |  | Pendiente |  |  |  |
| 5 | CP-AUT-04 | Authentication | 4 Account | Negative | Medium | Registration with a one-word name or with numbers | None | 1. POST /register with an invalid fullName | fullName: Juan / Ju4n P3r3z | 400 INVALID_NAME |  | Pendiente |  |  |  |
| 6 | CP-AUT-05 | Authentication | 4 Account | Boundary | Medium | Name of 31 characters (maximum limit 30) | None | 1. POST /register with a name of 31 characters | fullName: 31 alphabetic characters in two words | 400 INVALID_NAME. With exactly 30 characters it must be accepted |  | Pendiente |  |  |  |
| 7 | CP-AUT-06 | Authentication | 3.1 /register | Negative | High | Registration with an existing email | User already registered | 1. POST /register with the same email | existing email | 400 EMAIL_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 8 | CP-AUT-07 | Authentication | 3.1 /activate | Positive | High | Account activation with a valid code | User registered without activation | 1. POST /activate with the code from the email<br>2. Log in | email + valid activationCode | 200. The account becomes active and the login works |  | Pendiente |  |  |  |
| 9 | CP-AUT-08 | Authentication | 3.1 /activate | Negative | High | Activation with an incorrect code | User registered without activation | 1. POST /activate with a wrong code | activationCode: 000000 | 400 INVALID_ACTIVATION_CODE |  | Pendiente |  |  |  |
| 10 | CP-AUT-09 | Authentication | 3.1 /activate | Negative | Medium | Activation with an expired code | Code generated and expired | 1. Wait for the expiry<br>2. POST /activate | expired code | 400 ACTIVATION_CODE_EXPIRED |  | Pendiente |  |  |  |
| 11 | CP-AUT-10 | Authentication | 3.1 /activate | Negative | Low | Activate an account that is already active | Active account | 1. POST /activate | email of an active account | 400 ACCOUNT_ALREADY_ACTIVATED |  | Pendiente |  |  |  |
| 12 | CP-AUT-11 | Authentication | 3.1 /resend-activation | Negative | Low | Resend activation to an already activated account | Active account | 1. POST /resend-activation | email of an active account | 400 EMAIL_ALREADY_ACTIVATED |  | Pendiente |  |  |  |
| 13 | CP-AUT-12 | Authentication | 3.1 /login | Positive | High | Successful login | Active account | 1. POST /login with valid credentials | correct email + password | 200 with accessToken, refreshToken, userId, alias and role |  | Pendiente |  |  |  |
| 14 | CP-AUT-13 | Authentication | 3.1 /login | Negative | High | Login with an account not activated | Account registered without activation | 1. POST /login | correct credentials | 400 ACCOUNT_NOT_ACTIVATED |  | Pendiente |  |  |  |
| 15 | CP-AUT-14 | Authentication | 3.1 /login | Negative | Medium | Login with a nonexistent email | None | 1. POST /login | unregistered email | 404 USER_NOT_FOUND |  | Pendiente |  |  |  |
| 16 | CP-AUT-15 | Authentication | 3.1 /login | Negative | High | Login with an incorrect password | Active account | 1. POST /login with a wrong password | incorrect password | 400 INVALID_CREDENTIALS |  | Pendiente |  |  |  |
| 17 | CP-AUT-16 | Authentication | 4 Account | Boundary | High | Lockout after 5 failed attempts in 15 minutes | Active account | 1. Make 5 failed logins in a row<br>2. Try a sixth login with the correct password<br>3. Wait for the lockout time<br>4. Retry | incorrect password x5 | 400 ACCOUNT_LOCKED on the sixth attempt. It is unlocked when the period expires |  | Pendiente |  |  | Today the lockout lasts 1 minute (TODO go back to 30) |
| 18 | CP-AUT-17 | Authentication | 3.1 /login | Negative | Medium | Login with a blocked, deactivated or deleted account | Accounts in each status | 1. POST /login with each account | correct credentials | 400 ACCOUNT_BLOCKED / ACCOUNT_DEACTIVATED / ACCOUNT_DELETED depending on the case |  | Pendiente |  |  |  |
| 19 | CP-AUT-18 | Authentication | 3.1 /refresh | Positive | High | Renew tokens with a valid refresh token | Session started | 1. POST /refresh with the refreshToken | valid refreshToken | 200 with new tokens |  | Pendiente |  |  |  |
| 20 | CP-AUT-19 | Authentication | 3.1 /refresh | Negative | High | Refresh with a token revoked after logout | Logout performed | 1. POST /logout<br>2. POST /refresh with the previous token | revoked refreshToken | 400 REFRESH_TOKEN_REVOKED |  | Pendiente |  |  |  |
| 21 | CP-AUT-20 | Authentication | 3.1 /refresh | Negative | Medium | Refresh with an expired token | Refresh token older than 7 days | 1. POST /refresh | expired refreshToken | 400 REFRESH_TOKEN_EXPIRED |  | Pendiente |  |  |  |
| 22 | CP-AUT-21 | Authentication | 6 Registration/login | Integration | Medium | Logout synchronized across tabs (web) | Two tabs with a session | 1. Log out in tab A<br>2. Observe tab B | — | Tab B redirects to /login |  | Pendiente |  |  |  |
| 23 | CP-AUT-22 | Authentication | 6 Registration/login | Integration | High | Expired access JWT causes an automatic refresh (web) | Session with an expired 15-min access token | 1. Wait 15 min<br>2. Run a protected action | — | The client receives 401, renews with the refresh token and repeats the action without logging out. If the refresh fails, it logs out |  | Pendiente |  |  |  |
| 24 | CP-AUT-23 | Authentication | 3.1 /recover-password | Security | High | Password recovery does not reveal whether the email exists | One registered email and another not registered | 1. POST /recover-password with each email | existing / nonexistent email | 200 with the same generic message in both cases |  | Pendiente |  |  |  |
| 25 | CP-AUT-24 | Authentication | 3.1 /reset-password | Positive | High | Reset the password with a valid code | Recovery code received | 1. POST /reset-password<br>2. Login with the new password | code + new password and confirmation | 200 and successful login with the new password |  | Pendiente |  |  |  |
| 26 | CP-AUT-25 | Authentication | 3.1 /reset-password | Negative | Medium | Reset with a code already used or expired | Used / expired code | 1. POST /reset-password | reused or expired code | 400 RECOVERY_CODE_USED / RECOVERY_CODE_EXPIRED |  | Pendiente |  |  |  |
| 27 | CP-AUT-26 | Authentication | 3.1 /reset-password | Negative | Medium | Reset with passwords that do not match | Valid code | 1. POST /reset-password | new ≠ confirmation | 400 PASSWORD_MISMATCH |  | Pendiente |  |  |  |
| 28 | CP-AUT-27 | Authentication | 3.1 /oauth | Positive | Medium | Login with Google by OAuth2 (web) | Google credentials configured | 1. Press “Continue with Google” («Continuar con Google») on /login<br>2. Authorize | valid Google account | 302 to /login?oauth=true&token=... and session started |  | Pendiente |  |  |  |
| 29 | CP-AUT-28 | Authentication | 8 Edge cases | Security | High | Open redirect: frontend_redirect_uri outside the allowed list | None | 1. GET /oauth/google with an external frontend_redirect_uri | frontend_redirect_uri: https://sitio-malicioso.com | The request is rejected. It never redirects to the external domain |  | Pendiente |  |  |  |
| 30 | CP-AUT-29 | Authentication | 3.1 /google | Negative | Medium | Login with an invalid Google ID token | None | 1. POST /google with an altered token | invalid token | 400 GOOGLE_TOKEN_INVALID |  | Pendiente |  |  |  |
| 31 | CP-AUT-30 | Authentication | 6 Registration/login | Positive | Medium | Onboarding when the OAuth name does not meet the rules | Google account with a one-word name | 1. Login with Google | — | needsOnboarding response and the web goes to /complete-profile |  | Pendiente |  |  |  |
| 32 | CP-AUT-31 | Authentication | 3.1 /reactivate | Positive | Medium | Reactivation of an inactive account | INACTIVE account | 1. POST /reactivate-request<br>2. POST /reactivate-confirm with the token from the email<br>3. Login | email + token | 200 in both steps and the login works again |  | Pendiente |  |  |  |
| 33 | CP-AUT-32 | Authentication | 3.1 /reactivate | Security | Medium | Reactivation does not allow enumerating users | One registered email and another not registered | 1. POST /reactivate-request with each email | existing / nonexistent email | Always 200, with the same message |  | Pendiente |  |  |  |
| 34 | CP-USR-01 | Users | 3.2 /change-password | Positive | High | Successful password change | Session started | 1. POST /users/change-password | correct current password, valid new one and confirmation | 200. Login with the new password works |  | Pendiente |  |  |  |
| 35 | CP-USR-02 | Users | 3.2 /change-password | Negative | High | Change with an incorrect current password | Session started | 1. POST /users/change-password | wrong current password | 400 INVALID_CURRENT_PASSWORD |  | Pendiente |  |  |  |
| 36 | CP-USR-03 | Users | 3.2 /change-password | Negative | Medium | Reuse a recent password | Password history | 1. Change to the previous password | new = one of the latest | 400 PASSWORD_RECENTLY_USED |  | Pendiente |  |  |  |
| 37 | CP-USR-04 | Users | 3.2 /oauth/link | Negative | Low | Link an OAuth provider that is already linked | Account with Google linked | 1. POST /users/oauth/link with the same provider | provider: google | 400 OAUTH_ALREADY_LINKED |  | Pendiente |  |  |  |
| 38 | CP-USR-05 | Users | 3.2 /organizer-request | Positive | High | Organizer request with a PDF document | User with the USER role | 1. Open /organizer-petition-form<br>2. Attach the PDF and send | .pdf document | Request created in pending status and visible in GET /organizer-petition |  | Pendiente |  |  |  |
| 39 | CP-USR-06 | Users | 3.2 /organizer-request | Negative | Medium | Duplicate request while there is a pending one | Pending request | 1. POST /organizer-request again | — | 400 PETITION_ALREADY_PENDING |  | Pendiente |  |  |  |
| 40 | CP-USR-07 | Users | 3.2 /organizer-request | Negative | Medium | Request from a user who is already an organizer | ORGANIZER user | 1. POST /organizer-request | — | 400 ALREADY_ORGANIZER |  | Pendiente |  |  |  |
| 41 | CP-USR-08 | Users | 3.2 DELETE /me | Positive | Medium | Deactivate the account with the correct password | Session started | 1. DELETE /users/me with the password<br>2. Try to log in | correct password | 200 and the login responds ACCOUNT_DEACTIVATED |  | Pendiente |  |  |  |
| 42 | CP-USR-09 | Users | 3.2 DELETE /me | Negative | Medium | Deactivate the account with an incorrect password | Session started | 1. DELETE /users/me | wrong password | 400 INVALID_PASSWORD and the account remains active |  | Pendiente |  |  |  |
| 43 | CP-ADM-01 | Administration | 3.3 organizer-requests | Positive | High | Approve an organizer request | Pending request. ADMIN session | 1. GET /admin/organizer-requests<br>2. PUT /{id}/approve<br>3. The user logs in again | request id | 200. The user becomes ORGANIZER |  | Pendiente |  |  |  |
| 44 | CP-ADM-02 | Administration | 3.3 organizer-requests | Positive | Medium | Reject an organizer request | Pending request. ADMIN session | 1. PUT /{id}/reject | request id | 200. The user remains USER |  | Pendiente |  |  |  |
| 45 | CP-ADM-03 | Administration | 3.3 organizer-requests | Negative | Medium | Approve or reject an already resolved request | Request already approved | 1. PUT /{id}/approve again | resolved id | 400 PETITION_NOT_PENDING |  | Pendiente |  |  |  |
| 46 | CP-ADM-04 | Administration | 3.3 document | Negative | Low | Download the document of a nonexistent request | ADMIN session | 1. GET /organizer-requests/{id}/document | nonexistent id | 404 PETITION_NOT_FOUND or FILE_NOT_FOUND |  | Pendiente |  |  |  |
| 47 | CP-ADM-05 | Administration | 5 Roles | Security | High | USER tries to use administration endpoints | USER session | 1. GET /api/v1/admin/organizer-requests | USER token | 403 |  | Pendiente |  |  |  |
| 48 | CP-ADM-06 | Administration | 5 Roles | Security | High | Administration endpoint without a token | None | 1. GET /api/v1/admin/events without Authorization | — | 401 |  | Pendiente |  |  |  |
| 49 | CP-PRF-01 | Profile | 3.4 POST / | Positive | Medium | Create a profile | User without a profile | 1. POST /profiles | userId, valid fullName | 201 |  | Pendiente |  |  |  |
| 50 | CP-PRF-02 | Profile | 3.4 POST / | Negative | Medium | Create a duplicate profile | User with a profile | 1. POST /profiles again | same userId | 409 |  | Pendiente |  |  |  |
| 51 | CP-PRF-03 | Profile | 8 Edge cases | Negative | Medium | Bio with inappropriate language and leetspeak | Existing profile | 1. PUT /profiles/{id} with an offensive bio | bio with a forbidden word written in leetspeak | 400 BIO_INAPPROPRIATE_LANGUAGE |  | Pendiente |  |  |  |
| 52 | CP-PRF-04 | Profile | 3.4 PUT | Boundary | Low | Bio of 256 characters (maximum 255) | Existing profile | 1. PUT /profiles/{id} | bio: 256 characters | 400. With 255 characters it must be accepted |  | Pendiente |  |  |  |
| 53 | CP-PRF-05 | Profile | 3.4 GET | Negative | Low | Query a nonexistent profile | None | 1. GET /profiles/999999 | — | 404 |  | Pendiente |  |  |  |
| 54 | CP-EVT-01 | Events | 3.5 POST | Positive | High | Create a valid event | ORGANIZER session, active site and category | 1. POST /events (or wizard /events/create) | eventName, siteId, future startDate, finishDate ≥ startDate, availableSeats 500, categoryId | 201. Event in DRAFT status |  | Pendiente |  |  |  |
| 55 | CP-EVT-02 | Events | 4 Event | Negative | High | Start date in the past | ORGANIZER session | 1. POST /events | startDate: yesterday | 400 EVENT_START_DATE_IN_PAST |  | Pendiente |  |  |  |
| 56 | CP-EVT-03 | Events | 4 Event | Boundary | Medium | Start date more than 2 years away | ORGANIZER session | 1. POST /events | startDate: today + 2 years + 1 day | 400 EVENT_START_DATE_TOO_FAR |  | Pendiente |  |  |  |
| 57 | CP-EVT-04 | Events | 4 Event | Negative | High | End date earlier than the start | ORGANIZER session | 1. POST /events | finishDate < startDate | 400 EVENT_END_BEFORE_START |  | Pendiente |  |  |  |
| 58 | CP-EVT-05 | Events | 4 Event | Negative | Medium | Mandatory dates missing | ORGANIZER session | 1. POST /events without startDate or finishDate | — | 400 EVENT_DATES_REQUIRED |  | Pendiente |  |  |  |
| 59 | CP-EVT-06 | Events | 4 Event | Negative | Medium | Duplicate event (same name, date and site) | Event already created | 1. POST /events with the same data | same name + startDate + siteId | 400 EVENT_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 60 | CP-EVT-07 | Events | 4 Event | Boundary | High | Maximum attendance at the limits 0, 1, 100000 and 100001 | ORGANIZER session | 1. POST /events varying availableSeats | 0 / 1 / 100000 / 100001 | 0 and 100001 give 400. 1 and 100000 are accepted if they fit in the site |  | Pendiente |  |  |  |
| 61 | CP-EVT-08 | Events | 4 Event | Negative | High | Maximum attendance greater than the capacity of the site | Site with capacity 200 | 1. POST /events | availableSeats: 201 | 400 SEATS_EXCEED_CAPACITY |  | Pendiente |  |  |  |
| 62 | CP-EVT-09 | Events | 4 Event | Negative | Medium | Inactive or nonexistent category | Deactivated category | 1. POST /events | inactive categoryId | 400 CATEGORY_NOT_FOUND_OR_INACTIVE |  | Pendiente |  |  |  |
| 63 | CP-EVT-10 | Events | 5 Roles | Security | High | An organizer edits another organizer's event | Two organizers | 1. Log in as organizer B<br>2. PUT /events/{A's id} | — | Access denied EVENT_ACCESS_DENIED |  | Pendiente |  |  |  |
| 64 | CP-EVT-11 | Events | 4 Event | Negative | High | Send for review with fewer than 3 or more than 9 images | DRAFT event with 2 images | 1. PATCH /events/{id}/status to PENDING_REVIEW<br>2. Repeat with 10 images | 2 and 10 images | 400 EVENT_PUBLISH_MEDIA_COUNT_INVALID |  | Pendiente |  |  |  |
| 65 | CP-EVT-12 | Events | 4 Event | Negative | High | Send for review without sections with seats | DRAFT event with 3 images and without sections | 1. PATCH status to PENDING_REVIEW | — | 400 EVENT_SECTIONS_REQUIRED |  | Pendiente |  |  |  |
| 66 | CP-EVT-13 | Events | 4 Statuses | Positive | High | Complete flow DRAFT → PENDING_REVIEW → PUBLISHED | Event with 3–9 images and sections with seats | 1. The organizer sends it for review<br>2. ADMIN publishes from /admin-events<br>3. Open /events without a session | — | The event is PUBLISHED and appears in the public catalogue |  | Pendiente |  |  |  |
| 67 | CP-EVT-14 | Events | 4 Statuses | Negative | Medium | Admin rejects without a reason | PENDING_REVIEW event | 1. PATCH /admin/events/{id}/status newStatus REJECTED without reason | empty reason | 400. The reason is mandatory when rejecting |  | Pendiente |  |  |  |
| 68 | CP-EVT-15 | Events | 4 Statuses | Negative | High | Admin tries to publish from DRAFT | DRAFT event | 1. PATCH /admin/events/{id}/status to PUBLISHED | — | 400 EVENT_INVALID_STATUS_TRANSITION |  | Pendiente |  |  |  |
| 69 | CP-EVT-16 | Events | 4 Statuses | Negative | Medium | Complete the event before the day after finishDate | PUBLISHED event that ends today | 1. PATCH status to COMPLETED | — | 400 EVENT_COMPLETE_TOO_EARLY |  | Pendiente |  |  |  |
| 70 | CP-EVT-17 | Events | 4 Statuses | Positive | Medium | Cancel a published event | PUBLISHED event with sold tickets | 1. PATCH status to CANCELLED | — | Event CANCELLED. The tickets are not reverted automatically and the UI warns that the refund is separate |  | Pendiente |  |  |  |
| 71 | CP-EVT-18 | Events | 3.5 DELETE | Negative | Medium | Delete a published event | PUBLISHED event | 1. DELETE /events/{id} | — | 400 EVENT_DELETE_NOT_ALLOWED |  | Pendiente |  |  |  |
| 72 | CP-EVT-19 | Events | 3.5 public | Positive | Medium | Public filters by city, category and date range | Published events | 1. GET /events/public/city/{id}<br>2. GET /public/category/{id}<br>3. GET /public/date-range?from&to | valid IDs and dates | 200 with the events that meet each filter |  | Pendiente |  |  |  |
| 73 | CP-EVT-20 | Events | 3.5 public | Negative | Low | Invalid date range | None | 1. GET /events/public/date-range?from=2026-12-31&to=2026-01-01 | from > to | 400 INVALID_DATE_RANGE |  | Pendiente |  |  |  |
| 74 | CP-EVT-21 | Events | 3.5 public | Security | High | Events in DRAFT do not appear in the public catalogue | DRAFT event | 1. GET /events/public | — | The DRAFT event is not in the list |  | Pendiente |  |  |  |
| 75 | CP-MED-01 | Media and layout | 3.6 media | Positive | High | Upload a valid image to the event | ORGANIZER session that owns the event | 1. POST /events/{id}/media (multipart) | .jpg image of 2 MB | 200/201 and the image appears in GET /media |  | Pendiente |  |  |  |
| 76 | CP-MED-02 | Media and layout | 8 Edge cases | Negative | High | Image rejected by moderation | ORGANIZER session | 1. POST /events/{id}/media with an inappropriate image | image that triggers NSFW or Sightengine | 422 due to the image policy |  | Pendiente |  |  |  |
| 77 | CP-MED-03 | Media and layout | 3.16 Storage | Boundary | Medium | File larger than the 10 MB limit | ORGANIZER session | 1. POST media with an 11 MB file | 11 MB file | Rejection due to size (FILE_TOO_LARGE or multipart error) |  | Pendiente |  |  |  |
| 78 | CP-MED-04 | Media and layout | 4 Event | Negative | High | Edit the layout with the event under review | PENDING_REVIEW event | 1. PUT /events/{id}/layout | — | 400 EVENT_LAYOUT_EDIT_NOT_ALLOWED |  | Pendiente |  |  |  |
| 79 | CP-MED-05 | Media and layout | 4 Event | Negative | High | Regenerate seats with reservations or sales | Event with RESERVED or SOLD seats | 1. PUT /events/{id}/layout changing sections | — | 400 SEAT_REGENERATION_CONFLICT |  | Pendiente |  |  |  |
| 80 | CP-MED-06 | Media and layout | 3.6 layout | Security | High | Layout PUT by a user who is not the owner | Another organizer's event | 1. PUT /events/{id}/layout | — | Access denied |  | Pendiente |  |  |  |
| 81 | CP-MED-07 | Media and layout | 3.6 layout | Positive | Medium | Layout editor: create sections, blocks and seats (web) | DRAFT event | 1. Open /events/:id/layout<br>2. Create a section with a price<br>3. Generate seats<br>4. Save and reload | — | The layout persists and the generated seats match the editor |  | Pendiente |  |  |  |
| 82 | CP-RAT-01 | Ratings and comments | 3.6 ratings | Positive | Medium | Rate and comment on a published event | USER user, public PUBLISHED event | 1. POST /events/{id}/ratings | rating 4, valid comment | 201 and it is seen in GET /ratings |  | Pendiente |  |  |  |
| 83 | CP-RAT-02 | Ratings and comments | 3.6 ratings | Negative | Medium | Second numeric rating by the same user | User already rated | 1. POST ratings with another rating | rating 2 | It is only accepted as a comment. A second rating is not created |  | Pendiente |  |  |  |
| 84 | CP-RAT-03 | Ratings and comments | 3.6 ratings | Negative | Medium | The organizer rates their own event | Owner ORGANIZER session | 1. POST ratings with rating | rating 5 | The organizer's rating is rejected |  | Pendiente |  |  |  |
| 85 | CP-RAT-04 | Ratings and comments | 3.6 ratings | Negative | Medium | Rate an event that is not published or completed | DRAFT or CANCELLED event | 1. POST ratings | — | EVENT_RATING_NOT_ALLOWED |  | Pendiente |  |  |  |
| 86 | CP-RAT-05 | Ratings and comments | 3.6 ratings | Boundary | Low | Empty comment and comment of 501 characters | PUBLISHED event | 1. POST ratings with a blank comment<br>2. POST with 501 characters | — | COMMENT_BLANK and COMMENT_TOO_LONG. With 500 characters it is accepted |  | Pendiente |  |  |  |
| 87 | CP-RAT-06 | Ratings and comments | 3.6 ratings | Boundary | Low | Antispam: two comments in less than 10 seconds | PUBLISHED event | 1. POST a comment<br>2. POST another comment immediately | — | COMMENT_RATE_LIMITED on the second one |  | Pendiente |  |  |  |
| 88 | CP-CAT-01 | Categories and sites | 3.7 categories | Positive | Medium | Admin creates a category | ADMIN session | 1. POST /categories | new name | 201 |  | Pendiente |  |  |  |
| 89 | CP-CAT-02 | Categories and sites | 3.7 categories | Negative | Medium | Category with a repeated name | Existing category | 1. POST /categories with the same name | duplicate name | CATEGORY_NAME_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 90 | CP-CAT-03 | Categories and sites | 5 Roles | Security | High | Organizer tries to create a category | ORGANIZER session | 1. POST /categories | — | 403 |  | Pendiente |  |  |  |
| 91 | CP-CAT-04 | Categories and sites | 3.8 geolocation | Positive | Medium | Organizer creates a valid site | ORGANIZER session, existing city | 1. POST /geolocation/sites | name, address, capacity 500, latitude 2.93, longitude -75.28 | 201 |  | Pendiente |  |  |  |
| 92 | CP-CAT-05 | Categories and sites | 3.8 geolocation | Boundary | Medium | Site with capacity 0 and coordinates out of range | ORGANIZER session | 1. POST site with capacity 0<br>2. POST with latitude 91<br>3. POST with longitude -181 | capacity 0, lat 91, lon -181 | 400 in each case |  | Pendiente |  |  |  |
| 93 | CP-CAT-06 | Categories and sites | 3.8 geolocation | Negative | Low | Duplicate site | Existing site | 1. POST site with the same data | — | 409 |  | Pendiente |  |  |  |
| 94 | CP-CAT-07 | Categories and sites | 3.8 geolocation | Positive | Low | Search for nearby sites | Sites with coordinates | 1. GET nearby sites with latitude, longitude and radiusKm | radiusKm: 10 | List of sites within the radius |  | Pendiente |  |  |  |
| 95 | CP-SIL-01 | Sections and seats | 3.9 sections | Boundary | Medium | Section with capacity 0 or a negative price | DRAFT event | 1. POST /event-sections with capacity 0<br>2. POST with price -1 | — | 400 in both. Capacity 1 and price 0 are accepted |  | Pendiente |  |  |  |
| 96 | CP-SIL-02 | Sections and seats | 3.9 sections | Negative | Low | Duplicate section in the same event | Existing section | 1. Repeated POST /event-sections | — | EVENT_SECTION_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 97 | CP-SIL-03 | Sections and seats | 3.9 seats | Positive | High | Reserve an available seat | PUBLISHED event. Authenticated user | 1. Select a seat in /events/:id<br>2. POST /seats/{id}/reserve | AVAILABLE seatId | Seat RESERVED for 10 min and the change is published via WebSocket to other clients |  | Pendiente |  |  |  |
| 98 | CP-SIL-04 | Sections and seats | 3.9 seats | Negative | High | Reserve a seat already reserved by another user | Seat RESERVED by user A | 1. User B makes POST /seats/{id}/reserve | — | SEAT_NOT_AVAILABLE |  | Pendiente |  |  |  |
| 99 | CP-SIL-05 | Sections and seats | 3.9 seats | Concurrency | High | Two users reserve the same seat at the same time | AVAILABLE seat. Two sessions | 1. Send the two reservation requests simultaneously | — | Only one reservation succeeds. The other receives SEAT_NOT_AVAILABLE. There is no double reservation |  | Pendiente |  |  |  |
| 100 | CP-SIL-06 | Sections and seats | 4 Seats | Positive | High | The reservation expires after 10 minutes | RESERVED seat | 1. Wait 10 min without creating the order | — | The seat returns to AVAILABLE and it is notified via WebSocket |  | Pendiente |  |  |  |
| 101 | CP-SIL-07 | Sections and seats | 3.9 seats | Negative | Medium | Release another user's seat, an unreserved seat or your own seat | Seats in different statuses | 1. POST /seats/{id}/release in each case | — | Own: success. Another user's: UNAUTHORIZED_RELEASE. Not reserved: SEAT_NOT_RESERVED |  | Pendiente |  |  |  |
| 102 | CP-SIL-08 | Sections and seats | 3.9 seats | Negative | Low | Identical status change and duplicate seat code | Organizer of the event | 1. PATCH /seats with the same status<br>2. POST /seats with a repeated code | — | SEAT_STATUS_UNCHANGED and SEAT_CODE_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 103 | CP-SIL-09 | Sections and seats | 3.9 WebSocket | Security | Medium | WebSocket handshake without JWT | None | 1. Connect to /ws without a token | — | The connection is rejected |  | Pendiente |  |  |  |
| 104 | CP-ORD-01 | Orders and tickets | 3.10 /orders | Positive | High | Create an order with reserved seats | User with valid RESERVED seats | 1. POST /orders | eventId, seatIds [1,2] | DRAFT order, PENDING tickets with QR. Total = sum of section prices |  | Pendiente |  |  |  |
| 105 | CP-ORD-02 | Orders and tickets | 3.10 /orders | Negative | High | Order with a seat not reserved by the user | Seat reserved by another user | 1. POST /orders | seatIds with another user's seat | 400 |  | Pendiente |  |  |  |
| 106 | CP-ORD-03 | Orders and tickets | 3.10 /orders | Negative | High | Order with an expired reservation | Reservation older than 10 min | 1. POST /orders | expired seatIds | 400 |  | Pendiente |  |  |  |
| 107 | CP-ORD-04 | Orders and tickets | 3.10 /orders | Negative | Medium | Order without seats | Session started | 1. POST /orders with empty seatIds | seatIds: [] | 400 due to validation (minimum 1) |  | Pendiente |  |  |  |
| 108 | CP-ORD-05 | Orders and tickets | 3.10 cancel | Positive | High | Cancel an order in DRAFT or PAYMENT_PENDING | DRAFT order | 1. POST /orders/{id}/cancel | — | Order CANCELLED, tickets CANCELLED and seats AVAILABLE |  | Pendiente |  |  |  |
| 109 | CP-ORD-06 | Orders and tickets | 4 Orders | Negative | High | Cancel an order that has already been paid | PAID order | 1. POST /orders/{id}/cancel | — | 409 |  | Pendiente |  |  |  |
| 110 | CP-ORD-07 | Orders and tickets | 8 Gaps | Security | High | Cancel another user's order | Order of user A. Session of user B | 1. User B makes POST /orders/{A's id}/cancel | — | It should be rejected (403) |  | Pendiente |  |  | Known gap: today the owner is not checked. If the cancellation is executed, record a defect |
| 111 | CP-ORD-08 | Orders and tickets | 8 Gaps | Security | High | Query another user's tickets by userId | Two users with tickets | 1. User B makes GET /tickets/user/{A's id} | — | It should be rejected (403) |  | Pendiente |  |  | Known gap: it is not verified that it is the same user |
| 112 | CP-ORD-09 | Orders and tickets | 3.10 checkin | Positive | High | Check-in of a paid ticket | PAID ticket, not expired | 1. POST /tickets/{id}/checkin | validatedBy: name of the validator | 200. Ticket USED and record in ticket_checkin |  | Pendiente |  |  |  |
| 113 | CP-ORD-10 | Orders and tickets | 3.10 checkin | Negative | High | Repeated check-in of the same ticket | USED ticket | 1. POST /tickets/{id}/checkin again | — | 400 because the ticket has already been used |  | Pendiente |  |  |  |
| 114 | CP-ORD-11 | Orders and tickets | 3.10 checkin | Negative | High | Check-in of an unpaid or expired ticket | PENDING / expired ticket | 1. POST /tickets/{id}/checkin | — | 400 |  | Pendiente |  |  |  |
| 115 | CP-ORD-12 | Orders and tickets | 8 Gaps | Security | High | Check-in performed by a user without the organizer role | PAID ticket. USER session | 1. POST /tickets/{id}/checkin with a USER token | — | It should be denied |  | Pendiente |  |  | Known gap: there is no @PreAuthorize or staff role. Test only through the API (there is no QR scanner) |
| 116 | CP-PAG-01 | Payments | 3.11 /payments | Positive | High | Create a QR payment without wallet | DRAFT order | 1. POST /payments with orderId and paymentMethod QR | applyWalletCredit: false | 201 (without the ApiResponse envelope). Payment PENDING and order PAYMENT_PENDING |  | Pendiente |  |  |  |
| 117 | CP-PAG-02 | Payments | 3.11 webhook | Integration | High | Approved payment webhook | PENDING payment in the sandbox gateway | 1. Approve the payment in the sandbox gateway (port 4001)<br>2. Verify the order, tickets and seats | valid HMAC signature | Payment APPROVED, order PAID, tickets PAID and seats SOLD |  | Pendiente |  |  |  |
| 118 | CP-PAG-03 | Payments | 3.11 webhook | Integration | High | Rejected payment webhook | PENDING payment | 1. Reject the payment in the sandbox gateway<br>2. Verify the statuses | valid HMAC signature | Payment REJECTED. Seats AVAILABLE, tickets and order cancelled |  | Pendiente |  |  |  |
| 119 | CP-PAG-04 | Payments | 3.11 webhook | Security | High | Webhook with an invalid HMAC signature | None | 1. POST /webhooks/payment with an altered X-Signature | incorrect signature | 401 and no status change |  | Pendiente |  |  |  |
| 120 | CP-PAG-05 | Payments | 8 Edge cases | Concurrency | High | Duplicate webhook (same gateway_event_id) | Webhook already processed | 1. Resend the same webhook | same eventId | 200 without a double effect (idempotent) |  | Pendiente |  |  |  |
| 121 | CP-PAG-06 | Payments | 4 Statuses | Negative | Medium | Payment of an order that is no longer in DRAFT | PAID or CANCELLED order | 1. POST /payments | orderId of a closed order | 409 due to an invalid transition |  | Pendiente |  |  |  |
| 122 | CP-PAG-07 | Payments | 8 Edge cases | Integration | High | Gateway down when creating the payment | Sandbox gateway turned off | 1. Turn off the gateway<br>2. POST /payments with applyWalletCredit true | — | Controlled error. No orphan wallet reservation or hanging order remains (rollback) |  | Pendiente |  |  |  |
| 123 | CP-PAG-08 | Payments | 4 Wallet | Positive | High | 100% wallet payment | Balance ≥ order total | 1. POST /payments with applyWalletCredit true | — | APPROVED immediately, amount 0, walletAmountApplied = total and gatewayTransactionId with the wallet_only_ prefix |  | Pendiente |  |  |  |
| 124 | CP-PAG-09 | Payments | 4 Wallet | Positive | High | Mixed payment (wallet + gateway) | Balance lower than the total | 1. POST /payments with applyWalletCredit true<br>2. Approve in the gateway | — | Wallet reserved and then deducted. The gateway charges only the difference |  | Pendiente |  |  |  |
| 125 | CP-PAG-10 | Payments | 4 Wallet | Positive | High | Rejected mixed payment releases the balance | Mixed payment in progress | 1. Reject in the gateway<br>2. Query GET /wallet/me | — | The reserved balance is available again |  | Pendiente |  |  |  |
| 126 | CP-PAG-11 | Payments | 3.11 refund | Integration | High | Refund of a gateway payment (ADMIN) | APPROVED payment | 1. POST /payments/{id}/refund with a reason<br>2. Wait for the payment.refunded webhook | reason: Evento cancelado | Payment, order and tickets REFUNDED. The seats remain SOLD as defined |  | Pendiente |  |  |  |
| 127 | CP-PAG-12 | Payments | 4 Wallet | Positive | High | Refund of a wallet-only payment | APPROVED wallet_only payment | 1. POST /payments/{id}/refund | valid reason | Local closure. Payment, order and tickets REFUNDED and balance returned to the wallet |  | Pendiente |  |  |  |
| 128 | CP-PAG-13 | Payments | 3.11 refund | Boundary | Medium | Refund without a reason or with a reason of 501 characters | APPROVED payment | 1. POST refund with an empty reason<br>2. POST with 501 characters | — | 400 in both. With 500 characters it is accepted |  | Pendiente |  |  |  |
| 129 | CP-PAG-14 | Payments | 5 Roles | Security | High | USER tries to refund | USER session | 1. POST /payments/{id}/refund | — | 403 |  | Pendiente |  |  |  |
| 130 | CP-PAG-15 | Payments | 4 Statuses | Negative | Medium | Refund of a payment that is not APPROVED | PENDING payment | 1. POST /payments/{id}/refund | — | Rejected. Only an APPROVED payment is refunded |  | Pendiente |  |  |  |
| 131 | CP-PAG-16 | Payments | 3.11 UI | Positive | Medium | Checkout, pending payment and confirmed payment screens (web) | Order created | 1. Go to /checkout<br>2. Pay<br>3. Wait on /checkout/pending/:id until /checkout/confirmed/:id | — | The UI changes from pending to confirmed when the webhook arrives |  | Pendiente |  |  |  |
| 132 | CP-WAL-01 | Wallet | 3.12 /wallet/me | Positive | Medium | Query your own wallet and movements | User with a wallet | 1. GET /wallet/me<br>2. GET /wallet/me/transactions | — | 200 with the balance and movements of the owner |  | Pendiente |  |  |  |
| 133 | CP-WAL-02 | Wallet | 3.12 /wallet/me | Negative | Low | Query the wallet of a user without a wallet | User without a wallet | 1. GET /wallet/me | — | 404 |  | Pendiente |  |  |  |
| 134 | CP-WAL-03 | Wallet | 3.12 /credit | Positive | Medium | Admin credits balance | ADMIN session | 1. POST /wallet/credit | userId, amount | 200 and the balance increases |  | Pendiente |  |  |  |
| 135 | CP-WAL-04 | Wallet | 5 Roles | Security | High | Common user tries to credit or adjust the wallet | USER session | 1. POST /wallet/credit<br>2. POST /wallet/adjust | — | 403 in both |  | Pendiente |  |  |  |
| 136 | CP-WAL-05 | Wallet | 3.12 /adjust | Negative | High | Negative adjustment greater than the balance | Balance 10.000 | 1. POST /wallet/adjust with -20.000 | amount: -20000 | 422 InsufficientWalletBalance. The balance is never left negative |  | Pendiente |  |  |  |
| 137 | CP-NOT-01 | Notifications | 3.13 | Positive | Medium | List notifications with pagination and only unread ones | User with notifications | 1. GET /notifications/me?page=0&size=20<br>2. GET with unreadOnly=true | — | 200 paginated and filtered |  | Pendiente |  |  |  |
| 138 | CP-NOT-02 | Notifications | 3.13 | Positive | Medium | Mark one and all as read | Unread notifications | 1. PATCH /{id}/read<br>2. PATCH /me/read-all<br>3. GET /me/unread-count | — | The counter goes down to 0 at the end |  | Pendiente |  |  |  |
| 139 | CP-NOT-03 | Notifications | 7 Integrations | Integration | Medium | Email notification on a business event | SMTP configured | 1. Run an approved payment or an activation<br>2. Check the inbox | — | The email arrives and the in-app notification is created |  | Pendiente |  |  |  |
| 140 | CP-NOT-04 | Notifications | 3.13 | Security | High | A user does not see another user's notifications | Two users | 1. Mark as read with another user's notificationUserId | another user's id | Rejected or 404. It only operates on your own |  | Pendiente |  |  |  |
| 141 | CP-TEM-01 | Themes and languages | 3.14 themes | Positive | Low | Activate, customize and reset a theme | Session started | 1. POST activate of a theme<br>2. PUT customize<br>3. DELETE customize/{property} | dark theme | It is applied, customized and the property is reverted |  | Pendiente |  |  |  |
| 142 | CP-TEM-02 | Themes and languages | 3.15 languages | Positive | Low | Only active languages are listed publicly | Active and inactive languages | 1. GET /languages without a session | — | Only active languages |  | Pendiente |  |  |  |
| 143 | CP-TEM-03 | Themes and languages | 3.15 languages | Negative | Medium | Create a language with an existing code | Existing language | 1. POST language with a repeated code | code: es | LANGUAGE_CODE_EXISTS |  | Pendiente |  |  |  |
| 144 | CP-TEM-04 | Themes and languages | 3.15 languages | Negative | Medium | Deactivate the default language | Default language defined | 1. Deactivate the default language | — | CANNOT_DEACTIVATE_DEFAULT_LANGUAGE |  | Pendiente |  |  |  |
| 145 | CP-TEM-05 | Themes and languages | 3.15 translation | Positive | Medium | Request an asynchronous translation (ADMIN) | LibreTranslate up. ADMIN session | 1. POST /api/admin/translations/request<br>2. Query the job of the entity | entityType, entityId, sourceLanguageCode | Job created and translation completed. Brands and proper names are not translated |  | Pendiente |  |  | The global list of pending jobs returns empty (known TODO) |
| 146 | CP-TEM-06 | Themes and languages | 5 Roles | Security | Medium | USER tries to request translations | USER session | 1. POST /api/admin/translations/request | — | 403 |  | Pendiente |  |  |  |
| 147 | CP-SEG-01 | Security and storage | 3.16 Storage | Negative | Medium | Upload with an extension that is not allowed | Session started | 1. POST /storage/upload with an .exe | .exe file | 400 INVALID_FILE_EXTENSION |  | Pendiente |  |  |  |
| 148 | CP-SEG-02 | Security and storage | 8 Gaps | Security | High | Upload to storage without authentication | None | 1. POST /storage/upload without Authorization | — | It should return 401 |  | Pendiente |  |  | Known gap: the route is in permitAll |
| 149 | CP-SEG-03 | Security and storage | 8 Gaps | Security | High | Development endpoint for the activation code | Production environment | 1. GET /auth/dev/activate-code/{email} | registered email | It must be disabled (404 or 403) |  | Pendiente |  |  | Known gap: it exists only for testing |
| 150 | CP-SEG-04 | Security and storage | 7 Integrations | Security | Medium | Exposure of Actuator and Swagger | Production environment | 1. GET /actuator<br>2. GET /swagger-ui | — | They must not expose sensitive information without authentication |  | Pendiente |  |  | Today Actuator is public |
| 151 | CP-SEG-05 | Security and storage | 5 Roles | Security | High | Protected frontend routes according to role | USER session | 1. Open /admin-panel and /events/create manually | — | ProtectedRoute redirects. The backend responds 403 when calling the API |  | Pendiente |  |  |  |
| 152 | CP-SEG-06 | Security and storage | 9 Pending | Integration | Medium | Mobile coverage: purchase flow | Expo app, session started | 1. Login<br>2. Event detail<br>3. Checkout<br>4. PaymentPending | — | The mobile flow completes the purchase in the same way as the web |  | Pendiente |  |  |  |

**Sheet configuration**:

- Frozen panes at `C2`.
- Autofilter on `A1:O152`.
- Data validation (list) in `L2:L152`: `"Pendiente,Aprobado,Fallido,Bloqueado"`.
- Conditional formatting in `L2:L152`: type `cellIs`, operator `equal`, formula `"Aprobado"` (the applied style is not reproduced).
- Conditional formatting in `L2:L152`: type `cellIs`, operator `equal`, formula `"Fallido"` (the applied style is not reproduced).
- Conditional formatting in `L2:L152`: type `cellIs`, operator `equal`, formula `"Bloqueado"` (the applied style is not reproduced).

