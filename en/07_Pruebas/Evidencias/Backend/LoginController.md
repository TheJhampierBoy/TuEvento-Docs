---
id: TE-0143
title: "LoginController"
lang: en
source: 06_Pruebas/Backend/LoginController.pdf
source_sha256: b0b38c8352b34e4c39edb8872b4823570e5f23ab9c94332e8c8b7e8b05554ff4
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–6: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Éxi-to, Ex-cepción."
  - "69 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/LoginController.md
es_sha256: fb2c813a57b6fc7a73694092d9c57fa9abc5b9c298316a5866e84f8becab2dee
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - LoginController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for LoginController.

## 2. Reference Documents

Version: 1.0<br>
Title: LoginController Tests

## 3. Test: POST /api/v1/login/start - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Log in

Objective: Verify successful login<br>
Test Type: Unit

Input data: valid LoginDto

Procedure: POST

Output data - Expected Result: ResponseLogin

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/login/start - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid credentials

Objective: Error handling<br>
Test Type: Unit

Input data: invalid LoginDto

Procedure: POST

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates credentials.

## 5. Test: POST /api/v1/login/changePassword - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Change password

Objective: Verify change<br>
Test Type: Unit

Input data: valid ChangePasswordDto

Procedure: POST

Output data - Expected Result: Success

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: POST /api/v1/login/changePassword - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid password

Objective: Error handling<br>
Test Type: Unit

Input data: invalid ChangePasswordDto

Procedure: POST

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates password.

## 7. Test: POST /api/v1/login/forgot - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Forgot password

Objective: Verify email sending

Test Type: Unit

Input data: valid ForgotPasswordDto

Procedure: POST

Output data - Expected Result: Success

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: POST /api/v1/login/forgot - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent email

Objective: Error handling<br>
Test Type: Unit<br>
Input data: Invalid email<br>
Procedure: POST

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates email.

## 9. Test: GET /api/v1/login/validateResetToken - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Validate token

Objective: Verify valid token<br>
Test Type: Unit<br>
Input data: valid token<br>
Procedure: GET

Output data - Expected Result: Success

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/login/validateResetToken - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid token

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid token<br>
Procedure: GET

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates token.

## 11. Test: POST /api/v1/login/resetPasswordWithToken - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Reset password

Objective: Verify reset<br>
Test Type: Unit

Input data: valid ResetPasswordDTO

Procedure: POST

Output data - Expected Result: Success

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 12. Test: POST /api/v1/login/resetPasswordWithToken - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Expired token

Objective: Error handling<br>
Test Type: Unit

Input data: Expired token

Procedure: POST

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates expiration.
