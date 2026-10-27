---
id: TE-0131
title: "AccountActivationController"
lang: en
source: 06_Pruebas/Backend/AccountActivationController.pdf
source_sha256: 94fb46e09714260b30c3022d1a8526e0651929f381b57f68bbf8b6c2fbcc1979
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–4: «{n}»."
  - "48 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/AccountActivationController.md
es_sha256: bb1b919eace485d13d160d4d849ec5dafdb4e75c5a3504177f001720ad95598b
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - AccountActivationController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for AccountActivationController.

## 2. Reference Documents

Version: 1.0

Title: AccountActivationController Tests

## 3. Test: POST /api/v1/account-activation/create - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create activation code

Objective: Verify creation<br>
Test Type: Unit

Input data: valid AccountActivationDto

Procedure: POST

Output data - Expected Result: Code created

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/account-activation/create - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent user

Objective: Error handling<br>
Test Type: Unit

Input data: Invalid user

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

Personal comment: Validates user.

## 5. Test: PUT /api/v1/account-activation/resend - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Resend code

Objective: Verify resending<br>
Test Type: Unit

Input data: valid AccountActivationDto

Procedure: PUT

Output data - Expected Result: Code resent

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: PUT /api/v1/account-activation/resend - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Code already sent

Objective: Limit handling<br>
Test Type: Unit

Input data: Excessive resending

Procedure: PUT

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles limits.

## 7. Test: PUT /api/v1/account-activation/verify - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Verify code

Objective: Verify activation<br>
Test Type: Unit

Input data: valid AccountActivationDto

Procedure: PUT

Output data - Expected Result: Account activated

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: PUT /api/v1/account-activation/verify - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid code

Objective: Error handling<br>
Test Type: Unit

Input data: Incorrect code

Procedure: PUT

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Validates code.
