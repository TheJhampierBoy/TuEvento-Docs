# Glosario ES → EN — Tu Evento

| Campo | Valor |
|---|---|
| Proyecto | Tu Evento — CapySoft |
| Fecha | 2026-10-23 |
| Versión | 0.1 (propuesta, pendiente de aprobación) |
| Uso | Traducción fija de `es/` a `en/`. La comprobación automática de consistencia lee las tablas de las secciones 2 a 9 (columnas «Español», «Inglés» y «Variantes EN no permitidas»). |

## 1. Cómo se aplica

1. La traducción de la columna «Inglés» es **obligatoria** cada vez que el término español aparece con ese sentido. Las variantes de la última columna no se usan.
2. Cuando un término español tiene varios sentidos, hay una fila por sentido y la columna «Contexto» dice cuándo aplica cada una.
3. Varios términos españoles pueden ir a la misma traducción (p. ej. *silla* y *asiento* → *seat*). La distinción se pierde y no se anota como pérdida, salvo que el documento la use a propósito.
4. Las mayúsculas siguen el original: si el español escribe un título en mayúscula inicial, el inglés también (no se aplica *Title Case* que el original no tenga).
5. Las siglas que forman parte de identificadores (`HU-001`, `RF1`, `RNF…`, `CP-AUT-01`) **no cambian**, ni en el identificador ni en el texto. La primera vez que aparece la sigla en un documento se explica en inglés (ver sección 2).

## 2. Siglas e identificadores

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| HU (historia de usuario) | HU (user story) | La sigla se conserva porque es el prefijo de los identificadores `HU-001`… | US, UST |
| RF (requerimiento funcional) | RF (functional requirement) | La sigla se conserva por los identificadores `RF1`… | FR |
| RNF (requerimiento no funcional) | RNF (non-functional requirement) | La sigla se conserva por los identificadores | NFR |
| CP (caso de prueba) | CP (test case) | Solo en identificadores `CP-…` | TC |
| SRS / ERS | SRS / ERS | ERS es la sigla española de SRS; se conserva | — |
| ADSO | ADSO | Sigla del programa del SENA; ver sección 10 | — |
| MER (modelo entidad-relación) | MER (entity-relationship model) | La sigla se conserva por los nombres de carpeta y archivo | ERD |
| DDD, JWT, QR, OAuth, API, CRUD, DTO, UI, UX | sin cambio | Siglas ya en inglés | — |

## 3. Requisitos y análisis

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| historia de usuario | user story | — | user history |
| requerimiento funcional / requisito funcional | functional requirement | Ambas formas españolas van a la misma | — |
| requerimiento no funcional / requisito no funcional | non-functional requirement | — | nonfunctional requirement |
| especificación de requerimientos (de software) | (software) requirements specification | — | — |
| caso de uso | use case | — | — |
| actor | actor | — | — |
| épica | epic | — | — |
| criterio de aceptación / criterios de aceptación | acceptance criterion / acceptance criteria | — | acceptance criterions |
| precondición | precondition | — | pre-condition |
| postcondición | postcondition | — | post-condition |
| flujo principal / flujo alterno | main flow / alternate flow | — | basic flow, alternative flow |
| manejo de situaciones anormales | handling of abnormal situations | Campo de las fichas RF del SRS | — |
| documentos de visualización asociados | associated display documents | Campo de las fichas RF del SRS | — |
| requerimiento que lo utiliza o especializa | requirement that uses or specializes it | Campo de las fichas RF del SRS | — |
| entrada / salida (de un RF) | input / output | Campos «Entrada:» y «Salida:» de las fichas RF | entry, exit |
| ¿Crítico? Sí / No | Critical? Yes / No | Fichas RF | — |
| tipo: necesario / deseable / opcional | type: necessary / desirable / optional | Fichas RF | — |
| prioridad alta / media / baja | high / medium / low priority | También en casos de prueba | — |
| ficha (de un RF en el SRS) | requirement card | Cuadro de cada RF del SRS | requirement sheet |
| alcance | scope | — | reach |
| interesado(s) / stakeholder | stakeholder(s) | — | interested party |
| trazabilidad / matriz de trazabilidad | traceability / traceability matrix | — | — |
| levantamiento / recolección de datos | data collection | — | data gathering |
| encuesta / entrevista | survey / interview | — | poll |
| vigilancia tecnológica | technology watch | — | technological surveillance |
| cuadro comparativo | comparison table | — | comparative chart |
| propuesta técnica | technical proposal | — | — |
| ficha técnica | technical data sheet | — | technical card |
| documento de aceptación de requisitos | requirements acceptance document | — | — |

## 4. Dominio: usuarios y roles

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| usuario | user | — | — |
| usuario anónimo | anonymous user | — | guest |
| asistente | attendee | Persona que asiste o compra; rol por defecto | assistant, participant |
| organizador | organizer | — | organiser, promoter |
| administrador | administrator | En texto; `ADMIN` como valor de enum no cambia | admin (en prosa) |
| rol / roles | role / roles | — | — |
| solicitud de organizador / petición de organizador | organizer request | Ambas formas españolas; `OrganizerPetition…` en código no cambia | organizer petition (en prosa) |
| perfil | profile | — | — |
| cuenta | account | — | — |
| registro (de usuario) | registration | Acción de crear cuenta | sign-up, record |
| registro (de datos, fila) | record | Fila de base de datos o bitácora | registration |
| activación (de cuenta) | (account) activation | — | — |
| inicio de sesión / iniciar sesión | login / log in | Sustantivo / verbo | sign in, sign-in |
| cerrar sesión | log out | — | sign out |
| contraseña | password | — | passcode |
| recuperar / restablecer contraseña | recover / reset password | — | — |
| correo electrónico / correo | email | — | e-mail, mail |
| código de verificación | verification code | — | — |
| redes sociales | social networks | — | social media |

## 5. Dominio: eventos, recinto y asientos

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| evento | event | — | show |
| crear / publicar / editar evento | create / publish / edit event | — | — |
| borrador (estado) | draft | Estado de evento u orden; `DRAFT` no cambia | — |
| en revisión | under review | Estado | in review |
| publicado | published | Estado | — |
| rechazado | rejected | Estado | denied |
| cancelado / cancelación | cancelled / cancellation | Grafía británica, igual que el enum `CANCELLED` | canceled |
| finalizado | finished | Estado; `COMPLETED` no cambia | — |
| silla / asiento | seat | Ambas formas españolas | chair |
| sección | section | Zona con capacidad y precio propios (General, VIP, Palco, Tribuna) | area |
| General, VIP, Palco, Tribuna | General, VIP, Box, Stand | Nombres de sección del ejemplo | — |
| plano (del recinto/evento) | floor plan | Diseño de secciones y sillas | map, blueprint |
| mapa de asientos / mapa del recinto | seat map / venue map | — | — |
| layout | layout | Ya en inglés; en código (`EventLayout`) no cambia | — |
| maquetación / maquetar | layout design / design the layout | — | mock-up, mockup (como traducción de maquetación) |
| recinto | venue | — | enclosure, precinct |
| sitio (lugar físico, `Location`) | site | Módulo «Categorías y sitios» | venue |
| lugar (del evento) | location | — | place |
| capacidad | capacity | De sección o sitio | — |
| aforo | maximum attendance | Límite de asistentes del evento | capacity |
| categoría | category | — | — |
| ubicación / geolocalización | location / geolocation | — | — |
| departamento / ciudad | department / city | División administrativa de Colombia | state, province |
| calificación / valoración | rating | — | score, assessment |
| comentario | comment | — | review |
| reseña | review | — | — |
| moderación / moderar | moderation / moderate | — | — |
| recordatorio | reminder | — | — |
| notificación (push) | (push) notification | — | — |
| tema (de interfaz) | theme | — | topic, subject |
| idioma | language | — | idiom |
| panel de control / dashboard | dashboard | Ambas formas españolas | control panel |
| filtro / búsqueda | filter / search | — | — |

## 6. Dominio: compra, pagos y cartera

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| boleta / boleto / ticket / entrada (de un evento) | ticket | Todas las formas españolas | admission, voucher |
| boletería | ticketing | — | box office |
| reserva / reservación / reservar | reservation / reserve | — | booking, book |
| orden | order | — | — |
| carrito | cart | — | basket |
| compra / comprar | purchase / buy | — | — |
| pago / pagar | payment / pay | — | — |
| pago simulado | simulated payment | — | mock payment |
| pasarela de pagos / pasarela de pago | payment gateway | — | payment portal |
| reembolso | refund | — | reimbursement |
| cartera / cartera interna / billetera / wallet | wallet / internal wallet | Todas las formas españolas | purse |
| saldo | balance | — | credit |
| saldo compensatorio | compensatory balance | — | — |
| crédito (del wallet) | credit | Como en «wallet de crédito» | — |
| retiro / retirar (saldo) | withdrawal / withdraw | — | — |
| comisión | commission | — | fee |
| precio / tarifa | price / rate | — | — |
| comprobante (de reserva, de compra) | proof (of reservation, of purchase) | — | receipt |
| validación de asistencia | attendance validation | — | — |
| control de acceso / ingreso (al evento) | access control / entry | — | — |
| ingresos (dinero) | revenue | Solo en sentido económico | income |
| control financiero | financial control | — | — |
| idempotencia | idempotency | — | idempotence |

## 7. Pruebas y calidad

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| plan de pruebas | test plan | — | testing plan |
| caso de prueba / casos de prueba | test case / test cases | — | — |
| tipo de prueba | test type | — | — |
| positivo / negativo / límite | positive / negative / boundary | Tipo de caso de prueba | limit, edge |
| pasos | steps | — | — |
| datos de entrada | input data | — | entry data |
| resultado esperado | expected result | — | — |
| resultado obtenido | actual result | — | obtained result |
| estado (de ejecución) | status | — | state |
| aprobado / fallido / bloqueado / pendiente | passed / failed / blocked / pending | Estado de ejecución de un caso de prueba | approved (en este sentido) |
| aprobado / aprobación | approved / approval | Aprobación de una solicitud o un evento | passed (en este sentido) |
| responsable | owner | Columna de casos de prueba | responsible |
| observaciones | remarks | — | observations |
| criterios de entrada / salida / suspensión | entry / exit / suspension criteria | — | — |
| hallazgo | finding | — | — |
| defecto / incidencia | defect / issue | — | bug (como traducción) |
| severidad | severity | — | — |
| riesgo / matriz de riesgos | risk / risk matrix | — | — |
| probabilidad / impacto / mitigación | probability / impact / mitigation | — | likelihood |
| entorno de pruebas | test environment | — | — |
| lista de chequeo | checklist | — | check list |
| calidad de software | software quality | — | — |
| acción correctiva / preventiva / de mejora | corrective / preventive / improvement action | — | preventative |

## 8. Diseño, implementación y manuales

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| diagrama de clases | class diagram | — | — |
| diagrama de secuencia | sequence diagram | — | — |
| diagrama de estados | state diagram | — | statechart |
| diagrama de actividades | activity diagram | — | — |
| diagrama de flujo | flowchart | — | flow diagram |
| diagrama de procesos | process diagram | — | — |
| diccionario de datos | data dictionary | — | — |
| modelo entidad-relación | entity-relationship model | — | — |
| patrón de diseño / patrones de diseño | design pattern / design patterns | — | — |
| arquitectura N-capas | N-tier architecture | — | N-layer |
| microservicio | microservice | — | — |
| despliegue | deployment | — | — |
| implementación | implementation | Fase o manual de implementación | deployment |
| manual técnico / manual de usuario | technical manual / user manual | — | — |
| prototipo / mockup / mapa del sitio | prototype / mockup / site map | — | sitemap |
| términos y condiciones | terms and conditions | — | — |
| interfaz | interface | — | — |
| almacenamiento | storage | — | — |
| repositorio | repository | — | — |
| control de versiones / historial de revisión | version control / revision history | Tablas iniciales de los documentos | — |
| tabla de contenido / índice | table of contents / index | — | — |
| anexo | annex | — | appendix |
| integrantes | team members | — | integrants |
| versión inicial | initial version | — | — |

## 9. Proyecto formativo y metodología

| Español | Inglés | Contexto | Variantes EN no permitidas |
|---|---|---|---|
| ficha (del SENA) | ficha (training group) | Número de grupo del SENA. La primera vez en cada documento: «Ficha (training group): 3145556»; después, «ficha» | file, card, sheet |
| aprendiz | apprentice | Estudiante del SENA | trainee, student |
| instructor / instructora | instructor | — | teacher, professor |
| tecnólogo | technologist | Nivel de formación del SENA | technician |
| proyecto formativo | training project | — | formative project |
| fase | phase | — | stage |
| entregable | deliverable | — | — |
| equipo | team | — | — |
| líder del equipo | team leader | — | — |
| metodología | methodology | — | — |
| planificación | planning | — | planification |
| sprint, backlog, product owner, scrum master, daily | sin cambio | Términos de Scrum ya en inglés | — |
| cronograma | schedule | — | timeline (salvo en el nombre de archivo `TimeLine`) |

## 10. Lo que NO se traduce

### 10.1 Nombres propios

Se conservan en español. Se puede añadir la traducción entre paréntesis **solo la primera vez** que aparecen en cada documento.

| Nombre | Primera aparición en inglés |
|---|---|
| Tu Evento / TuEvento / Tu evento (se respeta la grafía de cada documento) | sin traducción |
| CapySoft | sin traducción |
| SENA | SENA |
| Servicio Nacional de Aprendizaje | Servicio Nacional de Aprendizaje (National Learning Service) |
| Tecnólogo en Análisis y Desarrollo de Software | Tecnólogo en Análisis y Desarrollo de Software (Technologist in Software Analysis and Development) |
| Análisis y Desarrollo de Software (ADSO) | Análisis y Desarrollo de Software (ADSO; Software Analysis and Development) |
| Número de ficha `3145556` | sin cambio |
| Personas: Jhampier Santos Ortiz, Cristofer David Lozano Contreras (y sus formas abreviadas), Karol Daniela Correa, Carlos Julio Cadena, Edwin Mauricio y cualquier otro nombre de persona | sin traducción |
| Correos institucionales (`…@soy.sena.edu.co`) y usuarios (`JhampierBoy`) | sin cambio |
| Productos y servicios: Wompi, Spring Boot, React, React Native, Expo, PostgreSQL, AWS, Figma, Canva, Google, Facebook, etc. | sin cambio |
| Nombres de documentos citados como título (p. ej. «Documento de Especificación de Requerimientos (SRS)») | Se traducen como texto; si se citan como **nombre de archivo**, no |

### 10.2 Código y datos técnicos (idénticos carácter por carácter)

- Bloques de código (```` ``` ````), incluidos los bloques `text` de OCR y los bloques SQL.
- Código en línea (`` `…` ``), endpoints y rutas (`/api/v1/auth/register`, `POST /register`), métodos HTTP y códigos de estado (`201`, `400`).
- Nombres de clases, métodos, campos, variables y tablas (`OrganizerPetitionController`, `fullName`, `sectionId`).
- Códigos de error (`INVALID_CURRENT_PASSWORD`, `INVALID_EMAIL`) y valores de enum (`ORGANIZER`, `ADMIN`, `USER`, `DRAFT`, `PUBLISHED`, `CANCELLED`, `COMPLETED`, `PAYMENT_PENDING`).
- Identificadores de documento: `HU-001`, `RF1`, `CP-AUT-01`, `TE-0007`.
- Datos de prueba (correos, contraseñas de ejemplo, nombres ficticios como `Juan` o `Ju4n P3r3z`, valores).
- Nombres de archivo y carpeta, incluidas sus erratas (`secuencie`, `Planificaion`, `Languaje`, `survey_Your_even`).
- Números, porcentajes, fechas numéricas y versiones.

### 10.3 Marcado

- Rutas de imágenes y destinos de enlaces (`![…](ruta)`, `[…](url)`). El **texto alternativo** y el **texto visible** del enlace se traducen, salvo que sea un nombre de archivo o una URL.
- Atributos HTML de tablas (`colspan`, `rowspan`, `style`, `width`) y las etiquetas HTML.
- Comentarios HTML con texto de figuras: se conserva el texto original y se añade debajo la traducción, dentro del mismo comentario, con el prefijo `EN:`.
- Texto dentro de imágenes y capturas: no se traduce; se anota en `losses`.

## 11. Decisiones pendientes de aprobación

1. **Fechas escritas con palabras** («9 de octubre de 2026», «Julio 2026»): propuesta, traducir el mes conservando el orden y los números («9 October 2026», «July 2026»). La verificación exige identidad de **números** y de fechas **numéricas** (`2026-10-09`).
2. **Formato numérico español** («100.000 asientos», «0,5»): propuesta, conservar los números tal cual y declararlo en `losses` (en inglés `100.000` podría leerse como cien).
3. **Textos literales de la interfaz** entre comillas («Tus tickets», «Mis Eventos»): propuesta, traducirlos y añadir el literal español entre paréntesis la primera vez, p. ej. “Your tickets” («Tus tickets»), porque no se conoce el texto real de la interfaz en inglés.
