---
id: TE-0140
title: "EventLayoutController"
lang: en
source: 06_Pruebas/Backend/EventLayoutController.pdf
source_sha256: 2c05c2ed239d87f2023cce3595483b54b397b9e15696294582a88b6879450019
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–6: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so, Ca-so, Ca-so."
  - "63 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/EventLayoutController.md
es_sha256: 99306438bb8c1d3b404f89d9bb41b053e8629172b6867d886d4a7c0ad81537ca
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - EventLayoutController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for EventLayoutController.

## 2. Reference Documents

Version: 1.0

Title: EventLayoutController Tests

## 3. Test: POST /api/v1/event-layout - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create event layout

Objective: Verify creation<br>
Test Type: Unit

Input data: valid EventLayoutDto

Procedure: POST

Output data - Expected Result: EventLayoutDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/event-layout - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid EventLayoutDto

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

## 5. Test: GET /api/v1/event-layout/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get layout by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: GET

Output data - Expected Result: EventLayoutDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: GET /api/v1/event-layout/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent layout

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

## 7. Test: GET /api/v1/event-layout/event/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get layout by event

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: EventLayoutDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: GET /api/v1/event-layout/event/{eventId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without layout

Objective: Error handling<br>
Test Type: Unit

Input data: eventId without layout

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

## 9. Test: PUT /api/v1/event-layout/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update layout

Objective: Verify update<br>
Test Type: Unit

Input data: id, EventLayoutDto

Procedure: PUT

Output data - Expected Result: EventLayoutDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: PUT /api/v1/event-layout/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent id

Objective: Error handling<br>
Test Type: Unit<br>
Input data: invalid id<br>
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

## 11. Test: DELETE /api/v1/event-layout/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete layout

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: valid id<br>
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

## 12. Test: DELETE /api/v1/event-layout/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent layout

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

## 13. Test: GET /api/v1/event-layout/exists/event/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Verify layout existence

Objective: Verify existence<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: Boolean

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.
