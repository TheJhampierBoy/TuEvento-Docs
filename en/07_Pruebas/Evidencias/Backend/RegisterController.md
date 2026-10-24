---
id: TE-0146
title: "RegisterController"
lang: en
source: 06_Pruebas/Backend/RegisterController.pdf
source_sha256: 40fe77313bcb2510ffb17ce386ed3ab5a88d5dff8c2bf41ebd8dad2d3a7b0821
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–2: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ex-cepción."
  - "15 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/RegisterController.md
es_sha256: 39212131a2bc660d4cd30d8177969e692da40b34dcda6975da958b5b772c8974
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - RegisterController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for RegisterController.

## 2. Reference Documents

Version: 1.0

Title: RegisterController Tests

## 3. Test: POST /api/v1/register - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Register user

Objective: Verify successful registration

Test Type: Unit

Input data: valid RegisterRequestDto

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

## 4. Test: POST /api/v1/register - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid RegisterRequestDto

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

Personal comment: Validates data.
