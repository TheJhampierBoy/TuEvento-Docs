---
id: TE-0147
title: "SeatController"
lang: en
source: 06_Pruebas/Backend/SeatController.pdf
source_sha256: 5e59455adac95359d2a50b8292ed153fad5e19bc82d43d291d4888a42ec55b32
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–8: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Excep-ción, Ca-so."
  - "84 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/SeatController.md
es_sha256: 07af9dba8e0cb1b66c240983cd146c4d24914f370b150f38f2edb6987c87d33a
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - SeatController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for SeatController.

## 2. Reference Documents

Version: 1.0<br>
Title: SeatController Tests

## 3. Test: POST /api/v1/seat - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create seat

Objective: Verify creation<br>
Test Type: Unit

Input data: valid SeatDto

Procedure: POST

Output data - Expected Result: SeatDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/seat - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid SeatDto

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

## 5. Test: PUT /api/v1/seat/{seatID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update seat

Objective: Verify update<br>
Test Type: Unit

Input data: seatID, SeatDto

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

## 6. Test: PUT /api/v1/seat/{seatID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent seatID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid seatID

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

## 7. Test: PUT /api/v1/seat/{seatID}/status - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update seat status

Objective: Verify status change

Test Type: Unit<br>
Input data: seatID, status<br>
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

## 8. Test: PUT /api/v1/seat/{seatID}/status - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid status

Objective: Error handling<br>
Test Type: Unit

Input data: invalid status

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

Personal comment: Validates status.

## 9. Test: DELETE /api/v1/seat/{seatID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete seat

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: valid seatID<br>
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

## 10. Test: DELETE /api/v1/seat/{seatID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent seat

Objective: Error handling<br>
Test Type: Unit

Input data: invalid seatID

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

## 11. Test: GET /api/v1/seat - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all seats

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of SeatDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 12. Test: GET /api/v1/seat/{seatID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get seat by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid seatID<br>
Procedure: GET

Output data - Expected Result: SeatDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 13. Test: GET /api/v1/seat/{seatID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent seat

Objective: Error handling<br>
Test Type: Unit

Input data: invalid seatID

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

## 14. Test: GET /api/v1/seat/section/{sectionId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get seats by section

Objective: Verify list<br>
Test Type: Unit

Input data: valid sectionId

Procedure: GET

Output data - Expected Result: List of SeatDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 15. Test: GET /api/v1/seat/section/{sectionId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Section without seats

Objective: Empty list handling<br>
Test Type: Unit

Input data: sectionId without seats

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

## 16. Test: POST /api/v1/seat/release-expired - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Release expired reservations

Objective: Verify release<br>
Test Type: Unit<br>
Input data: None<br>
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
