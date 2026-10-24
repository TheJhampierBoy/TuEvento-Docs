---
id: TE-0144
title: "NotificationController"
lang: en
source: 06_Pruebas/Backend/NotificationController.pdf
source_sha256: 622d23de3d61b940e32c13cff9ab354ef40295d06269073b84c1619d7513e3b7
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–6: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so, Ca-so."
  - "67 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/NotificationController.md
es_sha256: c996b6e9f233070157838897d00c1ad1d35210363acd53e7e59fb34e723c9414
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - NotificationController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for NotificationController.

## 2. Reference Documents

Version: 1.0

Title: NotificationController Tests

## 3. Test: POST /api/v1/notification/create - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create notification

Objective: Verify creation<br>
Test Type: Unit

Input data: valid NotificationDto

Procedure: POST

Output data - Expected Result: NotificationDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/notification/create - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid NotificationDto

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

## 5. Test: PUT /api/v1/notification/update - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update notification

Objective: Verify update<br>
Test Type: Unit

Input data: valid NotificationDto

Procedure: PUT

Output data - Expected Result: NotificationDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: PUT /api/v1/notification/update - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent notification

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

## 7. Test: DELETE /api/v1/notification/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete notification

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: DELETE

Output data - Expected Result: NotificationDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: DELETE /api/v1/notification/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent notification

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

## 9. Test: GET /api/v1/notification/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get notification by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: GET

Output data - Expected Result: NotificationDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/notification/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent notification

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

## 11. Test: GET /api/v1/notification/event/{eventID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get notifications by event

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid eventID<br>
Procedure: GET

Output data - Expected Result: List of NotificationDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 12. Test: GET /api/v1/notification/event/{eventID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without notifications

Objective: Empty handling<br>
Test Type: Unit

Input data: eventID without notifications

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
