---
id: TE-0134
title: "CategoryController"
lang: en
source: 06_Pruebas/Backend/CategoryController.pdf
source_sha256: f643c48b1c54fb6854cd5788540f721e24b26a55a16c96060d371b7442f0d414
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–8: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Éxi-to, Ex-cepción, Ca-so, Ca-so."
  - "96 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/CategoryController.md
es_sha256: 173c089651c2ef3cc8c56ff6b31b14959c664e6c9a8563704a33143bbabdc700
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - CategoryController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for CategoryController.

## 2. Reference Documents

Version: 1.0

Title: CategoryController Tests

## 3. Test: POST /api/v1/category - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create category

Objective: Verify creation<br>
Test Type: Unit

Input data: valid CategoryDto

Procedure: POST

Output data - Expected Result: CategoryDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/category - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid CategoryDto

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

## 5. Test: PUT /api/v1/category/{categoryID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update category

Objective: Verify update<br>
Test Type: Unit

Input data: categoryID, CategoryDto

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

## 6. Test: PUT /api/v1/category/{categoryID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent categoryID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid categoryID

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

## 7. Test: DELETE /api/v1/category/{categoryID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete category

Objective: Verify deletion<br>
Test Type: Unit

Input data: valid categoryID

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

## 8. Test: DELETE /api/v1/category/{categoryID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent category

Objective: Error handling<br>
Test Type: Unit

Input data: invalid categoryID

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

## 9. Test: GET /api/v1/category - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all categories

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of CategoryDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/category/{categoryID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get category by ID

Objective: Verify retrieval<br>
Test Type: Unit

Input data: valid categoryID

Procedure: GET

Output data - Expected Result: CategoryDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/category/{categoryID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent category

Objective: Error handling<br>
Test Type: Unit

Input data: invalid categoryID

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

## 12. Test: GET /api/v1/category/root - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get root categories

Objective: Verify roots<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of roots

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 13. Test: GET /api/v1/category/sub/{parentId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get subcategories

Objective: Verify subcategories<br>
Test Type: Unit

Input data: valid parentId

Procedure: GET

Output data - Expected Result: List of subcategories

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 14. Test: GET /api/v1/category/sub/{parentId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent parent

Objective: Error handling<br>
Test Type: Unit

Input data: invalid parentId

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

## 15. Test: GET /api/v1/category/search - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Search categories

Objective: Verify search<br>
Test Type: Unit<br>
Input data: name

Procedure: GET /search?name=...

Output data - Expected Result: Filtered list

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 16. Test: GET /api/v1/category/search - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Empty name

Objective: Empty handling<br>
Test Type: Unit<br>
Input data: empty name<br>
Procedure: GET

Output data - Expected Result: Empty list

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles empty.
