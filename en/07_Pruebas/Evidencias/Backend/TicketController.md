---
id: TE-0150
title: "TicketController"
lang: en
source: 06_Pruebas/Backend/TicketController.pdf
source_sha256: 9bbe5c4e95cfed23be2a893c67abc344d035fac5c5aaa6ade48a02fe5e105f17
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–6: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Éxi-to, Ex-cepción."
  - "61 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/TicketController.md
es_sha256: 505a5cf5c499b7bb9721c22169f0f834af8abf669b8d3ea378c8695c0475066e
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - TicketController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for TicketController.

## 2. Reference Documents

Version: 1.0<br>
Title: TicketController Tests

## 3. Test: POST /api/v1/ticket/create-with-seats - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create ticket with seats

Objective: Verify creation<br>
Test Type: Unit

Input data: valid TicketDto

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

## 4. Test: POST /api/v1/ticket/create-with-seats - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Seats not available

Objective: Conflict handling<br>
Test Type: Unit

Input data: Occupied seats

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

Personal comment: Handles conflicts.

## 5. Test: DELETE /api/v1/ticket/cancel/{ticketID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Cancel ticket

Objective: Verify cancellation<br>
Test Type: Unit

Input data: valid ticketID

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

## 6. Test: DELETE /api/v1/ticket/cancel/{ticketID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent ticket

Objective: Error handling<br>
Test Type: Unit

Input data: invalid ticketID

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

## 7. Test: GET /api/v1/ticket/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get ticket by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: GET

Output data - Expected Result: TicketDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: GET /api/v1/ticket/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent ticket

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

## 9. Test: GET /api/v1/ticket/by-event/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get tickets by event

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: List of TicketDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/ticket/by-event/{eventId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without tickets

Objective: Empty list handling<br>
Test Type: Unit

Input data: eventId without tickets

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

## 11. Test: GET /api/v1/ticket/by-user/{userId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get tickets by user

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid userId<br>
Procedure: GET

Output data - Expected Result: List of TicketDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 12. Test: GET /api/v1/ticket/by-user/{userId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: User without tickets

Objective: Empty list handling<br>
Test Type: Unit

Input data: userId without tickets

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
