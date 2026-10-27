---
title: "Data dictionary"
lang: en
source: "06_Base_Datos/Script_BD_implementado.sql"
generated_from: "lozano2303/TuEvento origin/develop 2d259e7 (Liquibase 4.31.1, PostgreSQL 17.10)"
generated_on: 2026-10-24
status: borrador
reviewed_by: ""
translation_of: es/06_Base_Datos/Diccionario_Datos.md
es_sha256: d26956fadb060794223d49992c2a985ce2430671f49bb743e850c2a2513ab199
---
# Data dictionary — Tu Evento

> **Draft generated from the implemented schema.** This dictionary was generated on 2026-10-24 from [`Script_BD_implementado.sql`](Script_BD_implementado.sql): the 171 Liquibase 4.31.1 changesets of `lozano2303/TuEvento` (`origin/develop` / `2d259e7`) applied to a temporary PostgreSQL 17.10. Names, types, nullability, keys and default values come from the schema. Descriptions come from database comments and code comments (Javadoc); where there is none, the description was derived from the code and is marked *[D]*. Each table's module comes from the JPA entity that maps it.
>
> Summary: 75 tables, 570 columns; 254 column and 65 table descriptions derived from the code (*[D]*), pending team review.
>
> The previous version of this document (design dictionary converted from the XLSX `04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx`) is kept in the Git history: `git show 5e68501:en/06_Base_Datos/Diccionario_Datos.md`.

**Key column legend:** PK = primary key · FK → `table.column` = foreign key · UQ = part of a UNIQUE constraint.

**Rule-generated descriptions.** Descriptions marked *[R1]*–*[R4]* do not come from comments: they are derived from the schema structure without interpretation. Unmarked descriptions come from database or code comments. *[R1]* PK column with `IDENTITY` → "Unique identifier of the table (PK, IDENTITY)." · *[R2]* `created_at`, `created_by`, `updated_at` and `updated_by` columns → standard audit description (in entities extending `JpaAuditingEntity`, `created_by` and `updated_by` store the authenticated user's name or `system`, according to `shared/infrastructure/config/JpaConfig.java`) · *[R3]* foreign key column → "Reference to table.column." · *[R4]* column with a list CHECK constraint → "Allowed values: …".

**Code-derived descriptions.** *[D]* marks a description written on 2026-10-24 from the column name, the JPA entity that maps it, its validations and its use in the use cases and repositories of `2d259e7`. It is an interpretation, not a schema comment: the team should review it and, if correct, remove the mark.

**Contents**

1. [`category`](#mod-category) — 2 tables
2. [`event`](#mod-event) — 7 tables
3. [`geolocation`](#mod-geolocation) — 3 tables
4. [`language`](#mod-language) — 16 tables
5. [`notification`](#mod-notification) — 4 tables
6. [`payment`](#mod-payment) — 4 tables
7. [`profile`](#mod-profile) — 2 tables
8. [`seat`](#mod-seat) — 3 tables
9. [`section`](#mod-section) — 2 tables
10. [`sectiontype`](#mod-sectiontype) — 0 tables
11. [`security`](#mod-security) — 16 tables
12. [`storage`](#mod-storage) — 4 tables
13. [`theme`](#mod-theme) — 4 tables
14. [`ticket`](#mod-ticket) — 5 tables
15. [`wallet`](#mod-wallet) — 3 tables

<a id="mod-category"></a>

## 1. Module `category`

### 1.1 `category`

**Description:** Event categories (hierarchical through `dad_id`). *[D]*

**Created in changeset:** `047-create-category.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(50)` | NO | UQ | — | Unique category name. *[D]* |
| `description` | `character varying(100)` | NO | — | — | Category description. *[D]* |
| `active` | `boolean` | NO | — | `true` | Whether the category is active; creating an event requires an active category. *[D]* |
| `visible` | `boolean` | NO | — | `true` | Whether the category is shown in the interface. *[D]* |
| `dad_id` | `integer` | YES | FK → `category.category_id` | — | Parent category; null for a root category. |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | NO | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | NO | — | — | User or process that last modified the record (audit). *[R2]* |

### 1.2 `category_event`

**Description:** Many-to-many relation between events and categories. *[D]*

**Created in changeset:** `048-create-category-event.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `category_event_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | Category linked to the event. |
| `event_id` | `integer` | NO | UQ, FK → `event.event_id` | — | Event linked to the category. |

<a id="mod-event"></a>

## 2. Module `event`

### 2.1 `event`

**Description:** Events created by organizers, with their site, dates, capacity and status in the DRAFT → PENDING_REVIEW → PUBLISHED flow. *[D]*

**Created in changeset:** `039-create-event.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `site_id` | `bigint` | NO | UQ, FK → `site.site_id` | — | Reference to `site.site_id`. *[R3]* |
| `event_name` | `character varying(100)` | NO | UQ | — | Event name; together with the start date and site it cannot be repeated. *[D]* |
| `description` | `character varying(255)` | NO | — | — | Event description. *[D]* |
| `start_date` | `date` | NO | UQ | — | Event start date. *[D]* CHECK constraint: `CHECK ((finish_date > start_date))`. |
| `finish_date` | `date` | NO | — | — | Event end date. *[D]* CHECK constraint: `CHECK ((finish_date > start_date))`. |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | Allowed values: `DRAFT`, `PENDING_REVIEW`, `PUBLISHED`, `REJECTED`, `CANCELLED`, `COMPLETED`. *[R4]* |
| `is_public` | `boolean` | NO | — | `true` | Whether the event appears in the public catalog when PUBLISHED. *[D]* |
| `available_seats` | `integer` | NO | — | — | Event capacity; cannot exceed the site's capacity. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |
| `rejection_reason` | `text` | YES | — | — | Rejection reason; filled when the status is REJECTED and cleared when it returns to DRAFT. |

### 2.2 `event_layout`

**Description:** Event seating plan saved by the layout editor. *[D]*

**Created in changeset:** `041-create-event-layout.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_layout_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `layout_data` | `jsonb` | NO | — | — | JSON of the sections, blocks and seats plan saved by the layout editor. *[D]* |

### 2.3 `event_log`

**Description:** Log of changes made to an event. *[D]*

**Created in changeset:** `093-create-event-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `action` | `character varying(100)` | NO | — | — | Action recorded on the event. *[D]* |
| `old_value` | `text` | YES | — | — | Value before the change. *[D]* |
| `new_value` | `text` | YES | — | — | Value after the change. *[D]* |
| `occurred_at` | `timestamp without time zone` | NO | — | `now()` | Date and time of the change. *[D]* |

### 2.4 `event_media`

**Description:** Images attached to an event. *[D]*

**Created in changeset:** `042-create-event-media.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `media_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `img_url` | `character varying(255)` | NO | — | — | Image URL in object storage. *[D]* |

### 2.5 `event_media_log`

**Description:** Version history of an event's images. *[D]*

**Created in changeset:** `043-create-event-media-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `media_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `media_id` | `bigint` | NO | FK → `event_media.media_id` | — | Reference to `event_media.media_id`. *[R3]* |
| `img_url` | `character varying(255)` | NO | — | — | Image URL in that version. *[D]* |
| `version` | `integer` | NO | — | — | Consecutive version number of the image. *[D]* |
| `is_visible` | `boolean` | NO | — | `true` | Whether that image version is visible. *[D]* |

### 2.6 `event_rating`

**Description:** User ratings (1–5) and comments on an event. *[D]*

**Created in changeset:** `044-create-event-rating.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `rating_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `rating` | `integer` | YES | — | — | Numeric rating from 1 to 5; null when the record is a comment only. *[D]* CHECK constraint: `CHECK (((rating IS NULL) OR ((rating >= 1) AND (rating <= 5))))`. |
| `comment` | `character varying()` | NO | — | — | Comment text (maximum 500 characters according to application validation). *[D]* |
| `is_visible` | `boolean` | NO | — | `true` | Whether the comment or rating is shown publicly. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was created (audit). *[R2]* |
| `parent_rating_id` | `bigint` | YES | FK → `event_rating.rating_id` | — | Comment being replied to; null for a top-level comment (cascade delete). |
| `edited_at` | `timestamp without time zone` | YES | — | — | Date and time of the last comment edit. |
| `reply_to_user_id` | `bigint` | YES | — | — | ID of the user being replied to directly (for mentions). |
| `reply_to_user_name` | `character varying(100)` | YES | — | — | Name of the user being replied to (to display @Name). |

### 2.7 `event_status_log`

**Description:** History of an event's status changes. *[D]*

**Created in changeset:** `040-create-event-status-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `status_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `old_status` | `character varying(20)` | YES | — | — | Previous event status. *[D]* |
| `new_status` | `character varying(20)` | NO | — | — | New event status. *[D]* |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | Date and time of the status change. *[D]* |
| `changed_by` | `bigint` | YES | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `reason` | `text` | YES | — | — | Administrator rejection reason when the new status is REJECTED; null otherwise. |

<a id="mod-geolocation"></a>

## 3. Module `geolocation`

### 3.1 `city`

**Description:** Cities (municipalities) loaded from `db/data/cities.csv`. *[D]*

**Created in changeset:** `026-create-city-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `city_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `department_id` | `integer` | NO | FK → `department.department_id` | — | Reference to `department.department_id`. *[R3]* |
| `name` | `character varying(100)` | NO | — | — | City name. *[D]* |
| `code` | `character varying(10)` | NO | UQ | — | Unique city code (DANE municipality code). *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 3.2 `department`

**Description:** Colombian departments loaded from `db/data/departments.csv`. *[D]*

**Created in changeset:** `025-create-department-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `department_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(100)` | NO | — | — | Department name. *[D]* |
| `code` | `character varying(10)` | NO | UQ | — | Unique department code (DANE code). *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 3.3 `site`

**Description:** Sites or venues where events take place, with capacity and coordinates. *[D]*

**Created in changeset:** `027-create-site-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `site_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `city_id` | `integer` | NO | FK → `city.city_id` | — | Reference to `city.city_id`. *[R3]* |
| `name` | `character varying(150)` | NO | — | — | Site name. *[D]* |
| `address` | `character varying(200)` | NO | — | — | Site address. *[D]* |
| `capacity` | `integer` | NO | — | — | Maximum people capacity of the site. *[D]* |
| `latitude` | `numeric(9,6)` | NO | — | — | Site latitude (−90 to 90). *[D]* |
| `longitude` | `numeric(9,6)` | NO | — | — | Site longitude (−180 to 180). *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

<a id="mod-language"></a>

## 4. Module `language`

### 4.1 `action_translation`

**Description:** Translations of system action names per language. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `action` | `character varying(100)` | NO | UQ | — | Code of the translated action. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_description` | `character varying(255)` | NO | — | — | Translated action description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.2 `category_translation`

**Description:** Translations of each category's name and description per language. *[D]*

**Created in changeset:** `088-create-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | Reference to `category.category_id`. *[R3]* |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated category name. *[D]* |
| `translated_description` | `character varying(255)` | YES | — | — | Translated category description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | Allowed values: `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. *[R4]* |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that last modified the record (audit). *[R2]* |

### 4.3 `channel_translation`

**Description:** Translations of notification channels per language. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `channel_id` | `integer` | NO | UQ | — | Translated channel; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | YES | — | — | Translated channel name. *[D]* |
| `translated_description` | `character varying(255)` | NO | — | — | Translated channel description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.4 `event_comment_reply_translation`

**Description:** Translations of replies to event comments. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `reply_id` | `integer` | NO | UQ | — | Translated reply; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_reply_text` | `character varying(255)` | YES | — | — | Translated reply text. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.5 `event_rating_translation`

**Description:** Translations of event rating comments. *[D]*

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `rating_id` | `integer` | NO | UQ | — | Translated rating; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_comment` | `character varying(255)` | YES | — | — | Translated comment. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.6 `event_translation`

**Description:** Translations of each event's name and description per language. *[D]*

**Created in changeset:** `088-create-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | UQ, FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | YES | — | — | Translated event name. *[D]* |
| `translated_description` | `character varying(255)` | YES | — | — | Translated event description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | Allowed values: `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. *[R4]* |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that last modified the record (audit). *[R2]* |

### 4.7 `language`

**Description:** Languages available on the platform. *[D]*

**Created in changeset:** `084-create-language-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `language_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `code` | `character varying(10)` | NO | UQ | — | Unique language code (for example, `es`, `en`). *[D]* |
| `name` | `character varying(50)` | NO | — | — | Language name. *[D]* |
| `is_active` | `boolean` | NO | — | `true` | Whether the language is active; the public only sees active ones. *[D]* |
| `is_default` | `boolean` | NO | — | `false` | Whether it is the default language; it cannot be deactivated. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | NO | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | NO | — | — | User or process that last modified the record (audit). *[R2]* |

### 4.8 `module_translation`

**Description:** Translations of system module names. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `module` | `character varying(50)` | NO | UQ | — | Code of the translated module. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated module name. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.9 `notification_translation`

**Description:** Notification translations (Javadoc of `NotificationTranslation`).

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `notification_id` | `integer` | NO | UQ | — | Translated notification; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_subject` | `text` | YES | — | — | Translated subject. *[D]* |
| `translated_body` | `text` | YES | — | — | Translated body. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.10 `notification_type_translation`

**Description:** Translations of notification types. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `notification_type_id` | `integer` | NO | UQ | — | Translated notification type; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated type name. *[D]* |
| `translated_description` | `character varying(255)` | NO | — | — | Translated type description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.11 `profile_translation`

**Description:** Translations of profile bios. *[D]*

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `profile_id` | `integer` | NO | UQ | — | Translated profile; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | UQ, FK → `language.language_id` | — | Reference to `language.language_id`. *[R3]* |
| `translated_bio` | `character varying(255)` | NO | — | — | Translated bio. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.12 `review_translation`

**Description:** Translations of reviews. *[D]*

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `review_id` | `integer` | NO | UQ | — | Translated review; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_comment` | `character varying(255)` | NO | — | — | Translated review comment. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.13 `seat_block_translation`

**Description:** Translations of seat block names. *[D]*

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `seat_block_id` | `integer` | NO | UQ | — | Translated seat block; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated block name. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.14 `section_type_translation`

**Description:** Translations of section types. *[D]*

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `section_type_id` | `integer` | NO | UQ | — | Translated section type; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated section type name. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.15 `theme_translation`

**Description:** Translations of visual theme names and descriptions. *[D]*

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `theme_id` | `integer` | NO | UQ | — | Translated theme; unique together with the language. *[D]* |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | Reference to `language.language_id`. *[R3]* |
| `translated_name` | `character varying(100)` | NO | — | — | Translated theme name. *[D]* |
| `translated_description` | `character varying(255)` | NO | — | — | Translated theme description. *[D]* |
| `source` | `character varying(50)` | NO | — | — | Translation origin: `MANUAL` (human) or `MACHINE` (automatic), according to `TranslationSource`. *[D]* |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | Translation status (`DRAFT`, `PUBLISHED` or `PENDING_REVIEW` in `TranslationStatus`); only published ones are shown. *[D]* |

### 4.16 `translation_job`

**Description:** Asynchronous machine translation jobs (LibreTranslate) per entity, with retries. *[D]*

**Created in changeset:** `087-translation-job-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `job_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `entity_type` | `character varying(50)` | NO | UQ | — | Type of entity being translated (for example, `event`, `category`, `profile`). *[D]* |
| `entity_id` | `bigint` | NO | UQ | — | Identifier of the entity being translated. *[D]* |
| `source_language_id` | `bigint` | NO | FK → `language.language_id` | — | Reference to `language.language_id`. *[R3]* |
| `target_language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | Reference to `language.language_id`. *[R3]* |
| `source_hash` | `character varying(64)` | NO | — | — | Hash of the source texts; detects whether they changed and need re-translation. *[D]* |
| `status` | `character varying(20)` | NO | — | — | Allowed values: `PENDING`, `PROCESSING`, `COMPLETED`, `FAILED`. *[R4]* |
| `provider` | `character varying(20)` | NO | — | — | Translation provider used. *[D]* |
| `attempts` | `integer` | NO | — | `0` | Number of attempts made. *[D]* |
| `last_error` | `character varying(1000)` | YES | — | — | Last provider error. *[D]* |
| `next_retry_at` | `timestamp without time zone` | YES | — | — | Date and time of the next retry. *[D]* |
| `completed_at` | `timestamp without time zone` | YES | — | — | Date and time the job finished. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | User or process that last modified the record (audit). *[R2]* |

<a id="mod-notification"></a>

## 5. Module `notification`

### 5.1 `channel`

**Description:** Notification delivery channels (for example, email or in-app). *[D]*

**Created in changeset:** `079-create-channel-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `channel_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(50)` | NO | UQ | — | Unique channel name. *[D]* |
| `description` | `character varying(100)` | NO | — | — | Channel description. *[D]* |
| `active` | `boolean` | NO | — | `true` | Whether the channel is active. *[D]* |
| `config` | `jsonb` | YES | — | — | Channel configuration in JSON. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 5.2 `notification`

**Description:** Notifications generated by business events. *[D]*

**Created in changeset:** `081-create-notification-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `channel_id` | `bigint` | NO | FK → `channel.channel_id` | — | Reference to `channel.channel_id`. *[R3]* |
| `notification_type_id` | `bigint` | NO | FK → `notification_type.notification_type_id` | — | Reference to `notification_type.notification_type_id`. *[R3]* |
| `entity_type` | `character varying(30)` | NO | — | — | Type of business entity that triggered the notification. *[D]* |
| `entity_id` | `bigint` | NO | — | — | Identifier of the entity that triggered the notification. *[D]* |
| `subject` | `character varying(150)` | NO | — | — | Notification subject. *[D]* |
| `body` | `text` | NO | — | — | Notification body. *[D]* |
| `sent_at` | `timestamp without time zone` | YES | — | — | Date and time sent. *[D]* |
| `idempotency_key` | `character varying(150)` | NO | UQ | — | Unique key that prevents creating the same notification twice. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 5.3 `notification_type`

**Description:** Catalog of notification types. *[D]*

**Created in changeset:** `080-create-notification-type-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_type_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(50)` | NO | UQ | — | Unique notification type name. *[D]* |
| `description` | `character varying(100)` | NO | — | — | Notification type description. *[D]* |
| `active` | `boolean` | NO | — | `true` | Whether the type is active. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 5.4 `notification_user`

**Description:** Delivery of a notification to a user through a channel, with its sending and read status. *[D]*

**Created in changeset:** `082-create-notification-user-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_user_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `notification_id` | `bigint` | NO | UQ, FK → `notification.notification_id` | — | Reference to `notification.notification_id`. *[R3]* |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `email_address` | `character varying(255)` | YES | — | — | Destination email used for sending. *[D]* |
| `delivered_status` | `character varying(20)` | NO | — | — | Allowed values: `PENDING`, `SENT`, `DELIVERED`, `FAILED`. *[R4]* |
| `error_message` | `text` | YES | — | — | Error message if sending failed. *[D]* |
| `read_at` | `timestamp without time zone` | YES | — | — | Date and time the user marked it as read; null if unread. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

<a id="mod-payment"></a>

## 6. Module `payment`

### 6.1 `payment`

**Description:** Order payments, through the gateway, the wallet or both. *[D]*

**Created in changeset:** `069-create-payment-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `payment_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | Reference to `order.order_id`. *[R3]* |
| `gateway` | `character varying(20)` | NO | — | — | Allowed values: `FAKE`, `WOMPI`. *[R4]* |
| `gateway_transaction_id` | `character varying(100)` | NO | UQ | — | Unique transaction identifier in the gateway; wallet-only payments use the `wallet_only_` prefix. *[D]* |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | Allowed values: `PENDING`, `APPROVED`, `REJECTED`, `ERROR`, `REFUNDED`. *[R4]* |
| `amount` | `numeric(19,4)` | NO | — | — | Amount charged through the gateway (0 if fully paid with the wallet). *[D]* |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | ISO 4217 currency code. *[D]* |
| `payment_method` | `character varying(20)` | YES | — | — | Allowed values: `CARD`, `PSE`, `NEQUI`, `CASH`, `QR`. *[R4]* |
| `processed_at` | `timestamp without time zone` | YES | — | — | Date and time the payment was processed. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |
| `wallet_amount_applied` | `numeric(19,4)` | NO | — | `0` | Part of the total covered with wallet balance. *[D]* CHECK constraint: `CHECK ((wallet_amount_applied >= (0)::numeric))`. |
| `wallet_transaction_id` | `bigint` | YES | FK → `wallet_transaction.transaction_id` | — | Reference to `wallet_transaction.transaction_id`. *[R3]* |

### 6.2 `payment_log`

**Description:** Audit of payment status changes (Javadoc of `PaymentLogEntity`).

**Created in changeset:** `070-create-payment-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `payment_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | Reference to `payment.payment_id`. *[R3]* |
| `old_status` | `character varying(20)` | NO | — | — | Previous payment status. *[D]* |
| `new_status` | `character varying(20)` | NO | — | — | New payment status. *[D]* |
| `changed_at` | `timestamp without time zone` | NO | — | — | Date and time of the change. *[D]* |
| `reason` | `character varying(500)` | YES | — | — | Reason for the status change. *[D]* |

### 6.3 `refund`

**Description:** Refunds requested on approved payments. *[D]*

**Created in changeset:** `072-create-refund-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `refund_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | Reference to `payment.payment_id`. *[R3]* |
| `status` | `character varying(20)` | NO | — | `'REQUESTED'::character varying` | Allowed values: `REQUESTED`, `APPROVED`, `PROCESSED`, `FAILED`. *[R4]* |
| `reason` | `character varying(500)` | YES | — | — | Refund reason (required, maximum 500 characters). *[D]* |
| `requested_at` | `timestamp without time zone` | NO | — | — | Date and time requested. *[D]* |
| `processed_at` | `timestamp without time zone` | YES | — | — | Date and time processed. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 6.4 `transaction_webhook`

**Description:** Audit of received webhooks (Javadoc of `TransactionWebhookEntity`).

**Created in changeset:** `071-create-transaction-webhook-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `webhook_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | Reference to `payment.payment_id`. *[R3]* |
| `gateway_event_id` | `character varying(100)` | NO | UQ | — | Unique gateway event identifier; ensures a repeated webhook is not processed twice. *[D]* |
| `payload` | `text` | NO | — | — | Received webhook body. *[D]* |
| `received_at` | `timestamp without time zone` | NO | — | — | Date and time received. *[D]* |

<a id="mod-profile"></a>

## 7. Module `profile`

### 7.1 `profile`

**Description:** User's public profile (name, bio and avatar). *[D]*

**Created in changeset:** `032-create-profile-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `profile_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id`, UQ | — | Reference to `app_user.user_id`. *[R3]* |
| `city_id` | `integer` | YES | FK → `city.city_id` | — | Reference to `city.city_id`. *[R3]* |
| `stored_file_id` | `integer` | YES | FK → `stored_file.stored_file_id` | — | Profile picture file (integer, no JPA relation to the storage module). |
| `full_name` | `character varying(30)` | NO | — | — | User's full name (maximum 30 characters). *[D]* |
| `bio` | `character varying(255)` | YES | — | — | User bio (maximum 255 characters; inappropriate language is filtered). *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |
| `name_changed_at` | `timestamp without time zone` | YES | — | — | Date of the last name change; 14 days are required between changes (`UpdateProfileUseCase`). *[D]* |
| `preferred_language_id` | `bigint` | YES | FK → `language.language_id` | — | User's preferred language for displaying content. |

### 7.2 `profile_log`

**Description:** Profile change log. *[D]*

**Created in changeset:** `033-create-profile-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `profile_id` | `bigint` | NO | FK → `profile.profile_id` | — | Reference to `profile.profile_id`. *[R3]* |
| `action` | `character varying(50)` | YES | — | — | Recorded action (for example, `FULL_NAME_CHANGED`). *[D]* |
| `old_value` | `character varying(255)` | YES | — | — | Previous value. *[D]* |
| `new_value` | `character varying(255)` | YES | — | — | New value. *[D]* |
| `occurred_at` | `timestamp without time zone` | YES | — | — | Date and time of the change. *[D]* |

<a id="mod-seat"></a>

## 8. Module `seat`

### 8.1 `seat`

**Description:** Seats of an event section, with their status and temporary hold. *[D]*

**Created in changeset:** `056-create-seat.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `seat_block_id` | `integer` | NO | FK → `seat_block.seat_block_id` | — | Reference to `seat_block.seat_block_id`. *[R3]* |
| `event_section_id` | `integer` | NO | UQ, FK → `event_section.event_section_id` | — | Reference to `event_section.event_section_id`. *[R3]* |
| `code` | `character varying(20)` | NO | UQ | — | Seat code, unique within the section. *[D]* |
| `row` | `integer` | NO | — | — | Seat row in the plan. *[D]* |
| `position` | `integer` | NO | — | — | Seat position within the row. *[D]* |
| `type` | `character varying(20)` | NO | — | — | Allowed values: `REGULAR`, `COURTESY`. *[R4]* |
| `status` | `character varying(20)` | NO | — | `'available'::character varying` | Allowed values: `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. *[R4]* |
| `reserved_by` | `integer` | YES | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `reserved_until` | `timestamp without time zone` | YES | — | — | Date and time the temporary hold expires (10 minutes). *[D]* |

### 8.2 `seat_block`

**Description:** Blocks grouping seats inside a section. *[D]*

**Created in changeset:** `055-create-seat-block.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_block_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_section_id` | `integer` | NO | FK → `event_section.event_section_id` | — | Reference to `event_section.event_section_id`. *[R3]* |
| `name` | `character varying(100)` | NO | — | — | Block name. *[D]* |
| `capacity` | `integer` | NO | — | — | Seat capacity of the block. *[D]* CHECK constraint: `CHECK ((capacity > 0))`. |

### 8.3 `seat_log`

**Description:** History of seat status changes. *[D]*

**Created in changeset:** `057-create-seat-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `seat_id` | `integer` | NO | FK → `seat.seat_id` | — | Reference to `seat.seat_id`. *[R3]* |
| `old_status` | `character varying(20)` | YES | — | — | Allowed values: `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. *[R4]* |
| `new_status` | `character varying(20)` | NO | — | — | Allowed values: `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. *[R4]* |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | Date and time of the change. *[D]* |
| `changed_by` | `integer` | YES | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `reason` | `character varying(255)` | YES | — | — | Reason for the status change. *[D]* |

<a id="mod-section"></a>

## 9. Module `section`

### 9.1 `event_section`

**Description:** Sections of an event, with capacity, available seats and price. *[D]*

**Created in changeset:** `053-create-event-section.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_section_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `integer` | NO | FK → `event.event_id`, UQ | — | Reference to `event.event_id`. *[R3]* |
| `section_type_id` | `integer` | NO | UQ, FK → `section_type.section_type_id` | — | Reference to `section_type.section_type_id`. *[R3]* |
| `capacity` | `integer` | NO | — | — | Total section capacity. *[D]* CHECK constraint: `CHECK ((capacity > 0))`. CHECK constraint: `CHECK ((available_seats <= capacity))`. |
| `available_seats` | `integer` | NO | — | — | Seats still available in the section. *[D]* CHECK constraint: `CHECK ((available_seats <= capacity))`. |
| `price` | `numeric(10,2)` | NO | — | — | Price per seat in the section. *[D]* CHECK constraint: `CHECK ((price >= (0)::numeric))`. |
| `is_active` | `boolean` | NO | — | `true` | Whether the section is active. *[D]* |

### 9.2 `section_type`

**Description:** Catalog of section types. *[D]*

**Created in changeset:** `052-create-section-type.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `section_type_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(100)` | NO | — | — | Section type name. *[D]* |
| `active` | `boolean` | NO | — | `true` | Whether the type is active. *[D]* |

<a id="mod-sectiontype"></a>

## 10. Module `sectiontype`

The `sectiontype` module has no tables of its own: the section type is stored in `section_type` (`section` module) and its translations in `section_type_translation` (`language` module).

<a id="mod-security"></a>

## 11. Module `security`

### 11.1 `account_activation`

**Description:** Account activation codes sent by email. *[D]*

**Created in changeset:** `007-create-account-activation-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `account_activation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `activation_code` | `character varying(8)` | NO | — | — | Activation code sent by email. *[D]* |
| `expires_at` | `timestamp without time zone` | NO | — | — | Code expiration date and time. *[D]* |
| `activated` | `boolean` | NO | — | `false` | Whether the code was already used to activate the account. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |

### 11.2 `account_lockout`

**Description:** Tracking of failed login attempts and temporary lockout. *[D]*

**Created in changeset:** `008-create-account-lockout-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `account_lockout_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `failed_attempts` | `integer` | NO | — | `0` | Failed attempts within the current window. *[D]* |
| `window_started_at` | `timestamp without time zone` | YES | — | — | Start of the failed-attempt counting window. *[D]* |
| `locked_until` | `timestamp without time zone` | YES | — | — | Date and time until which the account is locked. *[D]* |

### 11.3 `account_reactivation_token`

**Description:** Codes to reactivate deactivated accounts. *[D]*

**Created in changeset:** `060-create-account-reactivation-token-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `reactivation_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `token` | `character varying(8)` | NO | — | — | Reactivation code sent by email. *[D]* |
| `token_status` | `boolean` | NO | — | `false` | `true` when the code was used or invalidated; `false` while still valid. *[D]* |
| `expires_at` | `timestamp without time zone` | NO | — | — | Code expiration date and time. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |

### 11.4 `app_user`

**Description:** Platform users, with role and status. *[D]*

**Created in changeset:** `004-create-user-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | Reference to `user_status.user_status_id`. *[R3]* |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | Reference to `role.role_id`. *[R3]* |
| `alias` | `character varying(50)` | NO | UQ | — | Unique user alias. *[D]* |
| `activated` | `boolean` | NO | — | `false` | Whether the user activated their account. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 11.5 `auth_session`

**Description:** Authenticated sessions (issued access token, IP and browser). *[D]*

**Created in changeset:** `009-create-auth-session-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `auth_session_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `access_token` | `character varying(512)` | NO | — | — | Access token (JWT) issued in the session. *[D]* |
| `issued_at` | `timestamp without time zone` | NO | — | — | Issue date and time. *[D]* |
| `expires_at` | `timestamp without time zone` | NO | — | — | Expiration date and time. *[D]* |
| `ip_address` | `character varying(45)` | YES | — | — | Client IP address (IPv4 or IPv6). *[D]* |
| `user_agent` | `character varying(200)` | YES | — | — | Client user agent (browser or app). *[D]* |
| `revoked` | `boolean` | NO | — | `false` | Whether the session was revoked (for example, on logout). *[D]* |
| `revoked_at` | `timestamp without time zone` | YES | — | — | Revocation date and time. *[D]* |

### 11.6 `login_credentials`

**Description:** Email and password login credentials. *[D]*

**Created in changeset:** `006-create-login-credentials-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `login_credentials_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `password_hash` | `character varying(255)` | NO | — | — | BCrypt hash (cost 12) of the password. *[D]* |
| `email` | `character varying(255)` | NO | UQ | — | Unique login email. *[D]* |
| `last_login_at` | `timestamp without time zone` | YES | — | — | Date and time of the last login. *[D]* |

### 11.7 `oauth_account`

**Description:** OAuth provider accounts (Google, Facebook) linked to a user. *[D]*

**Created in changeset:** `013-create-oauth-account-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `oauth_account_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `provider` | `character varying(30)` | NO | UQ | — | OAuth provider (for example, `google`). *[D]* |
| `provider_user_id` | `character varying(100)` | NO | UQ | — | User identifier at the provider. *[D]* |
| `email` | `character varying(255)` | YES | — | — | Email reported by the provider. *[D]* |
| `linked_at` | `timestamp without time zone` | YES | — | — | Date and time linked. *[D]* |

### 11.8 `organizer_petition`

**Description:** User requests to obtain the organizer role. *[D]*

**Created in changeset:** `015-create-organizer-petition-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `organizer_petition_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `application_date` | `timestamp without time zone` | NO | — | — | Date and time of the request. *[D]* |
| `status` | `character varying(20)` | NO | — | — | Request status (pending, approved or rejected). *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |
| `stored_file_id` | `integer` | YES | FK → `stored_file.stored_file_id` | — | Reference to `stored_file.stored_file_id`. *[R3]* |
| `document_type` | `character varying(50)` | YES | — | — | Type of the document attached to the request. *[D]* |

### 11.9 `password_history`

**Description:** Password history to prevent reusing recent passwords. *[D]*

**Created in changeset:** `012-create-password-history-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `password_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `password_hash` | `character varying(255)` | NO | — | — | Hash of a previously used password. *[D]* |
| `changed_at` | `timestamp without time zone` | NO | — | — | Date and time of the change. *[D]* |

### 11.10 `permission`

**Description:** Catalog of permissions. *[D]*

**Created in changeset:** `003-create-permission-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `code` | `character varying(50)` | NO | UQ | — | Unique permission code. *[D]* |
| `name` | `character varying(80)` | NO | — | — | Permission name. *[D]* |
| `description` | `character varying(150)` | NO | — | — | Permission description. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 11.11 `recover_password`

**Description:** Password recovery codes sent by email. *[D]*

**Created in changeset:** `011-create-recover-password-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `recover_password_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `code` | `character varying(8)` | NO | — | — | Recovery code sent by email. *[D]* |
| `code_status` | `boolean` | NO | — | `false` | `true` when the code was used or invalidated; `false` while still valid. *[D]* |
| `expires_at` | `timestamp without time zone` | NO | — | — | Code expiration date and time. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `last_password_hash` | `character varying(255)` | YES | — | — | Hash of the password before the reset (mapped by the entity, but no use was found in the use cases). *[D]* |

### 11.12 `refresh_token`

**Description:** Refresh tokens issued to users. *[D]*

**Created in changeset:** `010-create-refresh-token-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `refresh_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `auth_session_id` | `integer` | NO | FK → `auth_session.auth_session_id` | — | Reference to `auth_session.auth_session_id`. *[R3]* |
| `token` | `character varying(512)` | NO | — | — | Issued refresh token. *[D]* |
| `issued_at` | `timestamp without time zone` | NO | — | — | Issue date and time. *[D]* |
| `expires_at` | `timestamp without time zone` | NO | — | — | Expiration date and time (7 days). *[D]* |
| `revoked` | `boolean` | NO | — | `false` | Whether the token was revoked (logout or rotation). *[D]* |
| `revoked_at` | `timestamp without time zone` | YES | — | — | Revocation date and time. *[D]* |

### 11.13 `role`

**Description:** Catalog of roles (USER, ORGANIZER, ADMIN). *[D]*

**Created in changeset:** `002-create-role-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `role_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `code` | `character varying(50)` | NO | UQ | — | Unique role code. *[D]* |
| `name` | `character varying(80)` | NO | — | — | Role name. *[D]* |
| `description` | `character varying(150)` | NO | — | — | Role description. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 11.14 `role_permission`

**Description:** Relation between roles and permissions. *[D]*

**Created in changeset:** `005-create-role-permission-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `role_permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | Reference to `role.role_id`. *[R3]* |
| `permission_id` | `integer` | NO | FK → `permission.permission_id` | — | Reference to `permission.permission_id`. *[R3]* |

### 11.15 `user_status`

**Description:** Catalog of user account statuses. *[D]*

**Created in changeset:** `001-create-user-status-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_status_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `code` | `character varying(30)` | NO | UQ | — | Unique account status code. *[D]* |
| `name` | `character varying(80)` | NO | — | — | Status name. *[D]* |
| `description` | `character varying(150)` | NO | — | — | Status description. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 11.16 `user_status_history`

**Description:** History of account status changes. *[D]*

**Created in changeset:** `014-create-user-status-history-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_status_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | Reference to `user_status.user_status_id`. *[R3]* |
| `reason` | `character varying(150)` | NO | — | — | Reason for the status change. *[D]* |

<a id="mod-storage"></a>

## 12. Module `storage`

### 12.1 `file_category`

**Description:** File categories with their allowed extensions and maximum size. *[D]*

**Created in changeset:** `019-create-file-category-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `file_category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `storage_provider_id` | `integer` | NO | FK → `storage_provider.storage_provider_id` | — | Reference to `storage_provider.storage_provider_id`. *[R3]* |
| `name` | `character varying(100)` | NO | — | — | File category name. *[D]* |
| `code` | `character varying(50)` | NO | UQ | — | Unique file category code. *[D]* |
| `is_public` | `boolean` | NO | — | `false` | Whether files in the category are publicly accessible. *[D]* |
| `allowed_extensions` | `character varying(100)` | NO | — | — | File extensions allowed in the category. *[D]* |
| `max_size_mb` | `integer` | NO | — | — | Maximum size per file, in MB. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 12.2 `storage_operation_log`

**Description:** Immutable log of storage operations: rows are only appended, never updated (Javadoc of `StorageOperationLogEntity`).

**Created in changeset:** `021-create-storage-operation-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `stored_file_id` | `integer` | NO | FK → `stored_file.stored_file_id` | — | Reference to `stored_file.stored_file_id`. *[R3]* |
| `performed_by` | `integer` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `operation` | `character varying(20)` | NO | — | — | Operation performed on storage (for example, upload or delete). *[D]* |
| `status` | `character varying(20)` | NO | — | — | Operation result. *[D]* |
| `error_message` | `character varying(500)` | YES | — | — | Error message if the operation failed. *[D]* |
| `occurred_at` | `timestamp without time zone` | NO | — | — | Date and time of the operation. *[D]* |

### 12.3 `storage_provider`

**Description:** Configured object storage providers (MinIO, RustFS, etc.). *[D]*

**Created in changeset:** `018-create-storage-provider-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `storage_provider_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(100)` | NO | — | — | Storage provider name. *[D]* |
| `code` | `character varying(20)` | NO | UQ | — | Unique provider code. *[D]* |
| `is_active` | `boolean` | NO | — | `false` | Whether it is the active provider. *[D]* |
| `config` | `jsonb` | NO | — | — | Provider configuration in JSON. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 12.4 `stored_file`

**Description:** Metadata of files uploaded to object storage. *[D]*

**Created in changeset:** `020-create-stored-file-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `stored_file_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `file_category_id` | `integer` | NO | FK → `file_category.file_category_id` | — | Reference to `file_category.file_category_id`. *[R3]* |
| `uploaded_by` | `integer` | NO | FK → `app_user.user_id` | — | ID of the user who uploaded the file. |
| `s3_key` | `character varying(512)` | NO | — | — | Object key in the bucket (S3-compatible API). *[D]* |
| `original_filename` | `character varying(255)` | NO | — | — | Original name of the uploaded file. *[D]* |
| `content_type` | `character varying(100)` | NO | — | — | File MIME type. *[D]* |
| `size_bytes` | `bigint` | NO | — | — | File size in bytes. *[D]* |
| `public_url` | `character varying(512)` | YES | — | — | Public file URL, if the category is public. *[D]* |
| `owner_entity_id` | `integer` | YES | — | — | Identifier of the entity owning the file. *[D]* |
| `owner_entity_type` | `character varying(50)` | YES | — | — | Type of the owning entity (for example, `EVENT`). *[D]* |
| `deleted` | `boolean` | NO | — | `false` | Logical (soft) deletion flag. *[D]* |
| `uploaded_at` | `timestamp without time zone` | NO | — | — | Upload date and time. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(50)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(50)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

<a id="mod-theme"></a>

## 13. Module `theme`

### 13.1 `theme`

**Description:** Visual themes of the interface. *[D]*

**Created in changeset:** `034-create-theme-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `theme_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `name` | `character varying(100)` | NO | UQ | — | Unique theme name. *[D]* |
| `description` | `character varying(255)` | NO | — | — | Theme description. *[D]* |
| `default_palette` | `jsonb` | NO | — | — | Theme's default color palette in JSON. *[D]* |

### 13.2 `theme_customization`

**Description:** Theme property customizations made by a user. *[D]*

**Created in changeset:** `036-create-theme-customization-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `customization_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_theme_id` | `bigint` | NO | UQ, FK → `user_theme.user_theme_id` | — | Customized user theme. |
| `property` | `character varying(100)` | NO | UQ | — | Customized theme property (unique per user and theme). *[D]* |
| `value` | `character varying(255)` | NO | — | — | Customized property value. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |

### 13.3 `theme_log`

**Description:** Theme audit log: rows are only appended, never updated (Javadoc of `ThemeLogEntity`).

**Created in changeset:** `037-create-theme-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_theme_id` | `bigint` | NO | FK → `user_theme.user_theme_id` | — | Reference to `user_theme.user_theme_id`. *[R3]* |
| `action` | `character varying(50)` | NO | — | — | Action recorded on the theme. *[D]* |
| `property` | `character varying(100)` | YES | — | — | Affected property. *[D]* |
| `old_value` | `character varying(255)` | YES | — | — | Previous value. *[D]* |
| `new_value` | `character varying(255)` | YES | — | — | New value. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |

### 13.4 `user_theme`

**Description:** Themes activated by each user. *[D]*

**Created in changeset:** `035-create-user-theme-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_theme_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | User the theme belongs to. |
| `theme_id` | `integer` | NO | UQ, FK → `theme.theme_id` | — | Selected theme. |
| `is_active` | `boolean` | NO | — | `true` | Whether it is the user's active theme. *[D]* |
| `created_at` | `timestamp without time zone` | YES | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | YES | — | — | Date and time the record was last modified (audit). *[R2]* |

<a id="mod-ticket"></a>

## 14. Module `ticket`

### 14.1 `order`

**Description:** Ticket purchase orders. *[D]*

**Created in changeset:** `064-create-order-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `order_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `total_amount` | `numeric(19,4)` | NO | — | — | Order total (sum of the section prices of the seats). *[D]* |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | ISO 4217 currency code. *[D]* |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | Allowed values: `DRAFT`, `PAYMENT_PENDING`, `PAID`, `CANCELLED`, `REFUNDED`, `USED`. *[R4]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 14.2 `seat_ticket`

**Description:** N:M relationship between seat and ticket, with the price captured at purchase time (Javadoc of `SeatTicketEntity`).

**Created in changeset:** `066-create-seat-ticket-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `seat_id` | `integer` | NO | UQ, FK → `seat.seat_id` | — | Reference to `seat.seat_id`. *[R3]* |
| `ticket_id` | `bigint` | NO | UQ, FK → `ticket.ticket_id` | — | Reference to `ticket.ticket_id`. *[R3]* |
| `price` | `numeric(19,4)` | NO | — | — | Seat price at purchase time. *[D]* |

### 14.3 `ticket`

**Description:** Tickets issued for an order, with code and QR. *[D]*

**Created in changeset:** `065-create-ticket-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | Reference to `event.event_id`. *[R3]* |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | Reference to `order.order_id`. *[R3]* |
| `code` | `character varying(50)` | NO | UQ | — | Unique ticket code. *[D]* |
| `qr_code` | `character varying(500)` | NO | — | — | Ticket QR code content. *[D]* |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | Allowed values: `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. *[R4]* |
| `expiration_date` | `timestamp without time zone` | YES | — | — | Ticket expiration; currently computed as creation date plus 30 days (`CreateOrderWithTicketsUseCaseImpl`). *[D]* |
| `total_price` | `numeric(19,4)` | NO | — | — | Total ticket price. *[D]* |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | ISO 4217 currency code. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 14.4 `ticket_checkin`

**Description:** Ticket check-in records at the event. *[D]*

**Created in changeset:** `067-create-ticket-checkin-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `checkin_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id`, UQ | — | Reference to `ticket.ticket_id`. *[R3]* |
| `checkin_time` | `timestamp without time zone` | NO | — | — | Check-in date and time. *[D]* |
| `validated_by` | `bigint` | NO | FK → `app_user.user_id` | — | Reference to `app_user.user_id`. *[R3]* |

### 14.5 `ticket_log`

**Description:** Immutable ticket audit (Javadoc of `TicketLogEntity`).

**Created in changeset:** `068-create-ticket-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `ticket_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id` | — | Reference to `ticket.ticket_id`. *[R3]* |
| `old_status` | `character varying(20)` | YES | — | — | Allowed values: `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. *[R4]* |
| `new_status` | `character varying(20)` | NO | — | — | Allowed values: `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. *[R4]* |
| `changed_at` | `timestamp without time zone` | NO | — | — | Date and time of the change. *[D]* |
| `changed_by` | `character varying(100)` | YES | — | — | User or process that made the change. *[D]* |
| `reason` | `character varying(255)` | YES | — | — | Reason for the change. *[D]* |

<a id="mod-wallet"></a>

## 15. Module `wallet`

### 15.1 `wallet`

**Description:** Wallet. Uses optimistic locking (`@Version`): if two transactions modify the same wallet at once, the second one fails (Javadoc of `WalletEntity`).

**Created in changeset:** `074-create-wallet-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `wallet_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `user_id` | `bigint` | NO | UQ | — | User owning the wallet (one per user). *[D]* |
| `balance` | `numeric(19,4)` | NO | — | `0` | Available balance; never negative. *[D]* CHECK constraint: `CHECK ((balance >= (0)::numeric))`. |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | Allowed values: `COP`. *[R4]* |
| `version` | `bigint` | NO | — | `0` | Version for optimistic locking. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `updated_at` | `timestamp without time zone` | NO | — | — | Date and time the record was last modified (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
| `updated_by` | `character varying(100)` | YES | — | — | User or process that last modified the record (audit). *[R2]* |

### 15.2 `wallet_reference`

**Description:** Wallet movement reference. Immutable: it has no audit or version columns (Javadoc of `WalletReferenceEntity`).

**Created in changeset:** `076-create-wallet-reference-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `wallet_reference_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `transaction_id` | `bigint` | NO | FK → `wallet_transaction.transaction_id` | — | Reference to `wallet_transaction.transaction_id`. *[R3]* |
| `entity_type` | `character varying(30)` | NO | — | — | Allowed values: `EVENT_CANCELLATION`, `ORDER`, `TICKET`, `ADMIN_ADJUSTMENT`. *[R4]* |
| `entity_id` | `bigint` | YES | — | — | Identifier of the business entity related to the transaction. *[D]* |

### 15.3 `wallet_transaction`

**Description:** Wallet transaction. Immutable: it only has `created_at` and `created_by` (Javadoc of `WalletTransactionEntity`).

**Created in changeset:** `075-create-wallet-transaction-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `transaction_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | Unique identifier of the table (PK, IDENTITY). *[R1]* |
| `wallet_id` | `bigint` | NO | FK → `wallet.wallet_id` | — | Reference to `wallet.wallet_id`. *[R3]* |
| `type` | `character varying(20)` | NO | — | — | Allowed values: `CREDIT`, `PAYMENT`, `REVERSAL`, `ADJUSTMENT`. *[R4]* |
| `amount` | `numeric(19,4)` | NO | — | — | Transaction amount (always positive). *[D]* CHECK constraint: `CHECK ((amount > (0)::numeric))`. |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | Allowed values: `PENDING`, `COMPLETED`, `FAILED`. *[R4]* |
| `balance_after` | `numeric(19,4)` | YES | — | — | Resulting balance after the transaction. *[D]* |
| `idempotency_key` | `character varying(100)` | NO | UQ | — | Unique key that prevents applying the same transaction twice. *[D]* |
| `created_at` | `timestamp without time zone` | NO | — | — | Date and time the record was created (audit). *[R2]* |
| `created_by` | `character varying(100)` | YES | — | — | User or process that created the record (audit). *[R2]* |
