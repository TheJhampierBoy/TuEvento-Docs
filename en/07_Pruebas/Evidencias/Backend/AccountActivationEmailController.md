---
id: TE-0132
title: "AccountActivationEmailController"
lang: en
source: 06_Pruebas/Backend/AccountActivationEmailController.pdf
source_sha256: 0db87810c8124c9379b410edaeef1c3d5690027c52084f29861de05a0d58cc57
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–2: «{n}»."
  - "16 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/AccountActivationEmailController.md
es_sha256: bfffe3e7cef5a0247ed882bb2b42e391ea1368e8b65e66b4dd38e117ea6da029
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - AccountActivationEmailController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for AccountActivationEmailController.

## 2. Reference Documents

Version: 1.0

Title: AccountActivationEmailController Tests

## 3. Test: POST /api/v1/account-activation-email/send/{userId - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Send activation email

Objective: Verify sending<br>
Test Type: Unit<br>
Input data: valid userId<br>
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

## 4. Test: POST /api/v1/account-activation-email/send/{userId - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent user

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid userId<br>
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

Personal comment: Handles nonexistent ones.
