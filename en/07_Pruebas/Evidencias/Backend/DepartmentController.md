---
id: TE-0137
title: "DepartmentController"
lang: en
source: 06_Pruebas/Backend/DepartmentController.pdf
source_sha256: 1487c4d34206898256a11e72ebe8e582af676244a1e1a8cd8b1d8a15bf41441c
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–5: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Éxi-to."
  - "53 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/DepartmentController.md
es_sha256: b3d676868d9bc44e848750cdba374d8a39a6003d6b3c6a32017f3fc5d4bd50e3
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - DepartmentController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for DepartmentController.

## 2. Reference Documents

Version: 1.0

Title: DepartmentController Tests

## 3. Test: POST /api/v1/department - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create department

Objective: Verify creation<br>
Test Type: Unit

Input data: valid DepartmentDto

Procedure: POST

Output data - Expected Result: DepartmentDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/department - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid DepartmentDto

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

## 5. Test: PUT /api/v1/department/{departmentID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update department

Objective: Verify update<br>
Test Type: Unit

Input data: departmentID, DepartmentDto

Procedure: PUT

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

## 6. Test: PUT /api/v1/department/{departmentID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent departmentID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid departmentID

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

## 7. Test: DELETE /api/v1/department/{departmentID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete department

Objective: Verify deletion<br>
Test Type: Unit

Input data: valid departmentID

Procedure: DELETE

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

## 8. Test: DELETE /api/v1/department/{departmentID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent department

Objective: Error handling<br>
Test Type: Unit

Input data: invalid departmentID

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

## 9. Test: GET /api/v1/department - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all departments

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of DepartmentDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/department/{departmentID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get department by ID

Objective: Verify retrieval<br>
Test Type: Unit

Input data: valid departmentID

Procedure: GET

Output data - Expected Result: DepartmentDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/department/{departmentID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent department

Objective: Error handling<br>
Test Type: Unit

Input data: invalid departmentID

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
