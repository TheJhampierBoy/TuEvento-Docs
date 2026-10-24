---
id: TE-0149
title: "StorageController"
lang: en
source: 06_Pruebas/Backend/StorageController.pdf
source_sha256: 33fabcaae83a1ba407dd8c6f6cbf30d9720656a31a638300454ef27076242615
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–4: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so, Ca-so."
  - "34 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/StorageController.md
es_sha256: 045ea654257484a7292349cfeb5e83aecefbd35b382fa73ff76e8d878c9ea5f3
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - StorageController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for StorageController.

## 2. Reference Documents

Version: 1.0

Title: StorageController Tests

## 3. Test: POST /api/v1/storage/upload - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Upload file

Objective: Verify upload<br>
Test Type: Unit

Input data: valid MultipartFile

Procedure: POST

Output data - Expected Result: File URL

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 4. Test: POST /api/v1/storage/upload - Exception Case

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

Personal comment: Handles invalid ones.

## 5. Test: GET /api/v1/storage/download/{fileName} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Download file

Objective: Verify download<br>
Test Type: Unit

Input data: existing fileName

Procedure: GET

Output data - Expected Result: ByteArrayResource

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 6. Test: GET /api/v1/storage/download/{fileName} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent file

Objective: Error handling<br>
Test Type: Unit

Input data: invalid fileName

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

## 7. Test: DELETE /api/v1/storage/delete/{fileName} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete file

Objective: Verify deletion<br>
Test Type: Unit

Input data: existing fileName

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

## 8. Test: DELETE /api/v1/storage/delete/{fileName} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent file

Objective: Error handling<br>
Test Type: Unit

Input data: invalid fileName

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
