---
id: TE-0097
title: "Diccionario de datos Tu-Evento"
lang: es
source: 04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx
source_sha256: 55e048637ab5260300cba10304b9cabffcf35f93612b8fc6af685a766436cc7d
conversion: "openpyxl 3.1.5 (data_only + fórmulas); sin revisión manual"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Formato visual (colores, bordes, anchos, fuentes y estilos del formato condicional) no se conserva."
  - "Celdas combinadas listadas pero no reproducidas como celda única."
  - "Los valores de las fórmulas son los guardados en caché por Excel; no se recalcularon."
status: borrador
reviewed_by: ""
---
# Diccionario de datos Tu-Evento

> Conversión de `04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx`: 13 hojas (Seguridad, Cartera, Categorias, Geolocalizacion, Secciones, Sillas, Temas, Lenguaje, Notificaciones, Pagos, Perfil, Eventos, Tickets), 0 fórmulas. Las columnas se nombran con la letra de Excel y cada fila con su número original.

## Hoja: Seguridad

Rango usado: `A1:G126` · 126 filas × 7 columnas · celdas combinadas: 13

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE SEGURIDAD |  |  |  |  |  |  |
| 2 |  | Entidad: account_lockout |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | account_lockout_id | INT | NO | Enteros positivos únicos | — | Identificador único del registro de bloqueo de cuenta. (PK) |
| 5 |  | user_id | INT | NO | ID de usuario existente | — | Identificador del usuario al que pertenece el registro de bloqueo. (FK) |
| 6 |  | failed_attempts | INT | NO | Número entero ≥ 0 | — | Cantidad de intentos fallidos de inicio de sesión. |
| 7 |  | window_started_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que inicia la ventana de conteo de intentos fallidos. |
| 8 |  | locked_until | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora hasta la cual la cuenta permanece bloqueada. |
| 11 |  | Entidad: account_activation |  |  |  |  |  |
| 12 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 13 |  | account_activation_id | INT | NO | Enteros positivos únicos | — | Identificador del registro de activación de cuenta. (PK) |
| 14 |  | user_id | INT | NO | ID de usuario existente | — | Usuario al que pertenece el proceso de activación. (FK) |
| 15 |  | activation_code | VARCHAR | NO | Código alfanumérico | 6 | Código utilizado para activar la cuenta del usuario. |
| 16 |  | activated | BOOLEAN | NO | TRUE / FALSE | — | Indica si la cuenta ya fue activada. |
| 17 |  | expires_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en el que expira el código de activación. |
| 18 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en la que se creó el registro de activación. |
| 20 |  | Entidad: refresh_token |  |  |  |  |  |
| 21 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 22 |  | refresh_token_id | INT | NO | Enteros positivos únicos | — | Identificador único del refresh token. (PK) |
| 23 |  | user_id | INT | NO | ID de usuario existente | — | Usuario propietario del token. (FK) |
| 24 |  | auth_session_id | INT | NO | ID de sesión existente | — | Sesión de autenticación asociada al token. (FK) |
| 25 |  | token | VARCHAR | NO | Cadena alfanumérica segura | 512 | Token utilizado para renovar la sesión de autenticación. |
| 26 |  | issued_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que el token fue emitido. |
| 27 |  | expires_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que el token expira. |
| 28 |  | revoked | BOOLEAN | NO | TRUE / FALSE | — | Indica si el token ha sido revocado. |
| 29 |  | revoked_at | TIMESTAMP | SI | Fecha y hora válidas | — | Momento en que el token fue revocado. |
| 31 |  | Entidad: user |  |  |  |  |  |
| 32 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 33 |  | user_id | INT | NO | Enteros positivos únicos | — | Identificador único del usuario. (PK) |
| 34 |  | user_status_id | INT | NO | ID de estado existente | — | Estado actual del usuario dentro del sistema. (FK) |
| 35 |  | role_id | INT | NO | ID de rol existente | — | Rol asignado al usuario dentro del sistema. (FK) |
| 36 |  | alias | VARCHAR | NO | Texto único | 50 | Alias o nombre de usuario utilizado para identificar al usuario en el sistema. |
| 37 |  | activated | BOOLEAN | NO | TRUE / FALSE | — | Indica si la cuenta del usuario se encuentra activada. |
| 40 |  | Entidad: auth_session |  |  |  |  |  |
| 41 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 42 |  | auth_session_id | INT | NO | Enteros positivos únicos | — | Identificador único de la sesión de autenticación. (PK) |
| 43 |  | user_id | INT | NO | ID de usuario existente | — | Usuario propietario de la sesión. (FK) |
| 44 |  | access_token | VARCHAR | NO | Token alfanumérico | 512 | Token de acceso utilizado para autenticar solicitudes. |
| 45 |  | issued_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora de emisión del token de acceso. |
| 46 |  | expires_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora de expiración de la sesión. |
| 47 |  | ip_address | VARCHAR | NO | Dirección IP válida | 45 | Dirección IP desde la que se originó la sesión. |
| 48 |  | user_agent | VARCHAR | NO | Texto descriptivo | 200 | Información del navegador o dispositivo del usuario. |
| 49 |  | revoked | BOOLEAN | NO | TRUE / FALSE | — | Indica si la sesión fue revocada. |
| 50 |  | revoked_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha en la que la sesión fue revocada. |
| 52 |  | Entidad: user_status |  |  |  |  |  |
| 53 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 54 |  | user_status_id | INT | NO | Enteros positivos únicos | — | Identificador único del estado del usuario. (PK) |
| 55 |  | code | VARCHAR | NO | Código identificador | 30 | Código interno del estado del usuario. |
| 56 |  | name | VARCHAR | NO | Texto descriptivo | 60 | Nombre del estado del usuario. |
| 57 |  | description | VARCHAR | NO | Texto descriptivo | 150 | Descripción del significado del estado del usuario. |
| 59 |  | Entidad: user_status_history |  |  |  |  |  |
| 60 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 61 |  | user_status_history_id | INT | NO | Enteros positivos únicos | — | Identificador del registro histórico de estado. (PK) |
| 62 |  | user_id | INT | NO | ID de usuario existente | — | Usuario al que corresponde el cambio de estado. (FK) |
| 63 |  | user_status_id | INT | NO | ID de estado existente | — | Estado asignado al usuario en ese momento. (FK) |
| 64 |  | reason | VARCHAR | NO | Texto descriptivo | 150 | Motivo por el cual se produjo el cambio de estado del usuario. |
| 66 |  | Entidad: oauth_account |  |  |  |  |  |
| 67 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 68 |  | oauth_account_id | INT | NO | Enteros positivos únicos | — | Identificador del registro de autenticación externa. (PK) |
| 69 |  | user_id | INT | NO | ID de usuario existente | — | Usuario propietario de la cuenta OAuth. (FK) |
| 70 |  | provider | VARCHAR | NO | Nombre del proveedor OAuth | 40 | Proveedor de autenticación externa (Google, Facebook, etc.). |
| 71 |  | provider_user_id | VARCHAR | SI | Identificador externo | 100 | Identificador del usuario dentro del proveedor OAuth. |
| 72 |  | email | VARCHAR | SI | Dirección de correo electrónico | 255 | Correo electrónico asociado a la cuenta OAuth. |
| 73 |  | linked_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha en la que la cuenta externa fue vinculada al sistema. |
| 75 |  | Entidad: organizer_petition |  |  |  |  |  |
| 76 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 77 |  | organizer_petition_id | INT | NO | Enteros positivos únicos | — | Identificador de la solicitud para convertirse en organizador. (PK) |
| 78 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que realiza la solicitud. (FK) |
| 79 |  | document | BYTEA | NO | Archivo binario | — | Documento enviado por el usuario como soporte de la solicitud. |
| 80 |  | applicationDate | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha en que el usuario realizó la solicitud. |
| 81 |  | status | ENUM | NO | Pending, Approved, Rejected | — | Estado actual de la solicitud de organizador. |
| 83 |  | Entidad: permission |  |  |  |  |  |
| 84 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 85 |  | permission_id | INT | NO | Enteros positivos únicos | — | Identificador único del permiso del sistema. (PK) |
| 86 |  | code | VARCHAR | NO | Código interno | 50 | Código identificador del permiso. |
| 87 |  | name | VARCHAR | NO | Texto descriptivo | 80 | Nombre del permiso dentro del sistema. |
| 88 |  | description | VARCHAR | NO | Texto descriptivo | 150 | Descripción funcional del permiso. |
| 90 |  | Entidad: role |  |  |  |  |  |
| 91 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 92 |  | role_id | INT | NO | Enteros positivos únicos | — | Identificador único del rol del sistema. (PK) |
| 93 |  | code | VARCHAR | NO | Código interno | 50 | Código que identifica el rol. |
| 94 |  | name | VARCHAR | NO | Texto descriptivo | 80 | Nombre del rol dentro del sistema. |
| 95 |  | description | VARCHAR | NO | Texto descriptivo | 150 | Descripción del rol y sus responsabilidades. |
| 97 |  | Entidad: role_permission |  |  |  |  |  |
| 98 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 99 |  | role_permission_id | INT | NO | Enteros positivos únicos | — | Identificador de la relación rol-permiso. (PK) |
| 100 |  | permission_id | INT | NO | ID de permiso existente | — | Permiso asociado al rol. (FK) |
| 101 |  | role_id | INT | NO | ID de rol existente | — | Rol al que se asigna el permiso. (FK) |
| 103 |  | Entidad: recover_password |  |  |  |  |  |
| 104 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 105 |  | recover_password_id | INT | NO | Enteros positivos únicos | — | Identificador del proceso de recuperación de contraseña. (PK) |
| 106 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que solicita la recuperación de contraseña. (FK) |
| 107 |  | code | VARCHAR | NO | Código alfanumérico | 8 | Código utilizado para validar la recuperación de contraseña. |
| 108 |  | code_status | BOOLEAN | NO | TRUE / FALSE | — | Indica si el código ya fue utilizado o validado. |
| 109 |  | expires_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que el código deja de ser válido. |
| 110 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha en que se generó el código de recuperación. |
| 111 |  | last_password_hash | VARCHAR | NO | Hash criptográfico | 255 | Última contraseña registrada del usuario antes de la recuperación. |
| 113 |  | Entidad: password_history |  |  |  |  |  |
| 114 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 115 |  | password_history_id | INT | NO | Enteros positivos únicos | — | Identificador del registro de historial de contraseñas. (PK) |
| 116 |  | user_id | INT | NO | ID de usuario existente | — | Usuario al que pertenece la contraseña almacenada. (FK) |
| 117 |  | password_hash | VARCHAR | NO | Hash criptográfico | 255 | Contraseña cifrada almacenada en el historial. |
| 118 |  | changed_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que el usuario cambió su contraseña. |
| 120 |  | Entidad: login_credentials |  |  |  |  |  |
| 121 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 122 |  | login_credentials_id | INT | NO | Enteros positivos únicos | — | Identificador de las credenciales de acceso del usuario. (PK) |
| 123 |  | user_id | INT | NO | ID de usuario existente | — | Usuario propietario de las credenciales. (FK) |
| 124 |  | password_hash | VARCHAR | NO | Hash criptográfico | 255 | Contraseña cifrada utilizada para autenticación. |
| 125 |  | email | VARCHAR | NO | Dirección de correo electrónico válida | 255 | Correo electrónico utilizado para iniciar sesión. |
| 126 |  | last_login_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora del último inicio de sesión del usuario. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B103:C103`, `B113:C113`, `B11:C11`, `B120:C120`, `B20:C20`, `B2:C2`, `B40:C40`, `B52:C52`, `B59:C59`, `B66:C66`, `B75:C75`, `B83:C83`, `B97:C97`


## Hoja: Cartera

Rango usado: `A1:G31` · 31 filas × 7 columnas · celdas combinadas: 2

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE CARTERA |  |  |  |  |  |  |
| 2 |  | Entidad: wallet |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | wallet_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la billetera digital del usuario. (PK) |
| 5 |  | user_id | INT | NO | Identificadores de usuarios existentes | — | Referencia al usuario propietario de la billetera. (FK) |
| 6 |  | balance | DECIMAL(10,2) | NO | Valores monetarios positivos o cero | 10.2 | Saldo actual disponible en la billetera del usuario. Valor por defecto: 0. |
| 7 |  | currency | STRING | NO | Códigos de moneda ISO (ej: COP, USD, EUR) | 3 | Moneda en la que opera la billetera. Valor por defecto: COP. |
| 9 |  | Entidad: wallet_transaction |  |  |  |  |  |
| 10 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 11 |  | transaction_id | INT | NO | Números enteros únicos | — | Identificador único de la transacción realizada en la billetera. (PK) |
| 12 |  | wallet_id | INT | NO | Identificadores de billeteras existentes | — | Referencia a la billetera donde se registra la transacción. (FK) |
| 13 |  | type | ENUM | NO | refund, top-up, withdrawal, payment | — | Tipo de operación realizada en la billetera. |
| 14 |  | amount | DECIMAL(10,2) | NO | Valores monetarios positivos | 10.2 | Cantidad de dinero involucrada en la transacción. |
| 15 |  | status | ENUM | NO | pending, completed, failed | — | Estado actual de la transacción. |
| 16 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que se registró la transacción en el sistema. |
| 18 |  | Entidad: wallet_reference |  |  |  |  |  |
| 19 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 20 |  | wallet_reference_id | INT | NO | Números enteros únicos | — | Identificador único de la referencia de la transacción. (PK) |
| 21 |  | transaction_id | INT | NO | Identificadores de transacciones existentes | — | Referencia a la transacción de billetera asociada. (FK) |
| 22 |  | entity_type | ENUM | SI | order, payment, refund | — | Tipo de entidad del sistema asociada con la transacción. |
| 23 |  | entity_id | INT | SI | Identificadores de entidades relacionadas | — | Identificador de la entidad específica vinculada con la transacción. |
| 24 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que se registró la transacción en el sistema. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B18:C18`, `B26:C26`


## Hoja: Categorias

Rango usado: `A1:G22` · 22 filas × 7 columnas · celdas combinadas: 2

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE CATEGORIAS |  |  |  |  |  |  |
| 2 |  | Entidad: category |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | category_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la categoría dentro del sistema. (PK) |
| 5 |  | name | VARCHAR | NO | Texto alfanumérico | 50 | Nombre de la categoría utilizada para clasificar eventos. |
| 6 |  | description | VARCHAR | NO | Texto descriptivo | 100 | Descripción detallada de la categoría. |
| 7 |  | active | BOOLEAN | NO | TRUE / FALSE | 1 | Indica si la categoría se encuentra activa dentro del sistema. Valor por defecto: TRUE. |
| 8 |  | visible | BOOLEAN | NO | TRUE / FALSE | 1 | Determina si la categoría es visible para los usuarios en la plataforma. Valor por defecto: TRUE. |
| 9 |  | dad_id | INT | SI | Identificadores de categorías existentes | — | Referencia a la categoría padre en caso de existir una jerarquía de categorías. (FK) |
| 11 |  | Entidad: category_event |  |  |  |  |  |
| 12 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 13 |  | category_event_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la relación entre categorías y eventos. (PK) |
| 14 |  | category_id | INT | NO | Identificadores de categorías existentes | — | Identificador de la categoría asociada al evento. (PK, FK) |
| 15 |  | event_id | INT | NO | Identificadores de eventos existentes | — | Identificador del evento asociado a la categoría. (PK, FK) |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B11:C11`, `B2:C2`


## Hoja: Geolocalizacion

Rango usado: `A1:G45` · 45 filas × 7 columnas · celdas combinadas: 5

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE GEOLOCALIZACION |  |  |  |  |  |  |
| 2 |  | Entidad: department |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | department_id | INT | NO | Números enteros positivos únicos | — | Identificador único del departamento o región administrativa. (PK) |
| 5 |  | name | VARCHAR | NO | Texto alfanumérico | 100 | Nombre oficial del departamento o región geográfica. |
| 6 |  | code | VARCHAR | SI | Códigos alfanuméricos | 10 | Código identificador del departamento según el sistema de clasificación utilizado. |
| 8 |  | Entidad: city |  |  |  |  |  |
| 9 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 10 |  | city_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la ciudad registrada en el sistema. (PK) |
| 11 |  | department_id | INT | NO | Identificadores de departamentos existentes | — | Referencia al departamento al que pertenece la ciudad. (FK) |
| 12 |  | name | VARCHAR | NO | Texto alfanumérico | 100 | Nombre oficial de la ciudad. |
| 13 |  | code | VARCHAR | SI | Códigos alfanuméricos | 10 | Código identificador de la ciudad dentro del sistema o estándar territorial. |
| 15 |  | Entidad: site |  |  |  |  |  |
| 16 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 17 |  | site_id | INT | NO | Números enteros positivos únicos | — | Identificador único del sitio o lugar donde se realiza un evento. (PK) |
| 18 |  | city_id | INT | NO | Identificadores de ciudades existentes | — | Referencia a la ciudad donde se encuentra ubicado el sitio del evento. (FK) |
| 19 |  | name | VARCHAR | NO | Texto alfanumérico | 150 | Nombre del lugar o establecimiento donde se realiza el evento. |
| 20 |  | address | VARCHAR | NO | Texto alfanumérico | 200 | Dirección física del sitio donde se realiza el evento. |
| 21 |  | capacity | INT | SI | Números enteros positivos | — | Capacidad máxima de personas que puede albergar el sitio. |
| 22 |  | latitude | DECIMAL | SI | Valores decimales de coordenadas geográficas | 9.6 | Coordenada geográfica de latitud que indica la ubicación del sitio. |
| 23 |  | longitude | DECIMAL | SI | Valores decimales de coordenadas geográficas | 9.6 | Coordenada geográfica de longitud que indica la ubicación del sitio. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B15:C15`, `B25:C25`, `B2:C2`, `B34:C34`, `B8:C8`


## Hoja: Secciones

Rango usado: `A1:G15` · 15 filas × 7 columnas · celdas combinadas: 2

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE SECCIONES |  |  |  |  |  |  |
| 2 |  | Entidad: section_type |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 4 |  | section_type_id | INT | NO | Números enteros positivos únicos | — | Identificador único del tipo de sección. (PK) |
| 5 |  | name | VARCHAR | NO | Texto alfanumérico | 100 | Nombre del tipo de sección del evento (Ej: VIP, General, Preferencial). |
| 7 |  | Entidad: event_section |  |  |  |  |  |
| 8 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 9 |  | event_section_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la sección del evento. (PK) |
| 10 |  | event_id | INT | NO | Identificadores de eventos existentes | — | Evento al que pertenece la sección. (FK) |
| 11 |  | section_type_id | INT | NO | Identificadores de tipos de sección existentes | — | Tipo de sección asignado (VIP, General, etc.). (FK) |
| 12 |  | capacity | INT | NO | Números enteros positivos | — | Capacidad máxima de personas permitidas en la sección. |
| 13 |  | available_seats | INT | NO | Números enteros positivos | — | Número de asientos disponibles para reserva. |
| 14 |  | price | DECIMAL(10,2) | NO | Valores decimales positivos | 10.2 | Precio de la entrada para esa sección. |
| 15 |  | is_active | BOOLEAN | NO | TRUE / FALSE | 1 | Indica si la sección está disponible para venta. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B2:C2`, `B7:C7`


## Hoja: Sillas

Rango usado: `A1:G46` · 46 filas × 7 columnas · celdas combinadas: 4

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE SILLAS |  |  |  |  |  |  |
| 2 |  | Entidad: seat |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | seat_id | INT | NO | Enteros positivos únicos | — | Identificador único del asiento dentro del sistema. (PK) |
| 5 |  | seat_block_id | INT | NO | Enteros positivos que correspondan a un bloque de asientos existente | — | Identificador del bloque de asientos al que pertenece el asiento. (FK) |
| 6 |  | event_section_id | INT | NO | Enteros positivos que correspondan a una sección de evento existente | — | Identificador de la sección del evento donde se ubica el asiento. (FK) |
| 7 |  | code | VARCHAR | NO | Códigos alfanuméricos de identificación del asiento (ej: A10, B5) | 20 | Código único que identifica el asiento dentro de una sección. |
| 8 |  | row | INT | NO | Enteros positivos | — | Número de la fila donde se encuentra el asiento dentro del bloque. |
| 9 |  | position | INT | NO | Enteros positivos | — | Posición del asiento dentro de la fila correspondiente. |
| 10 |  | type | ENUM | SI | regular, courtesy | — | Tipo de asiento disponible en el evento (regular o de cortesía). |
| 11 |  | status | ENUM | SI | available, reserved, sold, courtesy | — | Estado actual del asiento dentro del sistema de reservas. |
| 13 |  | Entidad: seat_block |  |  |  |  |  |
| 14 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 15 |  | seat_block_id | INT | NO | Enteros positivos únicos | — | Identificador único del bloque de asientos. (PK) |
| 16 |  | event_section_id | INT | NO | Enteros positivos correspondientes a secciones de eventos existentes | — | Identificador de la sección del evento a la que pertenece el bloque de asientos. (FK) |
| 17 |  | name | VARCHAR | NO | Texto descriptivo del bloque de asientos | 100 | Nombre del bloque o zona de asientos dentro de la sección del evento. |
| 18 |  | capacity | INT | NO | Enteros positivos | — | Cantidad máxima de asientos que puede contener el bloque. |
| 20 |  | Entidad: seat_log |  |  |  |  |  |
| 21 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 22 |  | seat_log_id | INT | NO | Enteros positivos únicos | — | Identificador único del registro de historial de cambios de estado del asiento. (PK) |
| 23 |  | seat_id | INT | NO | Enteros positivos correspondientes a asientos existentes | — | Identificador del asiento sobre el cual se registra el cambio de estado. (FK) |
| 24 |  | old_status | ENUM | SI | available, reserved, sold, courtesy | — | Estado anterior del asiento antes de registrarse el cambio. |
| 25 |  | new_status | ENUM | SI | available, reserved, sold, courtesy | — | Nuevo estado asignado al asiento después del cambio. |
| 26 |  | change_at | TIMESTAMP | SI | Fecha y hora válidas del sistema | — | Fecha y hora en la que se registró el cambio de estado del asiento. |
| 27 |  | change_by | INT | SI | Enteros positivos correspondientes a usuarios del sistema | — | Identificador del usuario que realizó el cambio de estado. (FK) |
| 28 |  | reason | VARCHAR | SI | Texto descriptivo | 255 | Motivo o explicación del cambio de estado registrado para el asiento. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B13:C13`, `B20:C20`, `B2:C2`, `B40:C40`


## Hoja: Temas

Rango usado: `A1:G39` · 39 filas × 7 columnas · celdas combinadas: 5

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE TEMAS |  |  |  |  |  |  |
| 2 |  | Entidad: theme |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 4 |  | theme_id | INT | NO | Enteros positivos únicos | — | Identificador único del tema visual del sistema. (PK) |
| 5 |  | name | VARCHAR | NO | Texto alfanumérico | 100 | Nombre del tema visual disponible para la interfaz. |
| 6 |  | description | VARCHAR | NO | Texto descriptivo | 255 | Descripción del estilo o apariencia del tema. |
| 7 |  | default_palette | JSONB | SI | Objeto JSON con configuración de colores | — | Paleta de colores predeterminada del tema (colores, fondos, etc.). |
| 9 |  | Entidad: user_theme |  |  |  |  |  |
| 10 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 11 |  | user_theme_id | INT | NO | Enteros positivos únicos | — | Identificador del registro de configuración de tema del usuario. (PK) |
| 12 |  | user_id | INT | NO | Enteros positivos correspondientes a usuarios existentes | — | Identificador del usuario que utiliza el tema. (FK) |
| 13 |  | theme_id | INT | NO | Enteros positivos correspondientes a temas existentes | — | Identificador del tema seleccionado por el usuario. (FK) |
| 14 |  | is_active | BOOLEAN | SI | TRUE, FALSE | — | Indica si el tema se encuentra activo para el usuario. |
| 15 |  | created_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora en que se asignó el tema al usuario. |
| 16 |  | updated_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora de la última actualización del tema del usuario. |
| 18 |  | Entidad: theme_customization |  |  |  |  |  |
| 19 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 20 |  | customization_id | INT | NO | Enteros positivos únicos | — | Identificador único de la personalización del tema. (PK) |
| 21 |  | user_theme_id | INT | NO | Enteros positivos correspondientes a configuraciones de tema de usuario | — | Identificador de la configuración de tema asociada al usuario. (FK) |
| 22 |  | property | VARCHAR | NO | Nombre de propiedad visual | 100 | Propiedad visual personalizada del tema (ej: color_header, background). |
| 23 |  | value | VARCHAR | SI | Valor asociado a la propiedad | 255 | Valor asignado a la propiedad de personalización. |
| 24 |  | created_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha en la que se creó la personalización. |
| 25 |  | updated_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha de la última modificación de la personalización. |
| 27 |  | Entidad: theme_log |  |  |  |  |  |
| 28 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 29 |  | log_id | INT | NO | Enteros positivos únicos | — | Identificador único del registro de cambios del tema. (PK) |
| 30 |  | user_theme_id | INT | NO | Enteros positivos correspondientes a configuraciones de tema de usuario | — | Identificador del tema configurado para el usuario. (FK) |
| 31 |  | action | VARCHAR | SI | Texto descriptivo de la acción | 50 | Acción realizada sobre el tema (create, update, activate, etc.). |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B18:C18`, `B27:C27`, `B2:C2`, `B33:C33`, `B9:C9`


## Hoja: Lenguaje

Rango usado: `A1:G145` · 145 filas × 7 columnas · celdas combinadas: 16

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE LENGUAJES |  |  |  |  |  |  |
| 2 |  | Entidad: language |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | language_id | INT | NO | Enteros positivos | — | Identificador único del idioma en el sistema (PK) |
| 5 |  | code | VARCHAR | NO | Código del idioma (ej: es, en, fr) | 10 | Código abreviado del idioma utilizado por el sistema |
| 6 |  | name | VARCHAR | NO | Nombre del idioma | 50 | Nombre descriptivo del idioma disponible en el sistema |
| 7 |  | is_active | BOOLEAN | NO | TRUE / FALSE | — | Indica si el idioma se encuentra activo dentro del sistema |
| 9 |  | Entidad: event_translation |  |  |  |  |  |
| 10 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 11 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción del evento (PK) |
| 12 |  | event_id | INT | NO | ID de evento existente | — | Evento al que pertenece la traducción (FK) |
| 13 |  | language_id | INT | NO | ID de idioma existente | — | Idioma en el que se realiza la traducción (FK) |
| 14 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre del evento traducido |
| 15 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida del evento |
| 16 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 18 |  | Entidad: event_rating_translation |  |  |  |  |  |
| 19 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 20 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción de la calificación (PK) |
| 21 |  | rating_id | INT | NO | ID de calificación existente | — | Calificación asociada a la traducción (FK) |
| 22 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 23 |  | translated_comment | VARCHAR | NO | Texto | 255 | Comentario traducido de la calificación |
| 24 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 26 |  | Entidad: notification_translation |  |  |  |  |  |
| 27 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 28 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción de la notificación (PK) |
| 29 |  | notification_id | INT | NO | ID de notificación existente | — | Notificación asociada (FK) |
| 30 |  | language_id | INT | NO | ID de idioma existente | — | Idioma en el que se encuentra la traducción (FK) |
| 31 |  | translated_subject | VARCHAR | NO | Texto | 100 | Asunto traducido de la notificación |
| 32 |  | translated_body | VARCHAR | NO | Texto | 255 | Contenido traducido de la notificación |
| 33 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 35 |  | Entidad: event_comment_reply_translation |  |  |  |  |  |
| 36 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 37 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción de una respuesta (PK) |
| 38 |  | reply_id | INT | NO | ID de respuesta existente | — | Respuesta asociada a la traducción (FK) |
| 39 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 40 |  | translated_reply_text | VARCHAR | NO | Texto | 255 | Texto traducido de la respuesta |
| 41 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 43 |  | Entidad: profile_translation |  |  |  |  |  |
| 44 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 45 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción del perfil (PK) |
| 46 |  | profile_id | INT | NO | ID de perfil existente | — | Perfil al que pertenece la traducción (FK) |
| 47 |  | language_id | INT | NO | ID de idioma existente | — | Idioma en el que se encuentra la traducción (FK) |
| 48 |  | translated_bio | VARCHAR | NO | Texto | 255 | Biografía del usuario traducida |
| 49 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de la traducción realizada |
| 50 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 52 |  | Entidad: channel_translation |  |  |  |  |  |
| 53 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 54 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de la traducción del canal (PK) |
| 55 |  | channel_id | INT | NO | ID de canal existente | — | Canal asociado a la traducción (FK) |
| 56 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 57 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del canal |
| 58 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida del canal |
| 59 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de la traducción |
| 60 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado de la traducción |
| 62 |  | Entidad: section_type_translation |  |  |  |  |  |
| 63 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 64 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción del tipo de sección (PK) |
| 65 |  | section_type_id | INT | NO | ID de sección existente | — | Tipo de sección asociado (FK) |
| 66 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 67 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del tipo de sección |
| 68 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de la traducción |
| 69 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 71 |  | Entidad: category_translation |  |  |  |  |  |
| 72 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 73 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción de categoría (PK) |
| 74 |  | category_id | INT | NO | ID de categoría existente | — | Categoría asociada (FK) |
| 75 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 76 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido de la categoría |
| 77 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida de la categoría |
| 78 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 79 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 81 |  | Entidad: category_translation |  |  |  |  |  |
| 82 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 83 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción de categoría (PK) |
| 84 |  | category_id | INT | NO | ID de categoría existente | — | Categoría asociada (FK) |
| 85 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 86 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido de la categoría |
| 87 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida de la categoría |
| 88 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 89 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 91 |  | Entidad: review_translation |  |  |  |  |  |
| 92 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 93 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción de reseña (PK) |
| 94 |  | review_id | INT | NO | ID de reseña existente | — | Reseña asociada (FK) |
| 95 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 96 |  | translated_comment | VARCHAR | NO | Texto | 255 | Comentario traducido de la reseña |
| 97 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 98 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 100 |  | Entidad: seat_block_translation |  |  |  |  |  |
| 101 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 102 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción del bloque de asientos (PK) |
| 103 |  | seat_block_id | INT | NO | ID de bloque existente | — | Bloque de asientos asociado (FK) |
| 104 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 105 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del bloque de asientos |
| 106 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 107 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 109 |  | Entidad: notification_type_translation |  |  |  |  |  |
| 110 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 111 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción del tipo de notificación (PK) |
| 112 |  | notification_type_id | INT | NO | ID de tipo de notificación existente | — | Tipo de notificación asociado (FK) |
| 113 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 114 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del tipo de notificación |
| 115 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida del tipo de notificación |
| 116 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 117 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 119 |  | Entidad: theme_translation |  |  |  |  |  |
| 120 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 121 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción del tema (PK) |
| 122 |  | theme_id | INT | NO | ID de tema existente | — | Tema asociado a la traducción (FK) |
| 123 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 124 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del tema |
| 125 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida del tema |
| 126 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de traducción |
| 127 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 129 |  | Entidad: module_translation |  |  |  |  |  |
| 130 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 131 |  | translation_id | INT | NO | Enteros positivos | — | Identificador de traducción del módulo (PK) |
| 132 |  | module_string | VARCHAR | NO | Identificador de módulo | 100 | Cadena que identifica el módulo del sistema |
| 133 |  | language_id | INT | NO | ID de idioma existente | — | Idioma de la traducción (FK) |
| 134 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre traducido del módulo |
| 135 |  | source | VARCHAR | NO | manual / automatic | 50 | Fuente de la traducción |
| 136 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |
| 138 |  | Entidad: action_translation |  |  |  |  |  |
| 139 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 140 |  | translation_id | INT | NO | Enteros positivos | — | Identificador único de la traducción del evento (PK) |
| 141 |  | event_id | INT | NO | ID de evento existente | — | Evento al que pertenece la traducción (FK) |
| 142 |  | language_id | INT | NO | ID de idioma existente | — | Idioma en el que se realiza la traducción (FK) |
| 143 |  | translated_name | VARCHAR | NO | Texto | 100 | Nombre del evento traducido |
| 144 |  | translated_description | VARCHAR | NO | Texto | 255 | Descripción traducida del evento |
| 145 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Estado del proceso de traducción |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B100:E100`, `B109:D109`, `B119:C119`, `B129:D129`, `B138:C138`, `B18:D18`, `B26:D26`, `B2:C2`, `B35:E35`, `B43:C43`, `B52:C52`, `B62:D62`, `B71:D71`, `B81:D81`, `B91:D91`, `B9:C9`


## Hoja: Notificaciones

Rango usado: `A1:G35` · 35 filas × 7 columnas · celdas combinadas: 4

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE NOTIFICACIONES |  |  |  |  |  |  |
| 2 |  | Entidad: notification |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | notification_id | INT | NO | Enteros positivos | — | Identificador único de la notificación en el sistema (PK) |
| 5 |  | channel_id | INT | NO | ID de canal existente | — | Canal por el cual se envía la notificación (FK) |
| 6 |  | notification_type_id | INT | NO | ID de tipo de notificación existente | — | Tipo de notificación asociada (FK) |
| 7 |  | event_id | INT | NO | ID de evento existente | — | Evento relacionado con la notificación (FK) |
| 8 |  | subject | VARCHAR | NO | Texto | 150 | Asunto o título de la notificación enviada al usuario |
| 9 |  | body | TEXT | NO | Texto | — | Contenido o mensaje de la notificación |
| 10 |  | sent_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora en que la notificación fue enviada |
| 12 |  | Entidad: notification_type |  |  |  |  |  |
| 13 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 14 |  | notification_type_id | INT | NO | Enteros positivos | — | Identificador del tipo de notificación (PK) |
| 15 |  | name | VARCHAR | NO | Texto | 50 | Nombre del tipo de notificación |
| 16 |  | description | VARCHAR | NO | Texto | 100 | Descripción del tipo de notificación |
| 17 |  | active | BOOLEAN | NO | TRUE / FALSE | — | Indica si el tipo de notificación está activo en el sistema |
| 19 |  | Entidad: channel |  |  |  |  |  |
| 20 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 21 |  | channel_id | INT | NO | Enteros positivos | — | Identificador único del canal de notificación (PK) |
| 22 |  | name | VARCHAR | NO | Texto | 50 | Nombre del canal de notificación (ej: Email, SMS) |
| 23 |  | description | VARCHAR | NO | Texto | 100 | Descripción del canal |
| 24 |  | active | BOOLEAN | NO | TRUE / FALSE | — | Indica si el canal está habilitado en el sistema |
| 25 |  | config | JSONB | SI | Configuración en formato JSON | — | Configuración técnica del canal de envío |
| 27 |  | Entidad: notification_user |  |  |  |  |  |
| 28 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 29 |  | notification_user_id | INT | NO | Enteros positivos | — | Identificador del registro de notificación por usuario (PK) |
| 30 |  | notification_id | INT | NO | ID de notificación existente | — | Notificación asociada al usuario (FK) |
| 31 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que recibe la notificación (FK) |
| 32 |  | email_address | VARCHAR | NO | Dirección de correo electrónico válida | 255 | Correo electrónico del destinatario de la notificación |
| 33 |  | delivered_status | ENUM | NO | Pending, Sent, Delivered, Failed | — | Estado de entrega de la notificación |
| 34 |  | error_message | VARCHAR | SI | Texto | 255 | Mensaje de error en caso de que falle el envío |
| 35 |  | read_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora en que el usuario leyó la notificación |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B12:C12`, `B19:C19`, `B27:D27`, `B2:D2`


## Hoja: Pagos

Rango usado: `A1:G47` · 47 filas × 7 columnas · celdas combinadas: 2

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE PAGOS |  |  |  |  |  |  |
| 2 |  | Entidad: payment |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | payment_id | INT | NO | Enteros positivos | — | Identificador único del pago registrado en el sistema (PK) |
| 5 |  | order_id | INT | NO | ID de orden existente | — | Orden asociada al pago realizado (FK) |
| 6 |  | gateway | ENUM | NO | fake, wompi | — | Pasarela de pago utilizada para procesar la transacción |
| 7 |  | gateway_transaction_id | VARCHAR | NO | Identificador de transacción de la pasarela | 100 | Código de la transacción generado por la pasarela de pago |
| 8 |  | status | ENUM | NO | pending, approved, rejected, error, refunded | — | Estado actual del pago dentro del sistema |
| 9 |  | amount | DECIMAL | NO | Valores numéricos positivos | 10.2 | Monto total pagado en la transacción |
| 10 |  | payment_method | ENUM | NO | card, pse, nequi, cash | — | Método de pago utilizado por el usuario |
| 11 |  | processed_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora en que el pago fue procesado |
| 13 |  | Entidad: payment_log |  |  |  |  |  |
| 14 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 15 |  | payment_log_id | INT | NO | Enteros positivos | — | Identificador único del registro de historial del pago (PK) |
| 16 |  | payment_id | INT | NO | ID de pago existente | — | Pago asociado al registro del historial (FK) |
| 17 |  | old_status | ENUM | NO | pending, processing, paid, failed, refunded | — | Estado anterior del pago antes de la actualización |
| 18 |  | new_status | ENUM | NO | pending, processing, paid, failed, refunded | — | Nuevo estado del pago después del cambio |
| 19 |  | changed_at | TIMESTAMP | NO | Fecha y hora válidas | — | Momento en que ocurrió el cambio de estado |
| 20 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha en que se registró el cambio en el historial |
| 21 |  | reason | VARCHAR | SI | Texto | 255 | Motivo del cambio de estado del pago |
| 23 |  | Entidad: transaction_webhook |  |  |  |  |  |
| 24 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 25 |  | webhook_id | INT | NO | Enteros positivos | — | Identificador del webhook recibido desde la pasarela de pago (PK) |
| 26 |  | payment_id | INT | NO | ID de pago existente | — | Pago relacionado con el webhook recibido (FK) |
| 27 |  | payload | JSONB | NO | Datos en formato JSON | — | Información enviada por la pasarela de pago |
| 28 |  | received_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en que se recibió el webhook |
| 30 |  | Entidad: refund |  |  |  |  |  |
| 31 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 32 |  | refund_id | INT | NO | Enteros positivos | — | Identificador único del reembolso solicitado (PK) |
| 33 |  | payment_id | INT | NO | ID de pago existente | — | Pago al que se le solicita el reembolso (FK) |
| 34 |  | status | ENUM | NO | requested, approved, processed, failed | — | Estado del proceso de reembolso |
| 35 |  | reason | VARCHAR | SI | Texto | 255 | Motivo del reembolso solicitado |
| 36 |  | requested_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en que se solicitó el reembolso |
| 37 |  | processed_at | TIMESTAMP | SI | Fecha y hora válidas | — | Fecha y hora en que el reembolso fue procesado |
| 39 |  | Entidad: order |  |  |  |  |  |
| 40 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 41 |  | order_id | INT | NO | Enteros positivos | — | Identificador único de la orden de compra (PK) |
| 42 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que realiza la orden de compra (FK) |
| 43 |  | event_id | INT | NO | ID de evento existente | — | Evento asociado a la compra de entradas (FK) |
| 44 |  | total_amount | DECIMAL | NO | Valores numéricos positivos | 10.2 | Monto total de la orden |
| 45 |  | currency | VARCHAR | NO | Código de moneda | 3 | Moneda utilizada en la transacción (por defecto COP) |
| 46 |  | status | ENUM | NO | pending, processing, paid, failed, refunded | — | Estado actual de la orden de compra |
| 47 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha de creación de la orden |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B13:C13`, `B23:D23`


## Hoja: Perfil

Rango usado: `A1:G45` · 45 filas × 7 columnas · celdas combinadas: 2

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE PERFIL |  |  |  |  |  |  |
| 2 |  | Entidad: profile |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | profile_id | INT | NO | Enteros positivos | — | Identificador único del perfil del usuario (PK) |
| 5 |  | user_id | INT | NO | ID de usuario existente | — | Usuario al que pertenece el perfil (FK) |
| 6 |  | city_id | INT | NO | ID de ciudad existente | — | Ciudad registrada en el perfil del usuario (FK) |
| 7 |  | full_name | VARCHAR | NO | Texto | 100 | Nombre completo del usuario |
| 8 |  | photo_url | VARCHAR | NO | URL válida | 255 | Dirección de la foto de perfil del usuario |
| 9 |  | bio | VARCHAR | SI | Texto | 255 | Descripción o biografía del usuario |
| 11 |  | Entidad: profile_log |  |  |  |  |  |
| 12 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 13 |  | log_id | INT | NO | Enteros positivos | — | Identificador del registro de cambios del perfil (PK) |
| 14 |  | profile_id | INT | NO | ID de perfil existente | — | Perfil al que pertenece el cambio registrado (FK) |
| 15 |  | action | VARCHAR | NO | Texto | 50 | Acción realizada en el perfil |
| 16 |  | old_value | VARCHAR | SI | Texto | 255 | Valor anterior antes de la modificación |
| 17 |  | new_value | VARCHAR | SI | Texto | 255 | Nuevo valor después del cambio |
| 18 |  | occurred_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en que se realizó el cambio |
| 20 |  | Entidad: activity_log |  |  |  |  |  |
| 21 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 22 |  | log_id | INT | NO | Enteros positivos | — | Identificador único del registro de actividad (PK) |
| 23 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que realizó la acción registrada (FK) |
| 24 |  | module | VARCHAR | NO | Texto | 50 | Nombre del módulo donde ocurrió la acción |
| 25 |  | action | VARCHAR | NO | Texto | 100 | Acción realizada por el usuario |
| 26 |  | reference_id | INT | SI | ID relacionado con la acción | — | Identificador del registro afectado |
| 27 |  | occurred_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en que ocurrió la actividad |
| 29 |  | Entidad: wallet_summary |  |  |  |  |  |
| 30 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 31 |  | summary_id | INT | NO | Enteros positivos | — | Identificador del resumen de movimientos de la billetera (PK) |
| 32 |  | user_id | INT | NO | ID de usuario existente | — | Usuario propietario del resumen (FK) |
| 33 |  | wallet_id | INT | NO | ID de billetera existente | — | Billetera asociada al resumen (FK) |
| 34 |  | transaction_id | INT | NO | ID de transacción existente | — | Transacción relacionada con el resumen (FK) |
| 35 |  | type | ENUM | NO | recharge, payment, refund | — | Tipo de movimiento registrado en la billetera |
| 36 |  | amount | DECIMAL | NO | Valores numéricos positivos | 10.2 | Monto de la transacción |
| 37 |  | occurred_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora en que ocurrió la transacción |
| 39 |  | Entidad: preferences |  |  |  |  |  |
| 40 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 41 |  | preference_id | INT | NO | Enteros positivos | — | Identificador único de la preferencia registrada (PK) |
| 42 |  | user_id | INT | NO | ID de usuario existente | — | Usuario al que pertenecen las preferencias (FK) |
| 43 |  | language_id | INT | NO | ID de idioma existente | — | Idioma seleccionado por el usuario (FK) |
| 44 |  | theme_id | INT | NO | ID de tema existente | — | Tema visual seleccionado por el usuario (FK) |
| 45 |  | notifications | BOOLEAN | NO | TRUE / FALSE | — | Indica si el usuario tiene activadas las notificaciones |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B29:C29`, `B39:C39`


## Hoja: Eventos

Rango usado: `A1:G60` · 60 filas × 7 columnas · celdas combinadas: 7

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE EVENTOS |  |  |  |  |  |  |
| 2 |  | Entidad: event_layout |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 4 |  | event_layout_id | INT | NO | Enteros positivos | — | Identificador único del layout del evento (PK) |
| 5 |  | event_id | INT | NO | ID de evento existente | — | Evento al que pertenece el layout (FK) |
| 6 |  | layout_data | JSONB | NO | Datos en formato JSON | — | Información del diseño o distribución del evento |
| 8 |  | Entidad: event_media |  |  |  |  |  |
| 9 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 10 |  | media_id | INT | NO | Enteros positivos | — | Identificador único del recurso multimedia (PK) |
| 11 |  | event_id | INT | NO | ID de evento existente | — | Evento al que pertenece el archivo multimedia (FK) |
| 12 |  | img_url | VARCHAR | NO | URL válida | 255 | Dirección de la imagen o recurso multimedia del evento |
| 14 |  | Entidad: event_media_log |  |  |  |  |  |
| 15 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 16 |  | media_log_id | INT | NO | Enteros positivos | — | Identificador del historial de cambios del contenido multimedia (PK) |
| 17 |  | event_id | INT | NO | ID de evento existente | — | Evento relacionado con el registro (FK) |
| 18 |  | media_id | INT | NO | ID de recurso multimedia | — | Recurso multimedia relacionado (FK) |
| 19 |  | img_url | VARCHAR | NO | URL válida | 255 | Dirección del recurso multimedia almacenado |
| 20 |  | version | INT | NO | Enteros positivos | — | Versión del recurso multimedia |
| 21 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indica si el recurso multimedia es visible |
| 23 |  | Entidad: event_rating |  |  |  |  |  |
| 24 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 25 |  | rating_id | INT | NO | Enteros positivos | — | Identificador único de la calificación del evento (PK) |
| 26 |  | event_id | INT | NO | ID de evento existente | — | Evento que recibe la calificación (FK) |
| 27 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que realiza la calificación (FK) |
| 28 |  | rating | INT | NO | Valores entre 1 y 5 | — | Calificación otorgada al evento |
| 29 |  | comment | VARCHAR | NO | Texto | 255 | Comentario asociado a la calificación |
| 30 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indica si la calificación es visible |
| 31 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha en que se realizó la calificación |
| 33 |  | Entidad: event_comment_reply |  |  |  |  |  |
| 34 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 35 |  | reply_id | INT | NO | Enteros positivos | — | Identificador de la respuesta al comentario (PK) |
| 36 |  | parent_reply_id | INT | SI | ID de respuesta existente | — | Permite respuestas anidadas |
| 37 |  | rating_id | INT | NO | ID de calificación existente | — | Calificación a la que pertenece la respuesta (FK) |
| 38 |  | user_id | INT | NO | ID de usuario existente | — | Usuario que realiza la respuesta (FK) |
| 39 |  | reply_text | VARCHAR | NO | Texto | 255 | Contenido de la respuesta al comentario |
| 40 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indica si la respuesta es visible |
| 41 |  | created_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha de creación de la respuesta |
| 43 |  | Entidad: event_status_log |  |  |  |  |  |
| 44 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 45 |  | status_log_id | INT | NO | Enteros positivos | — | Identificador del historial de estados del evento (PK) |
| 46 |  | event_id | INT | NO | ID de evento existente | — | Evento asociado al cambio de estado (FK) |
| 47 |  | old_status | ENUM | NO | Draft, Published, Cancelled, Completed | — | Estado anterior del evento |
| 48 |  | new_status | ENUM | NO | Draft, Published, Cancelled, Completed | — | Nuevo estado del evento |
| 49 |  | changed_at | TIMESTAMP | NO | Fecha y hora válidas | — | Fecha y hora del cambio de estado |
| 50 |  | changed_by | INT | NO | ID de usuario existente | — | Usuario que realizó el cambio |
| 52 |  | Entidad: event |  |  |  |  |  |
| 53 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud | Descripción |
| 54 |  | event_section_id | INT | NO | Números enteros positivos únicos | — | Identificador único de la sección del evento. (PK) |
| 55 |  | event_id | INT | NO | Identificadores de eventos existentes | — | Evento al que pertenece la sección. (FK) |
| 56 |  | section_type_id | INT | NO | Identificadores de tipos de sección existentes | — | Tipo de sección asignado (VIP, General, etc.). (FK) |
| 57 |  | capacity | INT | NO | Números enteros positivos | — | Capacidad máxima de personas permitidas en la sección. |
| 58 |  | available_seats | INT | NO | Números enteros positivos | — | Número de asientos disponibles para reserva. |
| 59 |  | price | DECIMAL(10,2) | NO | Valores decimales positivos | 10.2 | Precio de la entrada para esa sección. |
| 60 |  | is_active | BOOLEAN | NO | TRUE / FALSE | 1 | Indica si la sección está disponible para venta. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B14:C14`, `B23:C23`, `B2:C2`, `B33:D33`, `B43:C43`, `B52:C52`, `B8:C8`


## Hoja: Tickets

Rango usado: `A1:G45` · 45 filas × 7 columnas · celdas combinadas: 1

| Fila | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | MODULO DE TICKETS |  |  |  |  |  |  |
| 2 |  | Entidad: seat_ticket |  |  |  |  |  |
| 3 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 4 |  | seat_id | INT | NO | Enteros positivos existentes en la tabla seat | N/A | Identificador del asiento asociado al ticket. (PK, FK) |
| 5 |  | ticket_id | INT | NO | Enteros positivos existentes en la tabla ticket | N/A | Identificador del ticket asociado al asiento. (PK, FK) |
| 6 |  | price | DECIMAL | NO | Valores monetarios positivos | 10.2 | Precio asignado al asiento dentro del ticket. |
| 8 |  | Entidad: ticket_checkin |  |  |  |  |  |
| 9 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 10 |  | checkin_id | INT | NO | Enteros positivos únicos | N/A | Identificador único del registro de check-in. (PK) |
| 11 |  | ticket_id | INT | NO | Enteros positivos existentes en la tabla ticket | N/A | Ticket utilizado para realizar el check-in al evento. (FK) |
| 12 |  | checkin_time | TIMESTAMP | SI | Fecha y hora válidas | N/A | Momento exacto en que el ticket fue validado en el evento. |
| 13 |  | validated_by | INT | SI | Identificador de usuario que valida el acceso | N/A | Usuario responsable de validar el ticket durante el ingreso al evento. (FK) |
| 15 |  | Entidad: ticket_log |  |  |  |  |  |
| 16 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 17 |  | ticket_log_id | INT | NO | Enteros positivos únicos | N/A | Identificador del registro histórico de cambios del ticket. (PK) |
| 18 |  | ticket_id | INT | NO | Enteros positivos existentes en ticket | N/A | Identificador del ticket al que pertenece el registro. (FK) |
| 19 |  | old_status | ENUM | SI | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | Estado anterior del ticket antes del cambio. |
| 20 |  | new_status | ENUM | SI | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | Nuevo estado asignado al ticket después de la modificación. |
| 21 |  | changed_at | TIMESTAMP | SI | Fecha y hora válidas | N/A | Fecha y hora en que se realizó el cambio de estado del ticket. |
| 22 |  | changed_by | INT | SI | Identificador de usuario | N/A | Usuario responsable de modificar el estado del ticket. (FK) |
| 23 |  | reason | VARCHAR | SI | Texto descriptivo | 255 | Motivo o justificación del cambio de estado del ticket. |
| 25 |  | Entidad: ticket |  |  |  |  |  |
| 26 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 27 |  | ticket_id | INT | NO | Enteros positivos únicos | N/A | Identificador único del ticket generado para un evento. (PK) |
| 28 |  | event_id | INT | NO | Enteros positivos existentes en event | N/A | Identificador del evento al que pertenece el ticket. (FK) |
| 29 |  | user_id | INT | NO | Enteros positivos existentes en user | N/A | Usuario propietario del ticket. (FK) |
| 30 |  | order_id | INT | NO | Enteros positivos existentes en order | N/A | Pedido mediante el cual se adquirió el ticket. (FK) |
| 31 |  | code | VARCHAR | NO | Código alfanumérico | 20 | Código único del ticket utilizado para validación. |
| 32 |  | qr_code | VARCHAR | SI | Cadena codificada | 255 | Código QR generado para la validación digital del ticket. |
| 33 |  | status | ENUM | SI | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | Estado actual del ticket dentro del proceso de compra o uso. |
| 34 |  | expiration_date | DATE | SI | Fechas válidas | N/A | Fecha límite de validez del ticket. |
| 35 |  | total_price | DECIMAL | NO | Valores monetarios positivos | 10.2 | Precio total pagado por el ticket. |
| 37 |  | Entidad: order |  |  |  |  |  |
| 38 |  | Nombre del campo | Tipo de dato | ¿Acepta valores nulos? | Valores aceptables | Longitud de caracteres | Descripción |
| 39 |  | order_id | INT | NO | Enteros positivos únicos | N/A | Identificador único del pedido de compra. (PK) |
| 40 |  | user_id | INT | NO | Enteros positivos existentes en user | N/A | Usuario que realizó el pedido. (FK) |
| 41 |  | event_id | INT | NO | Enteros positivos existentes en event | N/A | Evento asociado al pedido. (FK) |
| 42 |  | total_amount | DECIMAL | NO | Valores monetarios positivos | 10.2 | Monto total de la compra realizada en el pedido. |
| 43 |  | currency | VARCHAR | SI | Código de moneda ISO | 3 | Moneda utilizada en la transacción (por defecto COP). |
| 44 |  | status | ENUM | SI | 'pending', 'processing', 'paid', 'failed', 'refunded' | N/A | Estado actual del proceso de pago del pedido. |
| 45 |  | created_at | TIMESTAMP | SI | Fecha y hora válidas | N/A | Fecha y hora en que se generó el pedido. |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `B8:C8`

