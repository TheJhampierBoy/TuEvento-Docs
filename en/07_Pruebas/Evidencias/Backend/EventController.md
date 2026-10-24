---
id: TE-0138
title: "EventController"
lang: en
source: 06_Pruebas/Backend/EventController.pdf
source_sha256: 4b2ef27a79fc916792d44e552aef01910168ea73c40dcf099ae034c2d766ba05
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: pendiente_revision
losses:
  - "Page header or footer omitted on pages 1–9: «{n}»."
  - "Words split with a hyphen at the end of a line were joined: indivi-duales, integra-ción, dis-tintos, Éxi-to, Ex-cepción, Éxi-to."
  - "114 LaTeX accents (separate glyph over the letter) recomposed as single characters."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 100.00%, precision 100.00%, order 100.00%; missing {} (explained above)."
  - "The signs «¡» and «¿» in «ResponseDto¡EventDto¿» are like this in the original (LaTeX OT1 encoding, where < and > were written); they are not corrected."
  - "Review by sections: 18 headings (title + sections 1-17) located in the original; the 19 sections match in words and order."
  - "Translation: the characters «Ü» and «”» of the original («Error Üsuario no autenticado”») are kept where they appear."
status: borrador
reviewed_by: ""
translation_of: es/07_Pruebas/Evidencias/Backend/EventController.md
es_sha256: 730404881516a7660b7cc20a30acf06a54e6fd7e6526fd692ce3c9a5d904091e
---
> **Historical document.** This evidence belongs to the project's previous repository, [`lozano2303/tu-evento`](https://github.com/lozano2303/tu-evento) (August–October 2025): the tested controller exists there and not in the current code (`lozano2303/TuEvento`), or it was tested before the current repository existed (first commit: November 2, 2025). It is kept unchanged as evidence of the process. See C9 in `Registro_de_Contradicciones.md`.

# SOFTWARE TEST FORMAT - EventController

Keiner Cano

2 October 2025

## 1. Introduction

The purpose of this document is to track the tests of the EventController in the TuEvento project through the implementation of unit tests.

Unit tests allow us to make sure that the individual methods of a project's code work correctly, as well as the integration of the whole project.

In the functional requirements, the aim is to find errors related to the functionality of the system, and in the non-functional ones, failures in performance, security, usability and reliability.

There are 4 types of tests:

Unit tests. Designed to test a small and specific part of functionality. E.g. A method.

Integration tests. Designed to test the interaction between the different components of a system.

System tests. Designed to test the system as a whole as if it were a black box.

Acceptance tests. Designed to verify that the system meets the requirements demanded by the user.

## 2. Reference Documents

Version: 1.0<br>
Title: EventController Tests

## 3. Test: POST /api/v1/event/insert - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Insert valid event Objective: Verify that the endpoint inserts an event correctly with valid data

Test Type: Unit

Input data of the test: EventDto with all the required fields Test Procedure: Send POST request to /api/v1/event/insert with valid EventDto

Output data - Expected Result: ResponseDto¡EventDto¿with status success and event data

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Works correctly with valid data.

## 4. Test: POST /api/v1/event/insert - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Insert invalid event Objective: Verify that the endpoint handles errors with invalid data Test Type: Unit

Input data of the test: EventDto with missing fields Test Procedure: Send POST request to /api/v1/event/insert with invalid EventDto

Output data - Expected Result: ResponseDto with error message<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles exceptions correctly.

## 5. Test: PUT /api/v1/event/update - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Update valid event Objective: Verify that the endpoint updates an event correctly Test Type: Unit

Input data of the test: valid ResponseEvent and EventDto Test Procedure: Send PUT request to /api/v1/event/update with valid data

Output data - Expected Result: ResponseDto¡EventDto¿updated<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Successful update.

## 6. Test: PUT /api/v1/event/update - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Update event with nonexistent ID Objective: Verify error handling in update

Test Type: Unit

Input data of the test: ID of an event that does not exist

Test Procedure: Send PUT request with invalid ID<br>
Output data - Expected Result: ResponseDto with error<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Personal comment: Handles nonexistent IDs.

## 7. Test: DELETE /api/v1/event/cancel/{eventId} - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Cancel existing event<br>
Objective: Verify event cancellation<br>
Test Type: Unit

Input data of the test: valid eventId, authenticated user<br>
Test Procedure: Send DELETE request with valid eventId<br>
Output data - Expected Result: ResponseDto with success<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Successful cancellation.

## 8. Test: DELETE /api/v1/event/cancel/{eventId} - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Cancel event without authentication<br>
Objective: Verify security in cancellation<br>
Test Type: Unit

Input data of the test: No userID in request

Test Procedure: Send DELETE without authentication<br>
Output data - Expected Result: Error Üser not authenticated”<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Security implemented.

## 9. Test: PUT /api/v1/event/publish/{id} - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Publish event

Objective: Verify event publication<br>
Test Type: Unit

Input data of the test: valid event id

Test Procedure: Send PUT to /publish/id

Output data - Expected Result: Event published

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Successful publication.

## 10. Test: PUT /api/v1/event/publish/{id} - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Publish nonexistent event<br>
Objective: Error handling in publication<br>
Test Type: Unit<br>
Input data of the test: nonexistent id<br>
Test Procedure: PUT with invalid id<br>
Output data - Expected Result: Error<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Handles nonexistent IDs.

## 11. Test: GET /api/v1/event/{id} - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Get event by ID<br>
Objective: Verify event retrieval<br>
Test Type: Unit<br>
Input data of the test: valid id<br>
Test Procedure: GET /id<br>
Output data - Expected Result: EventDto<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Successful retrieval.

## 12. Test: GET /api/v1/event/{id} - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Get nonexistent event<br>
Objective: Error handling<br>
Test Type: Unit<br>
Input data of the test: nonexistent id<br>
Test Procedure: GET with invalid id<br>
Output data - Expected Result: Error<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:

Personal comment: Handles errors correctly.

## 13. Test: GET /api/v1/event/getAllbyUser - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Get events by user<br>
Objective: Verify the user's event list<br>
Test Type: Unit

Input data of the test: Authenticated user

Test Procedure: GET /getAllbyUser

Output data - Expected Result: List of EventDto

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Correct list.

## 14. Test: GET /api/v1/event/getAllbyUser - Exception Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Without authentication

Objective: Verify security<br>
Test Type: Unit<br>
Input data of the test: No userID<br>
Test Procedure: GET without authentication<br>
Output data - Expected Result: Error<br>
Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Security ok.

## 15. Test: GET /api/v1/event/getAll - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Get all events<br>
Objective: Verify complete list<br>
Test Type: Unit<br>
Input data of the test: None<br>
Test Procedure: GET /getAll

Output data - Expected Result: List of EventDto

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Works.

## 16. Test: GET /api/v1/event/filter - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Filter events

Objective: Verify filtering<br>
Test Type: Unit

Input data of the test: Filter parameters

Test Procedure: GET /filter with params

Output data - Expected Result: Filtered list

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Correct filtering.

## 17. Test: PUT /api/v1/event/complete/{eventId} - Success Case

Date performed: 2 October 2025<br>
Test duration: 5 min

Functional Requirement of the test: Complete event

Objective: Verify completion<br>
Test Type: Unit<br>
Input data of the test: valid eventId

Test Procedure: PUT /complete/eventId

Output data - Expected Result: Event completed

Actual Result: Successful Test<br>
Successful Test? Yes<br>
Performed by: Keiner Cano<br>
Signature:<br>
Date: 2 October 2025<br>
Approved by: CapySoft<br>
Signature:<br>
Date:<br>
Personal comment: Completed ok.
