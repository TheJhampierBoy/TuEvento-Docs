---
id: TE-0097
title: "Diccionario de datos Tu-Evento"
lang: en
source: 04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx
source_sha256: 55e048637ab5260300cba10304b9cabffcf35f93612b8fc6af685a766436cc7d
conversion: "openpyxl 3.1.5 (data_only + formulas); without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "Visual formatting (colours, borders, widths, fonts and conditional formatting styles) is not kept."
  - "Merged cells are listed but not reproduced as a single cell."
  - "The formula values are the ones cached by Excel; they were not recalculated."
  - "Translation: the sheet names, entity and field names, data types and the enumeration values written in English in the original (for example «Pending, Approved, Rejected») are kept as in the original; «SI» is translated as «YES»."
status: borrador
reviewed_by: ""
translation_of: es/06_Base_Datos/Diccionario_Datos.md
es_sha256: 5388e7b80ee129f754f792e284baba32763cfdfbfa2e0eff01af4875daa05518
---
# Data dictionary Tu-Evento

> Conversion of `04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx`: 13 sheets (Seguridad, Cartera, Categorias, Geolocalizacion, Secciones, Sillas, Temas, Lenguaje, Notificaciones, Pagos, Perfil, Eventos, Tickets), 0 formulas. The columns are named with the Excel letter and each row with its original number.

## Sheet: Seguridad

Used range: `A1:G126` · 126 rows × 7 columns · merged cells: 13

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | SECURITY MODULE |  |  |  |  |  |  |
| 2 |  | Entity: account_lockout |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | account_lockout_id | INT | NO | Unique positive integers | — | Unique identifier of the account lockout record. (PK) |
| 5 |  | user_id | INT | NO | Existing user ID | — | Identifier of the user to whom the lockout record belongs. (FK) |
| 6 |  | failed_attempts | INT | NO | Integer ≥ 0 | — | Number of failed login attempts. |
| 7 |  | window_started_at | TIMESTAMP | NO | Valid date and time | — | Moment when the counting window of failed attempts starts. |
| 8 |  | locked_until | TIMESTAMP | YES | Valid date and time | — | Date and time until which the account remains locked. |
| 11 |  | Entity: account_activation |  |  |  |  |  |
| 12 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 13 |  | account_activation_id | INT | NO | Unique positive integers | — | Identifier of the account activation record. (PK) |
| 14 |  | user_id | INT | NO | Existing user ID | — | User to whom the activation process belongs. (FK) |
| 15 |  | activation_code | VARCHAR | NO | Alphanumeric code | 6 | Code used to activate the user's account. |
| 16 |  | activated | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the account has already been activated. |
| 17 |  | expires_at | TIMESTAMP | NO | Valid date and time | — | Moment when the activation code expires. |
| 18 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the activation record was created. |
| 20 |  | Entity: refresh_token |  |  |  |  |  |
| 21 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 22 |  | refresh_token_id | INT | NO | Unique positive integers | — | Unique identifier of the refresh token. (PK) |
| 23 |  | user_id | INT | NO | Existing user ID | — | User who owns the token. (FK) |
| 24 |  | auth_session_id | INT | NO | Existing session ID | — | Authentication session associated with the token. (FK) |
| 25 |  | token | VARCHAR | NO | Secure alphanumeric string | 512 | Token used to renew the authentication session. |
| 26 |  | issued_at | TIMESTAMP | NO | Valid date and time | — | Moment when the token was issued. |
| 27 |  | expires_at | TIMESTAMP | NO | Valid date and time | — | Moment when the token expires. |
| 28 |  | revoked | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the token has been revoked. |
| 29 |  | revoked_at | TIMESTAMP | YES | Valid date and time | — | Moment when the token was revoked. |
| 31 |  | Entity: user |  |  |  |  |  |
| 32 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 33 |  | user_id | INT | NO | Unique positive integers | — | Unique identifier of the user. (PK) |
| 34 |  | user_status_id | INT | NO | Existing status ID | — | Current status of the user within the system. (FK) |
| 35 |  | role_id | INT | NO | Existing role ID | — | Role assigned to the user within the system. (FK) |
| 36 |  | alias | VARCHAR | NO | Unique text | 50 | Alias or user name used to identify the user in the system. |
| 37 |  | activated | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the user's account is activated. |
| 40 |  | Entity: auth_session |  |  |  |  |  |
| 41 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 42 |  | auth_session_id | INT | NO | Unique positive integers | — | Unique identifier of the authentication session. (PK) |
| 43 |  | user_id | INT | NO | Existing user ID | — | User who owns the session. (FK) |
| 44 |  | access_token | VARCHAR | NO | Alphanumeric token | 512 | Access token used to authenticate requests. |
| 45 |  | issued_at | TIMESTAMP | NO | Valid date and time | — | Date and time of issuance of the access token. |
| 46 |  | expires_at | TIMESTAMP | NO | Valid date and time | — | Date and time of expiry of the session. |
| 47 |  | ip_address | VARCHAR | NO | Valid IP address | 45 | IP address from which the session originated. |
| 48 |  | user_agent | VARCHAR | NO | Descriptive text | 200 | Information about the user's browser or device. |
| 49 |  | revoked | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the session was revoked. |
| 50 |  | revoked_at | TIMESTAMP | YES | Valid date and time | — | Date on which the session was revoked. |
| 52 |  | Entity: user_status |  |  |  |  |  |
| 53 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 54 |  | user_status_id | INT | NO | Unique positive integers | — | Unique identifier of the user status. (PK) |
| 55 |  | code | VARCHAR | NO | Identifier code | 30 | Internal code of the user status. |
| 56 |  | name | VARCHAR | NO | Descriptive text | 60 | Name of the user status. |
| 57 |  | description | VARCHAR | NO | Descriptive text | 150 | Description of the meaning of the user status. |
| 59 |  | Entity: user_status_history |  |  |  |  |  |
| 60 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 61 |  | user_status_history_id | INT | NO | Unique positive integers | — | Identifier of the historical status record. (PK) |
| 62 |  | user_id | INT | NO | Existing user ID | — | User to whom the status change corresponds. (FK) |
| 63 |  | user_status_id | INT | NO | Existing status ID | — | Status assigned to the user at that moment. (FK) |
| 64 |  | reason | VARCHAR | NO | Descriptive text | 150 | Reason for which the change of the user's status occurred. |
| 66 |  | Entity: oauth_account |  |  |  |  |  |
| 67 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 68 |  | oauth_account_id | INT | NO | Unique positive integers | — | Identifier of the external authentication record. (PK) |
| 69 |  | user_id | INT | NO | Existing user ID | — | User who owns the OAuth account. (FK) |
| 70 |  | provider | VARCHAR | NO | Name of the OAuth provider | 40 | External authentication provider (Google, Facebook, etc.). |
| 71 |  | provider_user_id | VARCHAR | YES | External identifier | 100 | Identifier of the user within the OAuth provider. |
| 72 |  | email | VARCHAR | YES | Email address | 255 | Email associated with the OAuth account. |
| 73 |  | linked_at | TIMESTAMP | YES | Valid date and time | — | Date on which the external account was linked to the system. |
| 75 |  | Entity: organizer_petition |  |  |  |  |  |
| 76 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 77 |  | organizer_petition_id | INT | NO | Unique positive integers | — | Identifier of the request to become an organizer. (PK) |
| 78 |  | user_id | INT | NO | Existing user ID | — | User who makes the request. (FK) |
| 79 |  | document | BYTEA | NO | Binary file | — | Document sent by the user as support for the request. |
| 80 |  | applicationDate | TIMESTAMP | YES | Valid date and time | — | Date on which the user made the request. |
| 81 |  | status | ENUM | NO | Pending, Approved, Rejected | — | Current status of the organizer request. |
| 83 |  | Entity: permission |  |  |  |  |  |
| 84 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 85 |  | permission_id | INT | NO | Unique positive integers | — | Unique identifier of the system permission. (PK) |
| 86 |  | code | VARCHAR | NO | Internal code | 50 | Identifier code of the permission. |
| 87 |  | name | VARCHAR | NO | Descriptive text | 80 | Name of the permission within the system. |
| 88 |  | description | VARCHAR | NO | Descriptive text | 150 | Functional description of the permission. |
| 90 |  | Entity: role |  |  |  |  |  |
| 91 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 92 |  | role_id | INT | NO | Unique positive integers | — | Unique identifier of the system role. (PK) |
| 93 |  | code | VARCHAR | NO | Internal code | 50 | Code that identifies the role. |
| 94 |  | name | VARCHAR | NO | Descriptive text | 80 | Name of the role within the system. |
| 95 |  | description | VARCHAR | NO | Descriptive text | 150 | Description of the role and its responsibilities. |
| 97 |  | Entity: role_permission |  |  |  |  |  |
| 98 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 99 |  | role_permission_id | INT | NO | Unique positive integers | — | Identifier of the role-permission relationship. (PK) |
| 100 |  | permission_id | INT | NO | Existing permission ID | — | Permission associated with the role. (FK) |
| 101 |  | role_id | INT | NO | Existing role ID | — | Role to which the permission is assigned. (FK) |
| 103 |  | Entity: recover_password |  |  |  |  |  |
| 104 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 105 |  | recover_password_id | INT | NO | Unique positive integers | — | Identifier of the password recovery process. (PK) |
| 106 |  | user_id | INT | NO | Existing user ID | — | User who requests the password recovery. (FK) |
| 107 |  | code | VARCHAR | NO | Alphanumeric code | 8 | Code used to validate the password recovery. |
| 108 |  | code_status | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the code has already been used or validated. |
| 109 |  | expires_at | TIMESTAMP | NO | Valid date and time | — | Moment when the code stops being valid. |
| 110 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Date on which the recovery code was generated. |
| 111 |  | last_password_hash | VARCHAR | NO | Cryptographic hash | 255 | Last password registered by the user before the recovery. |
| 113 |  | Entity: password_history |  |  |  |  |  |
| 114 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 115 |  | password_history_id | INT | NO | Unique positive integers | — | Identifier of the password history record. (PK) |
| 116 |  | user_id | INT | NO | Existing user ID | — | User to whom the stored password belongs. (FK) |
| 117 |  | password_hash | VARCHAR | NO | Cryptographic hash | 255 | Encrypted password stored in the history. |
| 118 |  | changed_at | TIMESTAMP | NO | Valid date and time | — | Moment when the user changed their password. |
| 120 |  | Entity: login_credentials |  |  |  |  |  |
| 121 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 122 |  | login_credentials_id | INT | NO | Unique positive integers | — | Identifier of the user's access credentials. (PK) |
| 123 |  | user_id | INT | NO | Existing user ID | — | User who owns the credentials. (FK) |
| 124 |  | password_hash | VARCHAR | NO | Cryptographic hash | 255 | Encrypted password used for authentication. |
| 125 |  | email | VARCHAR | NO | Valid email address | 255 | Email used to log in. |
| 126 |  | last_login_at | TIMESTAMP | YES | Valid date and time | — | Date and time of the user's last login. |

**Merged cells** (the value appears only in the top-left cell): `B103:C103`, `B113:C113`, `B11:C11`, `B120:C120`, `B20:C20`, `B2:C2`, `B40:C40`, `B52:C52`, `B59:C59`, `B66:C66`, `B75:C75`, `B83:C83`, `B97:C97`


## Sheet: Cartera

Used range: `A1:G31` · 31 rows × 7 columns · merged cells: 2

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | WALLET MODULE |  |  |  |  |  |  |
| 2 |  | Entity: wallet |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | wallet_id | INT | NO | Unique positive integers | — | Unique identifier of the user's digital wallet. (PK) |
| 5 |  | user_id | INT | NO | Identifiers of existing users | — | Reference to the user who owns the wallet. (FK) |
| 6 |  | balance | DECIMAL(10,2) | NO | Positive or zero monetary values | 10.2 | Current balance available in the user's wallet. Default value: 0. |
| 7 |  | currency | STRING | NO | ISO currency codes (e.g.: COP, USD, EUR) | 3 | Currency in which the wallet operates. Default value: COP. |
| 9 |  | Entity: wallet_transaction |  |  |  |  |  |
| 10 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 11 |  | transaction_id | INT | NO | Unique integers | — | Unique identifier of the transaction carried out in the wallet. (PK) |
| 12 |  | wallet_id | INT | NO | Identifiers of existing wallets | — | Reference to the wallet where the transaction is recorded. (FK) |
| 13 |  | type | ENUM | NO | refund, top-up, withdrawal, payment | — | Type of operation carried out in the wallet. |
| 14 |  | amount | DECIMAL(10,2) | NO | Positive monetary values | 10.2 | Amount of money involved in the transaction. |
| 15 |  | status | ENUM | NO | pending, completed, failed | — | Current status of the transaction. |
| 16 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Moment when the transaction was recorded in the system. |
| 18 |  | Entity: wallet_reference |  |  |  |  |  |
| 19 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 20 |  | wallet_reference_id | INT | NO | Unique integers | — | Unique identifier of the reference of the transaction. (PK) |
| 21 |  | transaction_id | INT | NO | Identifiers of existing transactions | — | Reference to the associated wallet transaction. (FK) |
| 22 |  | entity_type | ENUM | YES | order, payment, refund | — | Type of system entity associated with the transaction. |
| 23 |  | entity_id | INT | YES | Identifiers of related entities | — | Identifier of the specific entity linked to the transaction. |
| 24 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Moment when the transaction was recorded in the system. |

**Merged cells** (the value appears only in the top-left cell): `B18:C18`, `B26:C26`


## Sheet: Categorias

Used range: `A1:G22` · 22 rows × 7 columns · merged cells: 2

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | CATEGORIES MODULE |  |  |  |  |  |  |
| 2 |  | Entity: category |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | category_id | INT | NO | Unique positive integers | — | Unique identifier of the category within the system. (PK) |
| 5 |  | name | VARCHAR | NO | Alphanumeric text | 50 | Name of the category used to classify events. |
| 6 |  | description | VARCHAR | NO | Descriptive text | 100 | Detailed description of the category. |
| 7 |  | active | BOOLEAN | NO | TRUE / FALSE | 1 | Indicates whether the category is active within the system. Default value: TRUE. |
| 8 |  | visible | BOOLEAN | NO | TRUE / FALSE | 1 | Determines whether the category is visible to users on the platform. Default value: TRUE. |
| 9 |  | dad_id | INT | YES | Identifiers of existing categories | — | Reference to the parent category in case there is a category hierarchy. (FK) |
| 11 |  | Entity: category_event |  |  |  |  |  |
| 12 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 13 |  | category_event_id | INT | NO | Unique positive integers | — | Unique identifier of the relationship between categories and events. (PK) |
| 14 |  | category_id | INT | NO | Identifiers of existing categories | — | Identifier of the category associated with the event. (PK, FK) |
| 15 |  | event_id | INT | NO | Identifiers of existing events | — | Identifier of the event associated with the category. (PK, FK) |

**Merged cells** (the value appears only in the top-left cell): `B11:C11`, `B2:C2`


## Sheet: Geolocalizacion

Used range: `A1:G45` · 45 rows × 7 columns · merged cells: 5

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | GEOLOCATION MODULE |  |  |  |  |  |  |
| 2 |  | Entity: department |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | department_id | INT | NO | Unique positive integers | — | Unique identifier of the department or administrative region. (PK) |
| 5 |  | name | VARCHAR | NO | Alphanumeric text | 100 | Official name of the department or geographic region. |
| 6 |  | code | VARCHAR | YES | Alphanumeric codes | 10 | Identifier code of the department according to the classification system used. |
| 8 |  | Entity: city |  |  |  |  |  |
| 9 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 10 |  | city_id | INT | NO | Unique positive integers | — | Unique identifier of the city registered in the system. (PK) |
| 11 |  | department_id | INT | NO | Identifiers of existing departments | — | Reference to the department to which the city belongs. (FK) |
| 12 |  | name | VARCHAR | NO | Alphanumeric text | 100 | Official name of the city. |
| 13 |  | code | VARCHAR | YES | Alphanumeric codes | 10 | Identifier code of the city within the system or territorial standard. |
| 15 |  | Entity: site |  |  |  |  |  |
| 16 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 17 |  | site_id | INT | NO | Unique positive integers | — | Unique identifier of the site or place where an event takes place. (PK) |
| 18 |  | city_id | INT | NO | Identifiers of existing cities | — | Reference to the city where the event site is located. (FK) |
| 19 |  | name | VARCHAR | NO | Alphanumeric text | 150 | Name of the place or establishment where the event takes place. |
| 20 |  | address | VARCHAR | NO | Alphanumeric text | 200 | Physical address of the site where the event takes place. |
| 21 |  | capacity | INT | YES | Positive integers | — | Maximum capacity of people that the site can hold. |
| 22 |  | latitude | DECIMAL | YES | Decimal values of geographic coordinates | 9.6 | Geographic latitude coordinate that indicates the location of the site. |
| 23 |  | longitude | DECIMAL | YES | Decimal values of geographic coordinates | 9.6 | Geographic longitude coordinate that indicates the location of the site. |

**Merged cells** (the value appears only in the top-left cell): `B15:C15`, `B25:C25`, `B2:C2`, `B34:C34`, `B8:C8`


## Sheet: Secciones

Used range: `A1:G15` · 15 rows × 7 columns · merged cells: 2

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | SECTIONS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: section_type |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 4 |  | section_type_id | INT | NO | Unique positive integers | — | Unique identifier of the section type. (PK) |
| 5 |  | name | VARCHAR | NO | Alphanumeric text | 100 | Name of the section type of the event (E.g.: VIP, General, Preferencial). |
| 7 |  | Entity: event_section |  |  |  |  |  |
| 8 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 9 |  | event_section_id | INT | NO | Unique positive integers | — | Unique identifier of the event section. (PK) |
| 10 |  | event_id | INT | NO | Identifiers of existing events | — | Event to which the section belongs. (FK) |
| 11 |  | section_type_id | INT | NO | Identifiers of existing section types | — | Assigned section type (VIP, General, etc.). (FK) |
| 12 |  | capacity | INT | NO | Positive integers | — | Maximum capacity of people allowed in the section. |
| 13 |  | available_seats | INT | NO | Positive integers | — | Number of seats available for reservation. |
| 14 |  | price | DECIMAL(10,2) | NO | Positive decimal values | 10.2 | Price of the ticket for that section. |
| 15 |  | is_active | BOOLEAN | NO | TRUE / FALSE | 1 | Indicates whether the section is available for sale. |

**Merged cells** (the value appears only in the top-left cell): `B2:C2`, `B7:C7`


## Sheet: Sillas

Used range: `A1:G46` · 46 rows × 7 columns · merged cells: 4

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | SEATS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: seat |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | seat_id | INT | NO | Unique positive integers | — | Unique identifier of the seat within the system. (PK) |
| 5 |  | seat_block_id | INT | NO | Positive integers that correspond to an existing seat block | — | Identifier of the seat block to which the seat belongs. (FK) |
| 6 |  | event_section_id | INT | NO | Positive integers that correspond to an existing event section | — | Identifier of the event section where the seat is located. (FK) |
| 7 |  | code | VARCHAR | NO | Alphanumeric seat identification codes (e.g.: A10, B5) | 20 | Unique code that identifies the seat within a section. |
| 8 |  | row | INT | NO | Positive integers | — | Number of the row where the seat is located within the block. |
| 9 |  | position | INT | NO | Positive integers | — | Position of the seat within the corresponding row. |
| 10 |  | type | ENUM | YES | regular, courtesy | — | Type of seat available in the event (regular or courtesy). |
| 11 |  | status | ENUM | YES | available, reserved, sold, courtesy | — | Current status of the seat within the reservation system. |
| 13 |  | Entity: seat_block |  |  |  |  |  |
| 14 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 15 |  | seat_block_id | INT | NO | Unique positive integers | — | Unique identifier of the seat block. (PK) |
| 16 |  | event_section_id | INT | NO | Positive integers corresponding to existing event sections | — | Identifier of the event section to which the seat block belongs. (FK) |
| 17 |  | name | VARCHAR | NO | Descriptive text of the seat block | 100 | Name of the block or seating zone within the event section. |
| 18 |  | capacity | INT | NO | Positive integers | — | Maximum number of seats that the block can contain. |
| 20 |  | Entity: seat_log |  |  |  |  |  |
| 21 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 22 |  | seat_log_id | INT | NO | Unique positive integers | — | Unique identifier of the history record of seat status changes. (PK) |
| 23 |  | seat_id | INT | NO | Positive integers corresponding to existing seats | — | Identifier of the seat on which the status change is recorded. (FK) |
| 24 |  | old_status | ENUM | YES | available, reserved, sold, courtesy | — | Previous status of the seat before the change was recorded. |
| 25 |  | new_status | ENUM | YES | available, reserved, sold, courtesy | — | New status assigned to the seat after the change. |
| 26 |  | change_at | TIMESTAMP | YES | Valid system date and time | — | Date and time when the change of status of the seat was recorded. |
| 27 |  | change_by | INT | YES | Positive integers corresponding to system users | — | Identifier of the user who made the status change. (FK) |
| 28 |  | reason | VARCHAR | YES | Descriptive text | 255 | Reason or explanation of the status change recorded for the seat. |

**Merged cells** (the value appears only in the top-left cell): `B13:C13`, `B20:C20`, `B2:C2`, `B40:C40`


## Sheet: Temas

Used range: `A1:G39` · 39 rows × 7 columns · merged cells: 5

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | THEMES MODULE |  |  |  |  |  |  |
| 2 |  | Entity: theme |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 4 |  | theme_id | INT | NO | Unique positive integers | — | Unique identifier of the visual theme of the system. (PK) |
| 5 |  | name | VARCHAR | NO | Alphanumeric text | 100 | Name of the visual theme available for the interface. |
| 6 |  | description | VARCHAR | NO | Descriptive text | 255 | Description of the style or appearance of the theme. |
| 7 |  | default_palette | JSONB | YES | JSON object with colour configuration | — | Default colour palette of the theme (colours, backgrounds, etc.). |
| 9 |  | Entity: user_theme |  |  |  |  |  |
| 10 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 11 |  | user_theme_id | INT | NO | Unique positive integers | — | Identifier of the user's theme configuration record. (PK) |
| 12 |  | user_id | INT | NO | Positive integers corresponding to existing users | — | Identifier of the user who uses the theme. (FK) |
| 13 |  | theme_id | INT | NO | Positive integers corresponding to existing themes | — | Identifier of the theme selected by the user. (FK) |
| 14 |  | is_active | BOOLEAN | YES | TRUE, FALSE | — | Indicates whether the theme is active for the user. |
| 15 |  | created_at | TIMESTAMP | YES | Valid date and time | — | Date and time when the theme was assigned to the user. |
| 16 |  | updated_at | TIMESTAMP | YES | Valid date and time | — | Date and time of the last update of the user's theme. |
| 18 |  | Entity: theme_customization |  |  |  |  |  |
| 19 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 20 |  | customization_id | INT | NO | Unique positive integers | — | Unique identifier of the theme customization. (PK) |
| 21 |  | user_theme_id | INT | NO | Positive integers corresponding to user theme configurations | — | Identifier of the theme configuration associated with the user. (FK) |
| 22 |  | property | VARCHAR | NO | Name of the visual property | 100 | Customized visual property of the theme (e.g.: color_header, background). |
| 23 |  | value | VARCHAR | YES | Value associated with the property | 255 | Value assigned to the customization property. |
| 24 |  | created_at | TIMESTAMP | YES | Valid date and time | — | Date on which the customization was created. |
| 25 |  | updated_at | TIMESTAMP | YES | Valid date and time | — | Date of the last modification of the customization. |
| 27 |  | Entity: theme_log |  |  |  |  |  |
| 28 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 29 |  | log_id | INT | NO | Unique positive integers | — | Unique identifier of the theme change record. (PK) |
| 30 |  | user_theme_id | INT | NO | Positive integers corresponding to user theme configurations | — | Identifier of the theme configured for the user. (FK) |
| 31 |  | action | VARCHAR | YES | Descriptive text of the action | 50 | Action performed on the theme (create, update, activate, etc.). |

**Merged cells** (the value appears only in the top-left cell): `B18:C18`, `B27:C27`, `B2:C2`, `B33:C33`, `B9:C9`


## Sheet: Lenguaje

Used range: `A1:G145` · 145 rows × 7 columns · merged cells: 16

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | LANGUAGES MODULE |  |  |  |  |  |  |
| 2 |  | Entity: language |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | language_id | INT | NO | Positive integers | — | Unique identifier of the language in the system (PK) |
| 5 |  | code | VARCHAR | NO | Language code (e.g.: es, en, fr) | 10 | Abbreviated code of the language used by the system |
| 6 |  | name | VARCHAR | NO | Name of the language | 50 | Descriptive name of the language available in the system |
| 7 |  | is_active | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the language is active within the system |
| 9 |  | Entity: event_translation |  |  |  |  |  |
| 10 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 11 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of the event (PK) |
| 12 |  | event_id | INT | NO | Existing event ID | — | Event to which the translation belongs (FK) |
| 13 |  | language_id | INT | NO | Existing language ID | — | Language into which the translation is made (FK) |
| 14 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the event |
| 15 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the event |
| 16 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 18 |  | Entity: event_rating_translation |  |  |  |  |  |
| 19 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 20 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of the rating (PK) |
| 21 |  | rating_id | INT | NO | Existing rating ID | — | Rating associated with the translation (FK) |
| 22 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 23 |  | translated_comment | VARCHAR | NO | Text | 255 | Translated comment of the rating |
| 24 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 26 |  | Entity: notification_translation |  |  |  |  |  |
| 27 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 28 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of the notification (PK) |
| 29 |  | notification_id | INT | NO | Existing notification ID | — | Associated notification (FK) |
| 30 |  | language_id | INT | NO | Existing language ID | — | Language in which the translation is (FK) |
| 31 |  | translated_subject | VARCHAR | NO | Text | 100 | Translated subject of the notification |
| 32 |  | translated_body | VARCHAR | NO | Text | 255 | Translated content of the notification |
| 33 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 35 |  | Entity: event_comment_reply_translation |  |  |  |  |  |
| 36 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 37 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of a reply (PK) |
| 38 |  | reply_id | INT | NO | Existing reply ID | — | Reply associated with the translation (FK) |
| 39 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 40 |  | translated_reply_text | VARCHAR | NO | Text | 255 | Translated text of the reply |
| 41 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 43 |  | Entity: profile_translation |  |  |  |  |  |
| 44 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 45 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of the profile (PK) |
| 46 |  | profile_id | INT | NO | Existing profile ID | — | Profile to which the translation belongs (FK) |
| 47 |  | language_id | INT | NO | Existing language ID | — | Language in which the translation is (FK) |
| 48 |  | translated_bio | VARCHAR | NO | Text | 255 | Translated biography of the user |
| 49 |  | source | VARCHAR | NO | manual / automatic | 50 | Source of the translation made |
| 50 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 52 |  | Entity: channel_translation |  |  |  |  |  |
| 53 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 54 |  | translation_id | INT | NO | Positive integers | — | Identifier of the translation of the channel (PK) |
| 55 |  | channel_id | INT | NO | Existing channel ID | — | Channel associated with the translation (FK) |
| 56 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 57 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the channel |
| 58 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the channel |
| 59 |  | source | VARCHAR | NO | manual / automatic | 50 | Source of the translation |
| 60 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation |
| 62 |  | Entity: section_type_translation |  |  |  |  |  |
| 63 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 64 |  | translation_id | INT | NO | Positive integers | — | Translation identifier of the section type (PK) |
| 65 |  | section_type_id | INT | NO | Existing section ID | — | Associated section type (FK) |
| 66 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 67 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the section type |
| 68 |  | source | VARCHAR | NO | manual / automatic | 50 | Source of the translation |
| 69 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 71 |  | Entity: category_translation |  |  |  |  |  |
| 72 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 73 |  | translation_id | INT | NO | Positive integers | — | Category translation identifier (PK) |
| 74 |  | category_id | INT | NO | Existing category ID | — | Associated category (FK) |
| 75 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 76 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the category |
| 77 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the category |
| 78 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 79 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 81 |  | Entity: category_translation |  |  |  |  |  |
| 82 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 83 |  | translation_id | INT | NO | Positive integers | — | Category translation identifier (PK) |
| 84 |  | category_id | INT | NO | Existing category ID | — | Associated category (FK) |
| 85 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 86 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the category |
| 87 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the category |
| 88 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 89 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 91 |  | Entity: review_translation |  |  |  |  |  |
| 92 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 93 |  | translation_id | INT | NO | Positive integers | — | Review translation identifier (PK) |
| 94 |  | review_id | INT | NO | Existing review ID | — | Associated review (FK) |
| 95 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 96 |  | translated_comment | VARCHAR | NO | Text | 255 | Translated comment of the review |
| 97 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 98 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 100 |  | Entity: seat_block_translation |  |  |  |  |  |
| 101 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 102 |  | translation_id | INT | NO | Positive integers | — | Translation identifier of the seat block (PK) |
| 103 |  | seat_block_id | INT | NO | Existing block ID | — | Associated seat block (FK) |
| 104 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 105 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the seat block |
| 106 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 107 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 109 |  | Entity: notification_type_translation |  |  |  |  |  |
| 110 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 111 |  | translation_id | INT | NO | Positive integers | — | Translation identifier of the notification type (PK) |
| 112 |  | notification_type_id | INT | NO | Existing notification type ID | — | Associated notification type (FK) |
| 113 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 114 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the notification type |
| 115 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the notification type |
| 116 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 117 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 119 |  | Entity: theme_translation |  |  |  |  |  |
| 120 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 121 |  | translation_id | INT | NO | Positive integers | — | Translation identifier of the theme (PK) |
| 122 |  | theme_id | INT | NO | Existing theme ID | — | Theme associated with the translation (FK) |
| 123 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 124 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the theme |
| 125 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the theme |
| 126 |  | source | VARCHAR | NO | manual / automatic | 50 | Translation source |
| 127 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 129 |  | Entity: module_translation |  |  |  |  |  |
| 130 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 131 |  | translation_id | INT | NO | Positive integers | — | Translation identifier of the module (PK) |
| 132 |  | module_string | VARCHAR | NO | Module identifier | 100 | String that identifies the module of the system |
| 133 |  | language_id | INT | NO | Existing language ID | — | Language of the translation (FK) |
| 134 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the module |
| 135 |  | source | VARCHAR | NO | manual / automatic | 50 | Source of the translation |
| 136 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |
| 138 |  | Entity: action_translation |  |  |  |  |  |
| 139 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 140 |  | translation_id | INT | NO | Positive integers | — | Unique identifier of the translation of the event (PK) |
| 141 |  | event_id | INT | NO | Existing event ID | — | Event to which the translation belongs (FK) |
| 142 |  | language_id | INT | NO | Existing language ID | — | Language into which the translation is made (FK) |
| 143 |  | translated_name | VARCHAR | NO | Text | 100 | Translated name of the event |
| 144 |  | translated_description | VARCHAR | NO | Text | 255 | Translated description of the event |
| 145 |  | status | ENUM | NO | automatic, reviewed, rejected | — | Status of the translation process |

**Merged cells** (the value appears only in the top-left cell): `B100:E100`, `B109:D109`, `B119:C119`, `B129:D129`, `B138:C138`, `B18:D18`, `B26:D26`, `B2:C2`, `B35:E35`, `B43:C43`, `B52:C52`, `B62:D62`, `B71:D71`, `B81:D81`, `B91:D91`, `B9:C9`


## Sheet: Notificaciones

Used range: `A1:G35` · 35 rows × 7 columns · merged cells: 4

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | NOTIFICATIONS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: notification |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | notification_id | INT | NO | Positive integers | — | Unique identifier of the notification in the system (PK) |
| 5 |  | channel_id | INT | NO | Existing channel ID | — | Channel through which the notification is sent (FK) |
| 6 |  | notification_type_id | INT | NO | Existing notification type ID | — | Associated notification type (FK) |
| 7 |  | event_id | INT | NO | Existing event ID | — | Event related to the notification (FK) |
| 8 |  | subject | VARCHAR | NO | Text | 150 | Subject or title of the notification sent to the user |
| 9 |  | body | TEXT | NO | Text | — | Content or message of the notification |
| 10 |  | sent_at | TIMESTAMP | YES | Valid date and time | — | Date and time when the notification was sent |
| 12 |  | Entity: notification_type |  |  |  |  |  |
| 13 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 14 |  | notification_type_id | INT | NO | Positive integers | — | Identifier of the notification type (PK) |
| 15 |  | name | VARCHAR | NO | Text | 50 | Name of the notification type |
| 16 |  | description | VARCHAR | NO | Text | 100 | Description of the notification type |
| 17 |  | active | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the notification type is active in the system |
| 19 |  | Entity: channel |  |  |  |  |  |
| 20 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 21 |  | channel_id | INT | NO | Positive integers | — | Unique identifier of the notification channel (PK) |
| 22 |  | name | VARCHAR | NO | Text | 50 | Name of the notification channel (e.g.: Email, SMS) |
| 23 |  | description | VARCHAR | NO | Text | 100 | Description of the channel |
| 24 |  | active | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the channel is enabled in the system |
| 25 |  | config | JSONB | YES | Configuration in JSON format | — | Technical configuration of the sending channel |
| 27 |  | Entity: notification_user |  |  |  |  |  |
| 28 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 29 |  | notification_user_id | INT | NO | Positive integers | — | Identifier of the notification record per user (PK) |
| 30 |  | notification_id | INT | NO | Existing notification ID | — | Notification associated with the user (FK) |
| 31 |  | user_id | INT | NO | Existing user ID | — | User who receives the notification (FK) |
| 32 |  | email_address | VARCHAR | NO | Valid email address | 255 | Email of the recipient of the notification |
| 33 |  | delivered_status | ENUM | NO | Pending, Sent, Delivered, Failed | — | Delivery status of the notification |
| 34 |  | error_message | VARCHAR | YES | Text | 255 | Error message in case the sending fails |
| 35 |  | read_at | TIMESTAMP | YES | Valid date and time | — | Date and time when the user read the notification |

**Merged cells** (the value appears only in the top-left cell): `B12:C12`, `B19:C19`, `B27:D27`, `B2:D2`


## Sheet: Pagos

Used range: `A1:G47` · 47 rows × 7 columns · merged cells: 2

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | PAYMENTS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: payment |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | payment_id | INT | NO | Positive integers | — | Unique identifier of the payment registered in the system (PK) |
| 5 |  | order_id | INT | NO | Existing order ID | — | Order associated with the payment made (FK) |
| 6 |  | gateway | ENUM | NO | fake, wompi | — | Payment gateway used to process the transaction |
| 7 |  | gateway_transaction_id | VARCHAR | NO | Gateway transaction identifier | 100 | Code of the transaction generated by the payment gateway |
| 8 |  | status | ENUM | NO | pending, approved, rejected, error, refunded | — | Current status of the payment within the system |
| 9 |  | amount | DECIMAL | NO | Positive numeric values | 10.2 | Total amount paid in the transaction |
| 10 |  | payment_method | ENUM | NO | card, pse, nequi, cash | — | Payment method used by the user |
| 11 |  | processed_at | TIMESTAMP | YES | Valid date and time | — | Date and time when the payment was processed |
| 13 |  | Entity: payment_log |  |  |  |  |  |
| 14 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 15 |  | payment_log_id | INT | NO | Positive integers | — | Unique identifier of the payment history record (PK) |
| 16 |  | payment_id | INT | NO | Existing payment ID | — | Payment associated with the history record (FK) |
| 17 |  | old_status | ENUM | NO | pending, processing, paid, failed, refunded | — | Previous status of the payment before the update |
| 18 |  | new_status | ENUM | NO | pending, processing, paid, failed, refunded | — | New status of the payment after the change |
| 19 |  | changed_at | TIMESTAMP | NO | Valid date and time | — | Moment when the status change occurred |
| 20 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Date on which the change was recorded in the history |
| 21 |  | reason | VARCHAR | YES | Text | 255 | Reason for the change of status of the payment |
| 23 |  | Entity: transaction_webhook |  |  |  |  |  |
| 24 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 25 |  | webhook_id | INT | NO | Positive integers | — | Identifier of the webhook received from the payment gateway (PK) |
| 26 |  | payment_id | INT | NO | Existing payment ID | — | Payment related to the received webhook (FK) |
| 27 |  | payload | JSONB | NO | Data in JSON format | — | Information sent by the payment gateway |
| 28 |  | received_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the webhook was received |
| 30 |  | Entity: refund |  |  |  |  |  |
| 31 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 32 |  | refund_id | INT | NO | Positive integers | — | Unique identifier of the requested refund (PK) |
| 33 |  | payment_id | INT | NO | Existing payment ID | — | Payment for which the refund is requested (FK) |
| 34 |  | status | ENUM | NO | requested, approved, processed, failed | — | Status of the refund process |
| 35 |  | reason | VARCHAR | YES | Text | 255 | Reason for the requested refund |
| 36 |  | requested_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the refund was requested |
| 37 |  | processed_at | TIMESTAMP | YES | Valid date and time | — | Date and time when the refund was processed |
| 39 |  | Entity: order |  |  |  |  |  |
| 40 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 41 |  | order_id | INT | NO | Positive integers | — | Unique identifier of the purchase order (PK) |
| 42 |  | user_id | INT | NO | Existing user ID | — | User who places the purchase order (FK) |
| 43 |  | event_id | INT | NO | Existing event ID | — | Event associated with the purchase of tickets (FK) |
| 44 |  | total_amount | DECIMAL | NO | Positive numeric values | 10.2 | Total amount of the order |
| 45 |  | currency | VARCHAR | NO | Currency code | 3 | Currency used in the transaction (COP by default) |
| 46 |  | status | ENUM | NO | pending, processing, paid, failed, refunded | — | Current status of the purchase order |
| 47 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Creation date of the order |

**Merged cells** (the value appears only in the top-left cell): `B13:C13`, `B23:D23`


## Sheet: Perfil

Used range: `A1:G45` · 45 rows × 7 columns · merged cells: 2

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | PROFILE MODULE |  |  |  |  |  |  |
| 2 |  | Entity: profile |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | profile_id | INT | NO | Positive integers | — | Unique identifier of the user's profile (PK) |
| 5 |  | user_id | INT | NO | Existing user ID | — | User to whom the profile belongs (FK) |
| 6 |  | city_id | INT | NO | Existing city ID | — | City registered in the user's profile (FK) |
| 7 |  | full_name | VARCHAR | NO | Text | 100 | Full name of the user |
| 8 |  | photo_url | VARCHAR | NO | Valid URL | 255 | Address of the user's profile picture |
| 9 |  | bio | VARCHAR | YES | Text | 255 | Description or biography of the user |
| 11 |  | Entity: profile_log |  |  |  |  |  |
| 12 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 13 |  | log_id | INT | NO | Positive integers | — | Identifier of the profile change record (PK) |
| 14 |  | profile_id | INT | NO | Existing profile ID | — | Profile to which the recorded change belongs (FK) |
| 15 |  | action | VARCHAR | NO | Text | 50 | Action performed on the profile |
| 16 |  | old_value | VARCHAR | YES | Text | 255 | Previous value before the modification |
| 17 |  | new_value | VARCHAR | YES | Text | 255 | New value after the change |
| 18 |  | occurred_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the change was made |
| 20 |  | Entity: activity_log |  |  |  |  |  |
| 21 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 22 |  | log_id | INT | NO | Positive integers | — | Unique identifier of the activity record (PK) |
| 23 |  | user_id | INT | NO | Existing user ID | — | User who performed the recorded action (FK) |
| 24 |  | module | VARCHAR | NO | Text | 50 | Name of the module where the action occurred |
| 25 |  | action | VARCHAR | NO | Text | 100 | Action performed by the user |
| 26 |  | reference_id | INT | YES | ID related to the action | — | Identifier of the affected record |
| 27 |  | occurred_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the activity occurred |
| 29 |  | Entity: wallet_summary |  |  |  |  |  |
| 30 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 31 |  | summary_id | INT | NO | Positive integers | — | Identifier of the summary of wallet movements (PK) |
| 32 |  | user_id | INT | NO | Existing user ID | — | User who owns the summary (FK) |
| 33 |  | wallet_id | INT | NO | Existing wallet ID | — | Wallet associated with the summary (FK) |
| 34 |  | transaction_id | INT | NO | Existing transaction ID | — | Transaction related to the summary (FK) |
| 35 |  | type | ENUM | NO | recharge, payment, refund | — | Type of movement recorded in the wallet |
| 36 |  | amount | DECIMAL | NO | Positive numeric values | 10.2 | Amount of the transaction |
| 37 |  | occurred_at | TIMESTAMP | NO | Valid date and time | — | Date and time when the transaction occurred |
| 39 |  | Entity: preferences |  |  |  |  |  |
| 40 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 41 |  | preference_id | INT | NO | Positive integers | — | Unique identifier of the registered preference (PK) |
| 42 |  | user_id | INT | NO | Existing user ID | — | User to whom the preferences belong (FK) |
| 43 |  | language_id | INT | NO | Existing language ID | — | Language selected by the user (FK) |
| 44 |  | theme_id | INT | NO | Existing theme ID | — | Visual theme selected by the user (FK) |
| 45 |  | notifications | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the user has notifications enabled |

**Merged cells** (the value appears only in the top-left cell): `B29:C29`, `B39:C39`


## Sheet: Eventos

Used range: `A1:G60` · 60 rows × 7 columns · merged cells: 7

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | EVENTS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: event_layout |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 4 |  | event_layout_id | INT | NO | Positive integers | — | Unique identifier of the layout of the event (PK) |
| 5 |  | event_id | INT | NO | Existing event ID | — | Event to which the layout belongs (FK) |
| 6 |  | layout_data | JSONB | NO | Data in JSON format | — | Information on the design or distribution of the event |
| 8 |  | Entity: event_media |  |  |  |  |  |
| 9 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 10 |  | media_id | INT | NO | Positive integers | — | Unique identifier of the multimedia resource (PK) |
| 11 |  | event_id | INT | NO | Existing event ID | — | Event to which the multimedia file belongs (FK) |
| 12 |  | img_url | VARCHAR | NO | Valid URL | 255 | Address of the image or multimedia resource of the event |
| 14 |  | Entity: event_media_log |  |  |  |  |  |
| 15 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 16 |  | media_log_id | INT | NO | Positive integers | — | Identifier of the change history of the multimedia content (PK) |
| 17 |  | event_id | INT | NO | Existing event ID | — | Event related to the record (FK) |
| 18 |  | media_id | INT | NO | Multimedia resource ID | — | Related multimedia resource (FK) |
| 19 |  | img_url | VARCHAR | NO | Valid URL | 255 | Address of the stored multimedia resource |
| 20 |  | version | INT | NO | Positive integers | — | Version of the multimedia resource |
| 21 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the multimedia resource is visible |
| 23 |  | Entity: event_rating |  |  |  |  |  |
| 24 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 25 |  | rating_id | INT | NO | Positive integers | — | Unique identifier of the rating of the event (PK) |
| 26 |  | event_id | INT | NO | Existing event ID | — | Event that receives the rating (FK) |
| 27 |  | user_id | INT | NO | Existing user ID | — | User who makes the rating (FK) |
| 28 |  | rating | INT | NO | Values between 1 and 5 | — | Rating given to the event |
| 29 |  | comment | VARCHAR | NO | Text | 255 | Comment associated with the rating |
| 30 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the rating is visible |
| 31 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Date on which the rating was made |
| 33 |  | Entity: event_comment_reply |  |  |  |  |  |
| 34 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 35 |  | reply_id | INT | NO | Positive integers | — | Identifier of the reply to the comment (PK) |
| 36 |  | parent_reply_id | INT | YES | Existing reply ID | — | Allows nested replies |
| 37 |  | rating_id | INT | NO | Existing rating ID | — | Rating to which the reply belongs (FK) |
| 38 |  | user_id | INT | NO | Existing user ID | — | User who makes the reply (FK) |
| 39 |  | reply_text | VARCHAR | NO | Text | 255 | Content of the reply to the comment |
| 40 |  | is_visible | BOOLEAN | NO | TRUE / FALSE | — | Indicates whether the reply is visible |
| 41 |  | created_at | TIMESTAMP | NO | Valid date and time | — | Creation date of the reply |
| 43 |  | Entity: event_status_log |  |  |  |  |  |
| 44 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 45 |  | status_log_id | INT | NO | Positive integers | — | Identifier of the status history of the event (PK) |
| 46 |  | event_id | INT | NO | Existing event ID | — | Event associated with the status change (FK) |
| 47 |  | old_status | ENUM | NO | Draft, Published, Cancelled, Completed | — | Previous status of the event |
| 48 |  | new_status | ENUM | NO | Draft, Published, Cancelled, Completed | — | New status of the event |
| 49 |  | changed_at | TIMESTAMP | NO | Valid date and time | — | Date and time of the status change |
| 50 |  | changed_by | INT | NO | Existing user ID | — | User who made the change |
| 52 |  | Entity: event |  |  |  |  |  |
| 53 |  | Field name | Data type | Accepts null values? | Acceptable values | Length | Description |
| 54 |  | event_section_id | INT | NO | Unique positive integers | — | Unique identifier of the event section. (PK) |
| 55 |  | event_id | INT | NO | Identifiers of existing events | — | Event to which the section belongs. (FK) |
| 56 |  | section_type_id | INT | NO | Identifiers of existing section types | — | Assigned section type (VIP, General, etc.). (FK) |
| 57 |  | capacity | INT | NO | Positive integers | — | Maximum capacity of people allowed in the section. |
| 58 |  | available_seats | INT | NO | Positive integers | — | Number of seats available for reservation. |
| 59 |  | price | DECIMAL(10,2) | NO | Positive decimal values | 10.2 | Price of the ticket for that section. |
| 60 |  | is_active | BOOLEAN | NO | TRUE / FALSE | 1 | Indicates whether the section is available for sale. |

**Merged cells** (the value appears only in the top-left cell): `B14:C14`, `B23:C23`, `B2:C2`, `B33:D33`, `B43:C43`, `B52:C52`, `B8:C8`


## Sheet: Tickets

Used range: `A1:G45` · 45 rows × 7 columns · merged cells: 1

| Row | A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|---|
| 1 | TICKETS MODULE |  |  |  |  |  |  |
| 2 |  | Entity: seat_ticket |  |  |  |  |  |
| 3 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 4 |  | seat_id | INT | NO | Positive integers existing in the seat table | N/A | Identifier of the seat associated with the ticket. (PK, FK) |
| 5 |  | ticket_id | INT | NO | Positive integers existing in the ticket table | N/A | Identifier of the ticket associated with the seat. (PK, FK) |
| 6 |  | price | DECIMAL | NO | Positive monetary values | 10.2 | Price assigned to the seat within the ticket. |
| 8 |  | Entity: ticket_checkin |  |  |  |  |  |
| 9 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 10 |  | checkin_id | INT | NO | Unique positive integers | N/A | Unique identifier of the check-in record. (PK) |
| 11 |  | ticket_id | INT | NO | Positive integers existing in the ticket table | N/A | Ticket used to perform the check-in to the event. (FK) |
| 12 |  | checkin_time | TIMESTAMP | YES | Valid date and time | N/A | Exact moment when the ticket was validated at the event. |
| 13 |  | validated_by | INT | YES | Identifier of the user who validates the access | N/A | User responsible for validating the ticket during entry to the event. (FK) |
| 15 |  | Entity: ticket_log |  |  |  |  |  |
| 16 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 17 |  | ticket_log_id | INT | NO | Unique positive integers | N/A | Identifier of the historical record of ticket changes. (PK) |
| 18 |  | ticket_id | INT | NO | Positive integers existing in ticket | N/A | Identifier of the ticket to which the record belongs. (FK) |
| 19 |  | old_status | ENUM | YES | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | Previous status of the ticket before the change. |
| 20 |  | new_status | ENUM | YES | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | New status assigned to the ticket after the modification. |
| 21 |  | changed_at | TIMESTAMP | YES | Valid date and time | N/A | Date and time when the change of status of the ticket was made. |
| 22 |  | changed_by | INT | YES | User identifier | N/A | User responsible for modifying the status of the ticket. (FK) |
| 23 |  | reason | VARCHAR | YES | Descriptive text | 255 | Reason or justification of the change of status of the ticket. |
| 25 |  | Entity: ticket |  |  |  |  |  |
| 26 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 27 |  | ticket_id | INT | NO | Unique positive integers | N/A | Unique identifier of the ticket generated for an event. (PK) |
| 28 |  | event_id | INT | NO | Positive integers existing in event | N/A | Identifier of the event to which the ticket belongs. (FK) |
| 29 |  | user_id | INT | NO | Positive integers existing in user | N/A | User who owns the ticket. (FK) |
| 30 |  | order_id | INT | NO | Positive integers existing in order | N/A | Order through which the ticket was acquired. (FK) |
| 31 |  | code | VARCHAR | NO | Alphanumeric code | 20 | Unique code of the ticket used for validation. |
| 32 |  | qr_code | VARCHAR | YES | Encoded string | 255 | QR code generated for the digital validation of the ticket. |
| 33 |  | status | ENUM | YES | 'draft', 'payment pending', 'paid', 'cancelled', 'refunded', 'used' | N/A | Current status of the ticket within the purchase or use process. |
| 34 |  | expiration_date | DATE | YES | Valid dates | N/A | Validity deadline of the ticket. |
| 35 |  | total_price | DECIMAL | NO | Positive monetary values | 10.2 | Total price paid for the ticket. |
| 37 |  | Entity: order |  |  |  |  |  |
| 38 |  | Field name | Data type | Accepts null values? | Acceptable values | Character length | Description |
| 39 |  | order_id | INT | NO | Unique positive integers | N/A | Unique identifier of the purchase order. (PK) |
| 40 |  | user_id | INT | NO | Positive integers existing in user | N/A | User who placed the order. (FK) |
| 41 |  | event_id | INT | NO | Positive integers existing in event | N/A | Event associated with the order. (FK) |
| 42 |  | total_amount | DECIMAL | NO | Positive monetary values | 10.2 | Total amount of the purchase made in the order. |
| 43 |  | currency | VARCHAR | YES | ISO currency code | 3 | Currency used in the transaction (COP by default). |
| 44 |  | status | ENUM | YES | 'pending', 'processing', 'paid', 'failed', 'refunded' | N/A | Current status of the order's payment process. |
| 45 |  | created_at | TIMESTAMP | YES | Valid date and time | N/A | Date and time when the order was generated. |

**Merged cells** (the value appears only in the top-left cell): `B8:C8`

