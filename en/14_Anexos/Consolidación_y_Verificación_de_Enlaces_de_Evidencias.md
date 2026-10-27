---
id: TE-0165
title: "Consolidación_y_Verificación_de_Enlaces_de_Evidencias"
lang: en
source: Consolidación_y_Verificación_de_Enlaces_de_Evidencias.md
conversion: "Original Markdown (no conversion). English translation of es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-24
fidelity: pendiente_revision
losses:
  - "Translation: links, folder names and file names are kept as in the original (they are not translated)."
status: borrador
reviewed_by: ""
translation_of: es/14_Anexos/Consolidación_y_Verificación_de_Enlaces_de_Evidencias.md
es_sha256: 3078640ecd042471396e662febffa965ff26373548f72d045cd8d562a0ec0dc0
---
# Learning activity: Consolidation and verification of the training project's evidence links

## 1. General information

Program / cohort (ficha): Technologist in Software Analysis and Development — 3145556  
Training project: Tu Evento  
Work team: CapySoft  
Members: Jhampier Santos Ortiz · Cristofer David Lozano Contreras  
Delivery date: October 15, 2026

---

## 2. Purpose

Organize in a single Markdown document the reference links to the training project's evidence, so that the instructor and other authorized people can locate, open and verify the documentation, technical and functional products of the software.

At the end, the team will export the document to PDF and check that the links still work.

---

## 3. Expected result

A document with direct links to each applicable piece of evidence, a description of its content and its access status. The links must lead to the specific file, folder, repository, deployed application or record. Writing the name of a platform is not enough.

---

## 4. Development instructions

Gather the project's current evidence and check that it matches the current version of the repository and the application.  
Organize the documents in a shared folder or repository with clear names and an easy-to-navigate structure.  
Record the direct link to each piece of evidence in this document's matrix. When several pieces of evidence are in the same repository, include the specific path, folder or file.  
Set up viewing permissions for the instructor and the evaluators.  
If the link is declared public, check it in a private window or without signing in. If it is institutional or private, verify it with the account the evaluator will use.  
Avoid links to local files on the computer, expired links or links that require requesting unresolved permissions.  
Do not publish passwords, tokens, API keys, personal data, sensitive information or configuration files with secrets. Use test data when appropriate.  
Export the final document to PDF and check the links again after exporting.  
Update the matrix when the locations, versions or permissions of the evidence change.

---

## 5. Evidence and links matrix

In Access status, record one of these options: Public, Institutional access verified, Pending permissions or Not available. If a piece of evidence does not apply, justify it in the observations.

| No. | Evidence | Minimum content that must be verifiable | Direct link | Access status | Observations |
|---|---|---|---|---|---|
| 1 | Requirements specification report | Functional and non-functional requirements, user stories, acceptance criteria and traceability. | [02_Especificacion_Requisitos.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/02_Especificacion_Requisitos.md) | Public | |
| 2 | Software analysis | Dynamic views, processes, use cases or other applicable analysis artifacts. | [03_Analisis_Software.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/03_Analisis_Software.md) | Public | |
| 3 | Software technical proposal | Selected alternative, technologies, technical justification, scope and constraints. | [04_Propuesta_Tecnica.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/04_Propuesta_Tecnica.md) | Public | |
| 4 | Software design | Graphical interfaces, architecture, design patterns, data model and applicable diagrams. | [05_Diseno_Software.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/05_Diseno_Software.md) · [06_Base_Datos](https://github.com/TheJhampierBoy/TuEvento-Docs/tree/main/en/06_Base_Datos) | Public | |
| 5 | Source code and software artifacts | Web frontend, mobile application, backend, scripts and database repositories. Indicate the relevant branches. | [TuEvento (repositorio de código)](https://github.com/lozano2303/TuEvento) | Public | Main source code repository. Relevant branches: `main` / `develop`. |
| 6 | Testing documentation | Test plan or test cases, results, execution evidence, defects found and fixes. | [07_Pruebas](https://github.com/TheJhampierBoy/TuEvento-Docs/tree/main/en/07_Pruebas) | Public | |
| 7 | Implementation procedure | Reproducible installation, configuration, deployment and operation verification steps. | [09_Implementacion.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/09_Implementacion.md) | Public | |
| 8 | Corrective, preventive and improvement actions | Findings, priority, owner, action taken and closing evidence. | [08_Calidad_Mejoras.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/08_Calidad_Mejoras.md) | Public | |
| 9 | Technical, installation and user manual | Prerequisites, configuration, use of features and troubleshooting of common problems. | [10_Manual_Tecnico.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/10_Manual_Tecnico.md) · [11_Manual_Instalacion.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/11_Manual_Instalacion.md) · [12_Manual_Usuario.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/12_Manual_Usuario.md) | Public | |
| 10 | Project article | Problem, objectives, solution, methodology, results and conclusions. | [13_Articulo_Proyecto.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/13_Articulo_Proyecto.md) | Public | |
| 11 | Deployed application or demo | Access URL to the application or demo environment and instructions to verify features. | [Prototipo en Figma](https://www.figma.com/design/iuw3YMS7t81m3hIKMAvtHf/Tu-Evento?node-id=0-1&p=f&t=oc9DtpInYNo1rffd-0) | Public | Deployment URL pending registration once available. |
| 12 | Traceability and integration of evidence | Relationship between requirements, user stories, implemented modules, tests and changes or versions. | [Matriz_de_Trazabilidad_TuEvento.md](https://github.com/TheJhampierBoy/TuEvento-Docs/blob/main/en/14_Anexos/Matriz_de_Trazabilidad_TuEvento.md) | Public | |

**Important:** Do not include real passwords in this document. If the application requires authentication, describe the secure procedure for the evaluator to obtain the test credentials.

---

## 6. Accessibility and quality checklist

Check each item after verifying it:

- [X] All links open the correct resource.
- [X] There are no 404 errors, access denials or unresolved permission requests.
- [X] The documents can be read and their images, diagrams and tables are legible.
- [X] The repository allows identifying the project, its branches and the delivered version.
- [X] The evidence matches the actual state of the software.
- [ ] Simulated screens or results are not presented as if they were implemented features.
- [X] The deployed application starts and allows verifying the main features.
- [X] The documentation, the repository and the application match in names, features and version.
- [X] No credentials, sensitive data or private information are exposed.
- [X] The document includes the project name, team, update date and direct links.
- [X] The links were verified with the access level declared in the matrix.
- [X] The exported PDF keeps the links and its format is legible.

---

## 7. Acceptance criteria

| Criterion | Compliance condition | Result / observations |
|---|---|---|
| Completeness | All applicable evidence is recorded and those that do not apply are justified. | |
| Accessibility | Each link was tested with the declared access level. | |
| Traceability | It is possible to relate the important requirements to their implementation and their tests. | |
| Consistency | The documents match the repository and the operation of the application. | |
| Security | No secrets or data that should not be public are exposed. | |
| Presentation | The document is organized, legible and contains identifiable links. | |

---

## 8. Delivery

Suggested Markdown file name: `Enlaces_Evidencias_Proyecto_TuEvento.md`  
Suggested PDF name: `Enlaces_Evidencias_Proyecto_TuEvento_2026-10.pdf`  
Delivery channel: the one indicated by the instructor.  
Team responsibility: keep the links updated during the project iterations and replace those that change location.
