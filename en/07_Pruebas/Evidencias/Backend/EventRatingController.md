---
id: TE-0141
title: "EventRatingController"
lang: en
source: 06_Pruebas/Backend/EventRatingController.pdf
source_sha256: dc8de1cb6d380761da1a1ee10c31ff09553c255632bbbaf89520e15b122315d3
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–7: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so, Ca-so."
  - "66 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/EventRatingController.md
es_sha256: fe18aefc026926d2ab27de808be0a8dabfacfccfbcdd2fe003ed7f69335ac2df
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - EventRatingController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for EventRatingController.

## 2. Reference Documents

Version: 1.0

Title: EventRatingController Tests

## 3. Test: POST /api/v1/event-rating/insert/{userId}/{eventId - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Insert rating

Objective: Verify insertion<br>
Test Type: Unit

Input data: userId, eventId, EventRatingDto

Procedure: POST

Output data - Expected Result: EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/event-rating/insert/{userId}/{eventId - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid IDs

Objective: Error handling<br>
Test Type: Unit

Input data: Nonexistent IDs

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

## 5. Test: PUT /api/v1/event-rating/update - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update rating

Objective: Verify update<br>
Test Type: Unit

Input data: valid EventRatingDto

Procedure: PUT

Output data - Expected Result: EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: PUT /api/v1/event-rating/update - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent rating

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

## 7. Test: GET /api/v1/event-rating/get - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get rating by comment

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: comment<br>
Procedure: GET

Output data - Expected Result: EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 8. Test: GET /api/v1/event-rating/get - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent comment

Objective: Error handling<br>
Test Type: Unit

Input data: invalid comment

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

## 9. Test: DELETE /api/v1/event-rating/delete - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete rating

Objective: Verify deletion<br>
Test Type: Unit<br>
Input data: id<br>
Procedure: DELETE

Output data - Expected Result: EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: DELETE /api/v1/event-rating/delete - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent rating

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

## 11. Test: GET /api/v1/event-rating/getByEvent/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get ratings by event

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: List of EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 12. Test: GET /api/v1/event-rating/getByEvent/{eventId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without ratings

Objective: Empty handling<br>
Test Type: Unit

Input data: eventId without ratings

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

## 13. Test: GET /api/v1/event-rating/getByUser/{userId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get rating by user

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid userId<br>
Procedure: GET

Output data - Expected Result: EventRatingDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 14. Test: GET /api/v1/event-rating/getByUser/{userId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: User without rating

Objective: Error handling<br>
Test Type: Unit

Input data: userId without rating

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
