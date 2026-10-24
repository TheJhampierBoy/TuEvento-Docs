---
id: TE-0133
title: "AddressController"
lang: en
source: 06_Pruebas/Backend/AddressController.pdf
source_sha256: fb29dbb8c422b6747cc80cce746ad2cfc0e3b687096887af2b9fcea066679033
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–5: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ex-cepción."
  - "60 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/AddressController.md
es_sha256: f75837b14bde006eb0f342eb234891b906774a27648810a018d68c8b66fb2a21
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - AddressController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for AddressController.

## 2. Reference Documents

Version: 1.0

Title: AddressController Tests

## 3. Test: POST /api/v1/address - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Create address

Objective: Verify creation<br>
Test Type: Unit

Input data: valid AddressDto

Procedure: POST

Output data - Expected Result: Address ID

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/address - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid data

Objective: Error handling<br>
Test Type: Unit

Input data: invalid AddressDto

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

## 5. Test: PUT /api/v1/address/{addressID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update address

Objective: Verify update<br>
Test Type: Unit

Input data: addressID, AddressDto

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

## 6. Test: PUT /api/v1/address/{addressID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent addressID

Objective: Error handling<br>
Test Type: Unit

Input data: invalid addressID

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

## 7. Test: DELETE /api/v1/address/{addressID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete address

Objective: Verify deletion<br>
Test Type: Unit

Input data: valid addressID

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

## 8. Test: DELETE /api/v1/address/{addressID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent address

Objective: Error handling<br>
Test Type: Unit

Input data: invalid addressID

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

## 9. Test: GET /api/v1/address - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all addresses

Objective: Verify list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of AddressDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 10. Test: GET /api/v1/address/{addressID} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get address by ID

Objective: Verify retrieval<br>
Test Type: Unit

Input data: valid addressID

Procedure: GET

Output data - Expected Result: AddressDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 11. Test: GET /api/v1/address/{addressID} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent address

Objective: Error handling<br>
Test Type: Unit

Input data: invalid addressID

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
