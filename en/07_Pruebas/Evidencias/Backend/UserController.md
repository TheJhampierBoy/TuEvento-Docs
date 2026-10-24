---
id: TE-0151
title: "UserController"
lang: en
source: 06_Pruebas/Backend/UserController.pdf
source_sha256: 8b1f1bba6b19e9c23342a8d040b0d660883c4cc8f054971ca9f49f7d8256b9e7
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–9: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: Ca-so, Ca-so, /api/v1/user/{id}/delete-account, /api/v1/user/{id}/delete-account, Éxi-to, Ex-cepción."
  - "106 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/UserController.md
es_sha256: a9d53f5951f558f4bb4c658c3099295509704710265b3793de8bb773ba6ba974
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - UserController

Keiner Cano

2 October 2025

## 1. Introduction

Tests for UserController.

## 2. Reference Documents

Version: 1.0<br>
Title: UserController Tests

## 3. Test: PUT /api/v1/user/{id}/telephone - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update telephone

Objective: Verify telephone update

Test Type: Unit

Input data: valid id, newTelephone

Procedure: PUT request

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

## 4. Test: PUT /api/v1/user/{id}/telephone - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid telephone

Objective: Error handling<br>
Test Type: Unit

Input data: Invalid telephone

Procedure: PUT with invalid data

Output data - Expected Result: Error

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles errors.

## 5. Test: PUT /api/v1/user/{id}/birthdate - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update date of birth

Objective: Verify update<br>
Test Type: Unit

Input data: id, newBirthDate

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

## 6. Test: PUT /api/v1/user/{id}/birthdate - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Invalid date

Objective: Error handling<br>
Test Type: Unit

Input data: Date in incorrect format

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

Personal comment: Validates format.

## 7. Test: PUT /api/v1/user/{id}/address - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Update address

Objective: Verify update<br>
Test Type: Unit

Input data: id, newAddressId

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

## 8. Test: PUT /api/v1/user/{id}/address - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: nonexistent AddressId

Objective: Error handling<br>
Test Type: Unit

Input data: invalid AddressId

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

Personal comment: Validates existence.

## 9. Test: DELETE /api/v1/user/{id}/deleteaccount - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Delete account

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

## 10. Test: DELETE /api/v1/user/{id}/deleteaccount - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent user

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

## 11. Test: PUT /api/v1/user/{id}/deactivate - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Deactivate user

Objective: Verify deactivation<br>
Test Type: Unit<br>
Input data: valid id<br>
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

## 12. Test: PUT /api/v1/user/{id}/deactivate - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: User already deactivated

Objective: Status handling<br>
Test Type: Unit

Input data: deactivated user id

Procedure: PUT

Output data - Expected Result: Error or handling

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles status.

## 13. Test: PUT /api/v1/user/{id}/reactivate - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Reactivate user

Objective: Verify reactivation<br>
Test Type: Unit<br>
Input data: valid id<br>
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

## 14. Test: PUT /api/v1/user/{id}/reactivate - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: User already active

Objective: Status handling<br>
Test Type: Unit

Input data: active user id

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

Personal comment: Handles status.

## 15. Test: GET /api/v1/user/{id} - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get user by ID

Objective: Verify retrieval<br>
Test Type: Unit<br>
Input data: valid id<br>
Procedure: GET

Output data - Expected Result: UserDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 16. Test: GET /api/v1/user/{id} - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Nonexistent user

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

## 17. Test: GET /api/v1/user/search - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Search users by name

Objective: Verify search<br>
Test Type: Unit<br>
Input data: name

Procedure: GET /search?name=...

Output data - Expected Result: List of UserDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.

## 18. Test: GET /api/v1/user/search - Exception Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Empty name

Objective: Error handling<br>
Test Type: Unit<br>
Input data: empty name<br>
Procedure: GET

Output data - Expected Result: Error or empty list

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles empty.

## 19. Test: GET /api/v1/user - Success Case

Date performed: 2 October 2025

Test duration: 5 min

Functional Requirement: Get all users

Objective: Verify complete list<br>
Test Type: Unit<br>
Input data: None<br>
Procedure: GET

Output data - Expected Result: List of UserDto

Actual Result: Successful Test

Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Ok.
