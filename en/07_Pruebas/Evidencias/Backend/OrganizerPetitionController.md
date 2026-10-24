---
id: TE-0145
title: "OrganizerPetitionController"
lang: en
source: 06_Pruebas/Backend/OrganizerPetitionController.pdf
source_sha256: b90d037ca35c8169ea79ee0239d6512d41ff6f3cd3bc1320c7b4cfc1f5b5cb68
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–5: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so."
  - "52 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/OrganizerPetitionController.md
es_sha256: fa2ea31d0cb78b170e66cf94cfc97d0edf67bbfdc7fb9a640b9fe62cdec6e965
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - OrganizerPetitionController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for OrganizerPetitionController.

## 2. Reference Documents

Version: 1.0

Title: OrganizerPetitionController Tests

## 3. Test: POST /api/v1/organizer-petition - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Upload request

Objective: Verify upload<br>
Test Type: Unit

Input data: MultipartFile, userID

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

## 4. Test: POST /api/v1/organizer-petition - Exception Case

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

## 5. Test: GET /api/v1/organizer-petition - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all requests

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of OrganizerPetitionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: GET /api/v1/organizer-petition/user/{userID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get request by user

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid userID<br>
Procedure: GET

Output data - Expected Result: OrganizerPetitionDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 7. Test: GET /api/v1/organizer-petition/user/{userID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: User without request

Objective: Error handling<br>
Test Type: Unit

Input data: userID without request

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

## 8. Test: PUT /api/v1/organizer-petition/{petitionID}/status - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update status

Objective: Verify update<br>
Test Type: Unit

Input data: petitionID, status

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

## 9. Test: PUT /api/v1/organizer-petition/{petitionID}/status - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent petitionID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid petitionID

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

## 10. Test: GET /api/v1/organizer-petition/{petitionID}/docu - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Download document

Objective: Verify download<br>
Test Type: Unit

Input data: valid petitionID

Procedure: GET

Output data - Expected Result: Byte array

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/organizer-petition/{petitionID}/docu - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Request without document

Objective: Error handling<br>
Test Type: Unit

Input data: petitionID without document

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
