---
id: TE-0135
title: "CategoryEventController"
lang: en
source: 06_Pruebas/Backend/CategoryEventController.pdf
source_sha256: a8a2b8ae25e384eec502a320ea2fcf6b848b1dcee1a7de9f940c21957dd591e5
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–7: «{n}»."
  - "83 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/CategoryEventController.md
es_sha256: d24cfc6e6911e0730b5c04ba02c676cef11a7131f7bc3677a5d0a4c8352e3573
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - CategoryEventController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for CategoryEventController.

## 2. Reference Documents

Version: 1.0

Title: CategoryEventController Tests

## 3. Test: POST /api/v1/category-event/assign - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Assign category to event

Objective: Verify assignment<br>
Test Type: Unit

Input data: valid CategoryEventDto

Procedure: POST

Output data - Expected Result: CategoryEventDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/category-event/assign - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent IDs

Objective: Error handling<br>
Test Type: Unit<br>
Input data: Invalid IDs<br>
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

Personal comment: Validates IDs.

## 5. Test: DELETE /api/v1/category-event/remove/{categoryI - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Remove category from event

Objective: Verify removal<br>
Test Type: Unit

Input data: valid categoryId, eventId

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

## 6. Test: DELETE /api/v1/category-event/remove/{categoryI - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent assignment

Objective: Error handling<br>
Test Type: Unit

Input data: Unassigned IDs

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

## 7. Test: GET /api/v1/category-event/event/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get categories by event

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: List of CategoryEventDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: GET /api/v1/category-event/event/{eventId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without categories

Objective: Empty handling<br>
Test Type: Unit

Input data: eventId without assignments

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

## 9. Test: GET /api/v1/category-event/category/{categoryId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get events by category

Objective: Verify list<br>
Test Type: Unit

Input data: valid categoryId

Procedure: GET

Output data - Expected Result: List of CategoryEventDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/category-event/category/{categoryId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Category without events

Objective: Empty handling<br>
Test Type: Unit

Input data: categoryId without assignments

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

## 11. Test: DELETE /api/v1/category-event/event/{eventId}/a - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Remove all categories from event

Objective: Verify bulk removal

Test Type: Unit<br>
Input data: valid eventId<br>
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

## 12. Test: DELETE /api/v1/category-event/event/{eventId}/a - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent event

Objective: Error handling<br>
Test Type: Unit

Input data: invalid eventId

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

## 13. Test: DELETE /api/v1/category-event/category/{categor - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Remove all events from category

Objective: Verify bulk removal

Test Type: Unit

Input data: valid categoryId

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

## 14. Test: DELETE /api/v1/category-event/category/{categor - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent category

Objective: Error handling<br>
Test Type: Unit

Input data: invalid categoryId

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
