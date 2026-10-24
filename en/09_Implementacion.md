---
title: "Implementation"
lang: en
documents: [TE-0155]
status: borrador
---
# Implementation — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [Implementation manual](#doc-te-0155)

---

<a id="doc-te-0155"></a>

<!--
ruta_anterior: en/07_Implementacion/Manual_de_Implementacion_TuEvento.md
id: TE-0155
title: "Manual_de_Implementacion_TuEvento"
lang: en
source: 07_Implementacion/Manual_de_Implementacion_TuEvento.pdf
source_sha256: 09483490d39a2e4b8e0d40b4e5cde562be9d5e3c01d0e7bf07d3a7cc3c512f62
conversion: "pdfplumber 0.11.10 + converter for untagged PDF (method C, pilot 3); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Page header or footer omitted on pages 1–20: «{n}»."
  - "Page 4: figure included as an image (pagina-04-figura-1.png); its text (42 words) goes in a non-visible HTML comment, grouped by box ([...]) from top to bottom and from left to right; arrows and relationships are only in the image."
  - "Page 11: figure included as an image (pagina-11-figura-1.png); its text (7 words) goes in a non-visible HTML comment, grouped by box ([...]) from top to bottom and from left to right; arrows and relationships are only in the image."
  - "Pages 11: diagram boxes with text (which pdfplumber detects as one-row tables) included in the crop of the figure."
  - "PDF generated without LaTeX: hyphens at the end of a line are real hyphens and are kept when joining lines (they are not syllabic line-break hyphens)."
  - "11 ReportLab bullets without a Unicode mapping (Helvetica code 127, «(cid:127)» in the extraction) written as «•», which is how they look in the original."
  - "Manual table of contents (pages 2): the page numbers of the original are kept and the leader lines are removed."
  - "Tables with merged cells in HTML (colspan/rowspan calculated from the geometry of the borders); column widths, backgrounds and border thickness are not kept."
  - "Bold, italics and monospaced font are kept; sizes, colours, alignment and indentation are not."
  - "Automatic check against pdftotext: coverage 99.92%, precision 99.25%, order 99.04%; missing {'URL': 1, 'DEL': 1, 'REPOSITORIO': 1} (explained above)."
  - "Differences in the check explained: «URL DEL REPOSITORIO» is in the Markdown as `<URL_DEL_REPOSITORIO>` inside code, which the checker removes as an HTML tag; the «extra» words are the text of the figures, which goes in HTML comments. Text with double line spacing (APA): paragraphs are rebuilt from the first-line indentation."
  - "The 11 «•» bullets of the original are in the Markdown as list elements; the checker also counts a small shape of the diagram on page 4 as a bullet (12)."
  - "Translation: the code (commands, comments inside the commands, variable names, file names and URLs) is kept as in the original."
  - "Translation: the HTML comments with the text of the figures keep the original text and add the English translation after «EN:»."
  - "Translation: the APA citations are translated («s. f.» → «n.d.», «Recuperado el … de» → «Retrieved … from»); the titles of the cited works are not translated."
  - "Translation: the line breaks (<br>) of the Spanish text are kept at approximately the same position; in English they do not match the line ends of the original."
status: borrador
reviewed_by: ""
translation_of: es/09_Implementacion.md#doc-te-0155
es_sha256: 2e17860262cf60d46692d314c6695eae501d7a67e0e293713489b4a5d0392f49
-->

# Implementation manual of the Tu Evento system

Jhampier Santos Ortiz and Cristofer David Lozano Contreras

Servicio Nacional de Aprendizaje (SENA; National Learning Service)

Sede de la Industria y los Servicios, Neiva, Huila

Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development)

Instructor: Carlos Julio Cadena

9 October 2026

# Contents

Introduction 3

System architecture 3

Overview 3

Requirements 5

Hardware 5

Software 6

Ports 6

Obtaining the code and environment variables 7

Deployment with Docker Compose 9

Services and startup order 9

Migrations and initial administrator 11

Stopping and restarting 11

Deployment on Kubernetes 12

Continuous integration with GitHub Actions and SonarQube Cloud 13

Local development 15

Backend 15

Web frontend 15

Mobile application 15

Building the mobile application 16

System verification 16

Security 17

Troubleshooting 18

Known limitations 18

References 20

# Implementation manual of the Tu Evento system

# Introduction

This manual describes the procedure to install, configure, deploy and verify the Tu Evento system, an event management platform aimed at end users, organizers and administrators. It is intended for those who must put the system into operation, either on a development machine using Docker Compose or on a Kubernetes cluster.

The information was checked against the configuration files of the project repository (Santos Ortiz and Lozano Contreras, 2026), in particular the `docker-compose.yml,` file, the manifests in the `k8s/,` folder, the `.github/workflows/ci.yml` workflow and the Spring Boot configuration files. For security reasons, the document does not contain secret values: each credential is identified only by the name of its environment variable.

# System architecture

## Overview

Tu Evento follows a client-server architecture. The backend, developed with Spring Boot (Spring, n.d.), is a monolithic application that exposes a REST API and relies on auxiliary services: PostgreSQL for data persistence (PostgreSQL Global Development Group, n.d.), Redis as a cache (Redis Ltd., n.d.) and MinIO for object storage (MinIO, Inc., n.d.). Figure 1 presents the relationship between the components and the ports published in the development environment, and Table 1 summarizes the function of each one.

**Figure 1**<br>
*General architecture of the Tu Evento system*

![Figure on page 4](../_assets/07_Implementacion/Manual_de_Implementacion_TuEvento/pagina-04-figura-1.png)

<!-- Texto dentro de la figura (página 4): [Navegador web] [App móvil React Native, Expo] [Frontend web React + Nginx :3000] [Backend Spring Boot :8080 API REST, JWT, OAuth2, WebSockets, Liquibase] [Servicios externos SMTP, OAuth2 SightEngine] [PostgreSQL :5434] [Redis :6379] [MinIO :9000] [Pasarela simulada :4001] [PostgreSQL :5435] [fuera de cajas] Clasificador NSFW :8001 EN: Text inside the figure (page 4): [Web browser] [Mobile app React Native, Expo] [Web frontend React + Nginx :3000] [Backend Spring Boot :8080 REST API, JWT, OAuth2, WebSockets, Liquibase] [External services SMTP, OAuth2 SightEngine] [PostgreSQL :5434] [Redis :6379] [MinIO :9000] [Simulated gateway :4001] [PostgreSQL :5435] [outside boxes] NSFW classifier :8001 -->

<table>
<tr>
<td></td>
</tr>
<tr>
<td colspan="2"><strong>NSFW classifier</strong> :8001</td>
</tr>
</table>

*Note.* Diagram of our own elaboration based on the project's docker-compose.yml file. The arrows indicate the direction of the requests; the numbers preceded by a colon correspond to the ports published on the host machine. The external services (SMTP email, OAuth2 providers and SightEngine) are represented with a dashed border.

**Table 1**<br>
*System components*

| **Component** | **Technology** | **Function** |
|---|---|---|
| Backend | Spring Boot 3.5, Java 21 | REST API, business logic, security (JWT and OAuth2), WebSockets and migrations with Liquibase. |
| Web frontend | React 18, Vite 5 | Web interface; in a container it is served with Nginx. |
| Mobile frontend | React Native 0.81, Expo SDK 54 | Application for Android and iOS. |
| Database | PostgreSQL 17 | Data persistence of the backend. |
| Cache | Redis 7 | Cache and session data. |
| Object storage | MinIO | Profile pictures, event media and organizer documents. |
| Image moderation | NSFW service (Python 3.11) and SightEngine | Classification of the content before storing it. |
| Payment gateway | fake-payment-gateway (Java 21) | Sandbox gateway for testing the payment flow, with its own PostgreSQL database. |
| Continuous integration | GitHub Actions and SonarQube Cloud | Testing, building and code quality analysis. |

*Note.* Our own elaboration based on the project's pom.xml, package.json and docker-compose.yml files.

# Requirements

## Hardware

The complete stack runs nine containers, among them an image classification<br>
model. Table 2 indicates the recommended resources for the host<br>
machine.<br>
**Table 2**<br>
*Recommended resources of the host machine*

| **Resource** | **Minimum** | **Recommended** |
|---|---|---|
| RAM memory | 8 GB | 16 GB (complete stack) |
| Processor | 4 cores | 6 cores or more |
| Free storage | 20 GB | 40 GB |
| Operating system | Windows 10/11 with WSL2, Ubuntu 20.04 or later, macOS | Ubuntu 22.04 LTS |
| Network | Internet access to download images and dependencies | Same |

*Note.* The values are operating recommendations of the development team and must be adjusted to the real load.

## Software

The necessary tools depend on the work scenario, as detailed in<br>
Table 3.<br>
**Table 3**<br>
*Software tools according to the scenario*

| **Scenario** | **Necessary tools** |
|---|---|
| Deployment with Docker Compose | Docker Engine, Docker Compose v2 and Git. |
| Backend development | JDK 21 and Maven (the project includes the Maven Wrapper, `mvnw).` |
| Web frontend development | Node.js 20 and npm. |
| Mobile frontend development | Node.js 20, npm and EAS CLI 22.2.0 or later; Android Studio or Xcode for emulators (optional). |
| Deployment on Kubernetes | kubectl and a cluster with the Ingress NGINX controller, cert-manager and metrics-server. |

## Ports

The ports published on the host machine by each service are listed in Table 4.<br>
They must be free before starting the system.<br>
**Table 4**<br>
*Ports published by the services*

| **Port** | **Service** |
|---|---|
| 3000 | Web frontend (Nginx in Docker) |
| 5173 | Web frontend in development mode (Vite) |
| 8080 | Backend (API) |
| 5434 | PostgreSQL of the backend (port 5432 inside the container) |
| 5435 | PostgreSQL of the sandbox gateway (port 5432 inside the container) |
| 6379 | Redis |
| 9000 and 9001 | MinIO (API and web console) |
| 8001 | NSFW classification service |
| 4001 | Sandbox payment gateway |

*Note.* Source: the project's docker-compose.yml.

# Obtaining the code and environment variables

All the services are orchestrated from the `docker-compose.yml,` file, located at the root of the repository, and the variables are read from a `.env` file in that same folder, as indicated by the Docker Compose documentation (Docker Inc., n.d.). Code 1 shows how to obtain the code and create the variables file.

## Code 1

*Obtaining the code and creating the variables file*

| `git clone <URL_DEL_REPOSITORIO> TuEvento` `cd TuEvento` `cp .env.example .env` |
|---|

After creating the file, the variables of Table 5 must be completed with your own values; credentials from examples or from previous documents must not be reused.

**Table 5**<br>
*Environment variables defined in the .env.example file*

| **Variable** | **Description** |
|---|---|
| POSTGRES_DB, POSTGRES_USER, POSTGRES_PASSWORD | PostgreSQL database, user and password (shared with the sandbox gateway). |
| MAIL_USERNAME, MAIL_PASSWORD | Gmail SMTP account and its application password. |
| JWT_SECRET | Key to sign JWT tokens (at least 256 bits). |
| GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET | Google OAuth2 credentials. |
| VITE_GOOGLE_CLIENT_ID | Google Client ID used by the web frontend. |
| FACEBOOK_CLIENT_ID, FACEBOOK_CLIENT_SECRET | Facebook OAuth2 credentials. |
| ADMIN_EMAIL, ADMIN_PASSWORD, ADMIN_ALIAS | Data of the initial administrator created on the first startup. |
| MINIO_ROOT_USER, MINIO_ROOT_PASSWORD | MinIO root user and password (they also act as the access key). |
| REDIS_HOST, REDIS_PORT | Location of Redis. |
| SPRING_PROFILES_ACTIVE | Spring profile: dev, k8s or prod. |
| NSFW_SERVICE_URL, NSFW_THRESHOLD | Internal URL and threshold of the NSFW classifier. |
| SIGHTENGINE_API_USER, SIGHTENGINE_API_SECRET, SIGHTENGINE_MODELS, SIGHTENGINE_THRESHOLD | Additional moderation with SightEngine. |
| NOTIFICATION_EMAIL_ENABLED, NOTIFICATION_MAIL_HOST, NOTIFICATION_MAIL_PORT, NOTIFICATION_MAIL_USERNAME, NOTIFICATION_MAIL_PASSWORD | Email notifications. |

*Note.* Source: the project's .env.example file. No values are included.

In addition, the `docker-compose.yml` file and the Spring profiles use the variables of Table 6, which are not in `.env.example` and must be added to the `.env` file when applicable. The absence of `WEBHOOK_SECRET` prevents the sandbox gateway from starting correctly.

**Table 6**<br>
*Variables used that are not in .env.example*

| **Variable** | **Description** |
|---|---|
| WEBHOOK_SECRET | Secret to validate webhooks of the sandbox gateway; mandatory for the fake-payment-gateway service. |
| MINIO_PUBLIC_URL | MinIO URL accessible from the browser, used in presigned URLs. |
| PAYMENT_GATEWAY | Gateway selector; the value `fake` activates the sandbox gateway. |
| FAKE_GATEWAY_URL | URL of the sandbox gateway as seen from the backend. |
| SIGHTENGINE_NUDITY_THRESH OLD | Specific nudity detection threshold. |
| APP_CORS_ALLOWED_ORIGINS | Origins allowed by CORS (include http://localhost:3000 and http://localhost:5173). |
| APP_STORAGE_ENDPOINT | Internal MinIO endpoint to upload and delete files. |

*Note.* Source: the project's docker-compose.yml and application-dev.yml.

# Deployment with Docker Compose

This is the recommended method for development and test environments. All the commands of Code 2 are run from the root of the repository, which is where the `docker-compose.yml;` file is located, not from the backend folder.

## Code 2

*Starting the complete system with Docker Compose*

| `docker compose up --build -d` `docker compose ps` `docker compose logs -f backend` |
|---|

## Services and startup order

Docker Compose makes it possible to declare dependencies between services to control the startup order (Docker Inc., n.d.). Table 7 describes the nine services of the project and Figure 2 summarizes the dependencies that condition the startup of the backend and the frontend.

**Table 7**<br>
*Services defined in docker-compose.yml*

| **Service** | **Image or build** | **Ports** | **Depends on** |
|---|---|---|---|
| postgres | postgres:17-alpine | 5434:5432 | - |
| postgres-fake-gateway | postgres:17-alpine | 5435:5432 | - |
| redis | redis:7-alpine | 6379 | - |
| minio | quay.io/minio/minio | 9000, 9001 | - |
| minio-init | quay.io/minio/minio | - | minio (healthy) |
| nsfw-classifier | Local build (Python 3.11) | 8001:8000 | - |
| fake-payment-gateway | Local build (Java 21) | 4001 | postgres-fake-gateway |
| backend | Local build (Java 21) | 8080 | postgres, minio, redis, nsfw-classifier |
| frontend | Local build (Node 20 and Nginx) | 3000:80 | backend |

*Note.* Source: the project's docker-compose.yml.

**Figure 2**<br>
*Startup dependencies between services*

![Figure on page 11](../_assets/07_Implementacion/Manual_de_Implementacion_TuEvento/pagina-11-figura-1.png)

<!-- Texto dentro de la figura (página 11): [postgres] [postgres-fake-gateway] [fake-payment-gateway] [redis] [minio] [minio-init] [nsfw-classifier] EN: Text inside the figure (page 11): [postgres] [postgres-fake-gateway] [fake-payment-gateway] [redis] [minio] [minio-init] [nsfw-classifier] -->

<table>
<tr>
<td rowspan="2"><strong>backend</strong></td>
</tr>
<tr>
<td></td>
<td></td>
</tr>
</table>

### frontend

*Note.* Diagram of our own elaboration based on the depends_on clauses of the docker-compose.yml file. Each arrow goes from the service that must start first to the one that depends on it.

The `minio-init` container creates the `tuevento.` bucket. The prefixes `profile_picture/` and `event_media/` are public, while `organizer_document/` is private.

## Migrations and initial administrator

No manual step on the database is required. On startup, the backend automatically runs the Liquibase migrations (Liquibase, n.d.), more than ninety files located in `db/changelog/changes/,` which include the data of departments and cities. Afterwards, the `DataInitializer` component creates the administrator user from `ADMIN_EMAIL, ADMIN_PASSWORD` and `ADMIN_ALIAS,` only if it does not already exist.

## Stopping and restarting

Code 3 shows the commands to stop, restart or completely remove the environment. The `-v` option deletes the volumes and, therefore, the stored data.

## Code 3

*Stopping and restarting the environment*

| `docker compose down # detiene y elimina contenedores` `docker compose down -v # ademas elimina volumenes (borra datos)` `docker compose up -d # inicia nuevamente sin reconstruir` |
|---|

# Deployment on Kubernetes

The manifests are in the `k8s/.` folder. An active cluster is required with<br>
kubectl configured, an Ingress NGINX controller with cert-manager (issuer<br>
`letsencrypt-prod)` and metrics-server for autoscaling. The Ingress exposes the services<br>
through domains and TLS (The Kubernetes Authors, n.d.-b) and the HorizontalPodAutoscaler adjusts<br>
the number of replicas according to resource consumption (The Kubernetes Authors, n.d.-a). Table 8<br>
summarizes the defined resources.<br>
**Table 8**<br>
*Kubernetes manifests of the project*

| **Manifest** | **Resource** | **Detail** |
|---|---|---|
| secrets.yaml | Secret tu-evento-secrets | Credentials of the database, MinIO, JWT, OAuth, administrator and email. |
| configmap.yaml | ConfigMap tu-evento-config | prod profile, redis-service:6379 and postgres-service:5432. |
| deployment.yaml and service.yaml | Backend | Port 8080; service 80 to 8080, NodePort 30080. |
| frontend-deployment.yaml and frontend-service.yaml | Frontend | Port 80; NodePort 30081. |
| ingress.yaml | Ingress | api.tuevento.com and app.tuevento.com with TLS. |
| hpa.yaml | Autoscaling | Between 2 and 10 replicas of the backend; CPU 70 % and memory 80 %. |

*Note.* Source: the project's k8s/ folder.

The manifests must be applied in the order of Code 4.

## Code 4

*Ordered application of the manifests*

| `kubectl apply -f k8s/secrets.yaml` `kubectl apply -f k8s/configmap.yaml` `kubectl apply -f k8s/deployment.yaml` `kubectl apply -f k8s/service.yaml` `kubectl apply -f k8s/frontend-deployment.yaml` `kubectl apply -f k8s/frontend-service.yaml` `kubectl apply -f k8s/ingress.yaml` `kubectl apply -f k8s/hpa.yaml` `kubectl get pods` |
|---|

Three considerations must be taken into account. First, the manifests do not include PostgreSQL, Redis or MinIO, so these services must exist in the cluster with the names postgres-service, redis-service and minio-service. Second, the k8s profile has storage disabled (`app.storage.enabled=false),` so file upload will not be available until it is configured. Third, before applying `secrets.yaml` the example values must be replaced with your own values encoded in base64, and that file must not be versioned with real data.

# Continuous integration with GitHub Actions and SonarQube Cloud

Continuous integration runs on GitHub Actions, so it does not consume resources of the local machine. The `.github/workflows/ci.yml` workflow defines the process as code (GitHub, Inc., n.d.) and runs on every push or pull request to the `main` and `develop` branches, or manually. Its three jobs are described in Table 9.

**Table 9**<br>
*Jobs of the continuous integration workflow*

| **Job** | **Action** |
|---|---|
| Backend (tests + SonarQube) | With Java 17, runs ./mvnw -B verify in TuEventoBackend/tu-evento, which runs the tests and generates the coverage report with JaCoCo; it then sends the analysis to SonarQube Cloud. |
| Web (build) | With Node.js 22, runs npm ci and npm run build in TuEventoFrontend/web. |
| Móvil (bundle Expo) | With Node.js 22, runs npm ci and npx expo export --platform android in TuEventoFrontend/movil. |

*Note.* Source: the project's .github/workflows/ci.yml.

SonarQube Cloud analyzes the code of the backend, the web and the mobile application to detect bugs, vulnerabilities and duplicated code, and measures the test coverage of the backend (SonarSource, n.d.). The configuration is in the `sonar-project.properties` file at the root and the access token is stored in the repository secret `SONAR_TOKEN`; if the token is not available, the analysis is skipped. The results can be viewed at https://sonarcloud.io/project/overview?id=lozano2303_TuEvento.

The workflow does not build or publish Docker images and does not deploy to Kubernetes; therefore, the deployment must be carried out manually as indicated in the section Deployment on Kubernetes.

# Local development

## Backend

First the infrastructure is started with Docker Compose and then the backend is run with the `dev` profile and the exported environment variables, as shown in Code 5. The file generated by the packaging is `tu-evento-0.0.1-SNAPSHOT.jar.`

## Code 5

*Running the backend in development mode*

| `docker compose up -d postgres redis minio minio-init nsfw-classifier` `cd TuEventoBackend/tu-evento` `./mvnw clean package -DskipTests` `./mvnw spring-boot:run` `# o bien:` `java -jar target/tu-evento-0.0.1-SNAPSHOT.jar` |
|---|

## Web frontend

The frontend uses Vite (Vite, n.d.). In development mode it is normally served on port 5173, while port 3000 corresponds to the container with Nginx. The `VITE_API_URL` variable defines the API address and, in development, its value is `http://localhost:8080/api.` Code 6 summarizes the commands.

## Code 6

*Running and building the web frontend*

| `cd TuEventoFrontend/web` `npm install` `npm run dev # Vite, normalmente en http://localhost:5173` `npm run build # genera la carpeta dist` |
|---|

## Mobile application

The variable that points to the backend is `EXPO_PUBLIC_API_URL.` Expo only includes in the application bundle the variables whose name starts with `EXPO_PUBLIC_` (Expo, n.d.-a). On a physical device or emulator, `localhost,` must not be used, but rather the IP address of the machine that runs the backend (in the Android emulator, 10.0.2.2). The commands are shown in Code 7.

## Code 7

*Running the mobile application in development*

| `cd TuEventoFrontend/movil` `npm install` `npx expo start` `npx expo run:android` `npx expo run:ios # solo en macOS` |
|---|

## Building the mobile application

The build is done with EAS Build (Expo, n.d.-b), configured in `eas.json;` it requires EAS CLI 22.2.0 or later and an Expo account. The `preview` profile generates an APK for internal distribution and the `production` profile generates an AAB bundle for the store. The `expo build:android` and `expo build:ios` commands are obsolete and do not work with Expo SDK 54.

## Code 8

*Building the mobile application with EAS*

| `npm install -g eas-cli` `eas login` `eas build --platform android --profile preview # APK interno` `eas build --platform android --profile production # AAB para tienda` |
|---|

# System verification

Once the services have started, their status is confirmed with the addresses of Table 10. The backend exposes the health and metrics endpoints through Spring Boot Actuator (Spring, n.d.), which are also used by the Kubernetes probes.

**Table 10**<br>
*Verification addresses*

| **Address** | **Description** |
|---|---|
| http://localhost:8080/actuator/health | Status of the backend. |
| http://localhost:8080/actuator/metrics | Application metrics. |
| http://localhost:8080/swagger-ui | Interactive API documentation. |
| http://localhost:8080/api-docs | OpenAPI specification in JSON. |
| http://localhost:3000 | Web frontend. |
| http://localhost:9000/minio/health/live | Status of MinIO. |
| http://localhost:9001 | MinIO web console. |
| http://localhost:8001/health | Status of the NSFW classifier. |
| http://localhost:4001 | Sandbox payment gateway. |

*Note.* Source: the project's docker-compose.yml and application-dev.yml.

As a final functional test, open the web frontend and log in with the credentials defined in `ADMIN_EMAIL` and `ADMIN_PASSWORD.`

# Security

- Credentials, keys and tokens must not be recorded in this manual, in the repository or in screenshots; only the `.env,` file is used, which must not be versioned, or the Kubernetes Secrets.
- The `JWT_SECRET` must be random, of at least 256 bits, and each service must have different passwords.
- Any credential that has appeared in previous versions of the documentation (SMTP password, OAuth secrets, database password) must be considered compromised and rotated.
- The `APP_CORS_ALLOWED_ORIGINS` variable must contain only the necessary origins.
- In production, the ports of PostgreSQL, Redis and MinIO must not be exposed to the Internet; only the frontend and the API, through the Ingress with TLS.
- Specific versions of the images must be pinned, for example that of MinIO, which uses the `latest,` tag, to achieve reproducible deployments.
# Troubleshooting

Table 11 gathers the most frequent symptoms and the recommended action.

**Table 11**<br>
*Frequent problems and recommended actions*

| **Symptom** | **Probable cause and action** |
|---|---|
| The backend does not start | Verify that PostgreSQL, Redis, MinIO and the NSFW classifier are healthy (docker compose ps), review docker compose logs backend and confirm that port 8080 is free. |
| Database connection error | Review POSTGRES_DB, POSTGRES_USER and POSTGRES_PASSWORD in .env. From the host machine, PostgreSQL is exposed on port 5434, not on 5432. |
| The payment gateway fails | Verify that WEBHOOK_SECRET is defined in .env. |
| Images do not load | Review MINIO_PUBLIC_URL and that minio-init has created the tuevento bucket. |
| CORS error in the browser | Include the frontend origin in APP_CORS_ALLOWED_ORIGINS (3000 in Docker, 5173 with Vite). |
| Login with Google or Facebook fails | Check the OAuth2 credentials and that the redirect URIs match those registered with each provider. |
| The mobile app does not connect to the backend | Verify that EXPO_PUBLIC_API_URL uses the IP of the machine and not localhost; restart with npx expo start -c. |
| The web frontend does not build | Use Node.js 20; delete node_modules and run npm install. |

# Known limitations

- The payment gateway is a sandbox for testing the payment flow: the fake-payment-gateway service simulates the charges and notifies the result to the backend through a signed webhook, without processing real payments.
- Storage uses MinIO; the `s3_key` column of the files table keeps that name for historical reasons and there is no dependency on AWS S3.
- In Kubernetes, storage is disabled and the data services are not included in the manifests.
- Continuous integration does not build Docker images or deploy; deployment is manual.
- The indicated hardware resources are recommendations and must be adjusted to the real load.
# References

Docker Inc. (n.d.). *Docker Compose overview.* Retrieved 9 October 2026, from

https://docs.docker.com/compose/

Expo. (n.d.-a). *Environment variables in Expo.* Retrieved 9 October 2026, from

https://docs.expo.dev/guides/environment-variables/

Expo. (n.d.-b). *Introduction to EAS Build.* Retrieved 9 October 2026, from

https://docs.expo.dev/build/introduction/

GitHub, Inc. (n.d.). *Understanding GitHub Actions.* Retrieved 23 October 2026, from

https://docs.github.com/en/actions/about-github-actions/understanding-github-actions

Liquibase. (n.d.). *Liquibase documentation.* Retrieved 9 October 2026, from

https://docs.liquibase.com/

MinIO, Inc. (n.d.). *MinIO object storage documentation.* Retrieved 9 October 2026, from

https://min.io/docs/minio/linux/index.html

PostgreSQL Global Development Group. (n.d.). *PostgreSQL 17 documentation.* Retrieved 9

October 2026, from https://www.postgresql.org/docs/17/

Redis Ltd. (n.d.). *Redis documentation.* Retrieved 9 October 2026, from

https://redis.io/docs/

Santos Ortiz, J. and Lozano Contreras, C. D. (2026). *Tu Evento: Plataforma de gestión de eventos*

[Software]. Repository of the training project.

SonarSource. (n.d.). *SonarQube Cloud documentation.* Retrieved 23 October 2026, from

https://docs.sonarsource.com/sonarqube-cloud/

Spring. (n.d.). *Spring Boot reference documentation.* Retrieved 9 October 2026, from

https://docs.spring.io/spring-boot/index.html

The Kubernetes Authors. (n.d.-a). *Horizontal Pod Autoscaling.* Retrieved 9 October

2026, from https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/ The Kubernetes Authors. (n.d.-b). *Ingress.* Retrieved 9 October 2026, from

https://kubernetes.io/docs/concepts/services-networking/ingress/

Vite. (n.d.). *Getting started.* Retrieved 9 October 2026, from https://vite.dev/guide/
