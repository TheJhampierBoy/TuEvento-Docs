---
id: TE-0136
title: "CityController"
lang: en
source: 06_Pruebas/Backend/CityController.pdf
source_sha256: a103b8fdab5204e09bca0ca186a344027a80b715d80b88302b8f24e7d42e8029
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–5: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Excep-ción, Ca-so, Ca-so."
  - "53 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/CityController.md
es_sha256: 66ac8690009e0d6d98eb4df79dbca30e82e4717ae5af977bcfc89ad86d896aac
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - CityController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for CityController.

## 2. Reference Documents

Version: 1.0<br>
Title: CityController Tests

## 3. Test: POST /api/v1/city - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create city

Objective: Verify creation<br>
Test Type: Unit

Input data: valid CityDto

Procedure: POST

Output data - Expected Result: CityDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/city - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid CityDto

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

## 5. Test: PUT /api/v1/city/{cityID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update city

Objective: Verify update<br>
Test Type: Unit

Input data: cityID, CityDto

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

## 6. Test: PUT /api/v1/city/{cityID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent cityID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid cityID

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

## 7. Test: DELETE /api/v1/city/{cityID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete city

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: valid cityID<br>
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

## 8. Test: DELETE /api/v1/city/{cityID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent city

Objective: Error handling<br>
Test Type: Unit

Input data: invalid cityID

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

## 9. Test: GET /api/v1/city - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all cities

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of CityDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/city/{cityID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get city by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid cityID<br>
Procedure: GET

Output data - Expected Result: CityDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/city/{cityID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent city

Objective: Error handling<br>
Test Type: Unit

Input data: invalid cityID

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
