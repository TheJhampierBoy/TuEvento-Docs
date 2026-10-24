---
id: TE-0148
title: "SectionController"
lang: en
source: 06_Pruebas/Backend/SectionController.pdf
source_sha256: e856fd60954c3711eef667fe122646d4e29b4b312de57b6936a938962e8eeca6
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–5: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Excep-ción, Excep-ción, Ca-so, Ca-so."
  - "58 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/SectionController.md
es_sha256: 63504e9f3052754e3647d82aaa45506c3be2b67fadb74cf2847264d9e1b36c72
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - SectionController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for SectionController.

## 2. Reference Documents

Version: 1.0

Title: SectionController Tests

## 3. Test: POST /api/v1/section - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Insert section

Objective: Verify insertion<br>
Test Type: Unit

Input data: valid SectionDto

Procedure: POST

Output data - Expected Result: SectionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/section - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid SectionDto

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

## 5. Test: GET /api/v1/section - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all sections

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of SectionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: PUT /api/v1/section - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update section

Objective: Verify update

Test Type: Unit

Input data: valid SectionDto

Procedure: PUT

Output data - Expected Result: SectionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 7. Test: PUT /api/v1/section - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent ID

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid ID<br>
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

Personal comment: Handles nonexistent ones.

## 8. Test: DELETE /api/v1/section/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete section

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: DELETE

Output data - Expected Result: SectionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 9. Test: DELETE /api/v1/section/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent section

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid id<br>
Procedure: DELETE

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

## 10. Test: GET /api/v1/section/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get section by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: GET

Output data - Expected Result: SectionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/section/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent section

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid id<br>
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

Personal comment: Handles nonexistent ones.
