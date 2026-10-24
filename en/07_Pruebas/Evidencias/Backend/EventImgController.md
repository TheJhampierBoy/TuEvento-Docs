---
id: TE-0139
title: "EventImgController"
lang: en
source: 06_Pruebas/Backend/EventImgController.pdf
source_sha256: 664c7eab5b782309f0dfb61f407fba17e12e40b3d1296e3ec777314d63147ee2
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–4: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Éxi-to, Ex-cepción."
  - "42 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/EventImgController.md
es_sha256: 5a95d1254dff7897ec0a25f658b7269e150a6bf644e452d7ec271e50036363cf
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - EventImgController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for EventImgController.

## 2. Reference Documents

Version: 1.0

Title: EventImgController Tests

## 3. Test: POST /api/v1/event-img - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Upload event image

Objective: Verify upload<br>
Test Type: Unit

Input data: eventId, valid MultipartFile

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

## 4. Test: POST /api/v1/event-img - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid file

Objective: Error handling<br>
Test Type: Unit

Input data: Corrupt file

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

Personal comment: Validates file.

## 5. Test: GET /api/v1/event-img/{eventId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get event images

Objective: Verify list<br>
Test Type: Unit<br>
Input data: valid eventId<br>
Procedure: GET

Output data - Expected Result: List of images

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: GET /api/v1/event-img/{eventId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Event without images

Objective: Empty handling<br>
Test Type: Unit

Input data: eventId without images

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

## 7. Test: DELETE /api/v1/event-img/{eventImgId} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete image

Objective: Verify deletion<br>
Test Type: Unit

Input data: valid eventImgId

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

## 8. Test: DELETE /api/v1/event-img/{eventImgId} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent image

Objective: Error handling<br>
Test Type: Unit

Input data: invalid eventImgId

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
