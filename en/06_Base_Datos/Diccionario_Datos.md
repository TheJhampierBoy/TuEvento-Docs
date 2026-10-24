---
title: "Data dictionary"
lang: en
source: "06_Base_Datos/Script_BD_implementado.sql"
generated_from: "lozano2303/TuEvento origin/develop 2d259e7 (Liquibase 4.31.1, PostgreSQL 17.10)"
generated_on: 2026-10-24
status: borrador
reviewed_by: ""
translation_of: es/06_Base_Datos/Diccionario_Datos.md
es_sha256: a6d54774e148d7cdd0ac760e679834e0ed8d615dddd4b091a4c9f193a2453994
---
# Data dictionary — Tu Evento

> **Draft generated from the implemented schema.** This dictionary was generated on 2026-10-24 from [`Script_BD_implementado.sql`](Script_BD_implementado.sql): the 171 Liquibase 4.31.1 changesets of `lozano2303/TuEvento` (`origin/develop` / `2d259e7`) applied to a temporary PostgreSQL 17.10. Names, types, nullability, keys and default values come from the schema. Descriptions come from database comments and code comments (Javadoc); where there is none, it says **PENDING** for the team to complete. Each table's module comes from the JPA entity that maps it.
>
> Summary: 75 tables, 570 columns, 555 pending column descriptions.
>
> The previous version of this document (design dictionary converted from the XLSX `04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx`) is kept in the Git history: `git show 5e68501:en/06_Base_Datos/Diccionario_Datos.md`.

**Key column legend:** PK = primary key · FK → `table.column` = foreign key · UQ = part of a UNIQUE constraint.

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

**Description:** PENDING

**Created in changeset:** `047-create-category.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(50)` | NO | UQ | — | PENDING |
| `description` | `character varying(100)` | NO | — | — | PENDING |
| `active` | `boolean` | NO | — | `true` | PENDING |
| `visible` | `boolean` | NO | — | `true` | PENDING |
| `dad_id` | `integer` | YES | FK → `category.category_id` | — | Parent category; null for a root category. |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | NO | — | — | PENDING |
| `updated_by` | `character varying(100)` | NO | — | — | PENDING |

### 1.2 `category_event`

**Description:** PENDING

**Created in changeset:** `048-create-category-event.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `category_event_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | Category linked to the event. |
| `event_id` | `integer` | NO | UQ, FK → `event.event_id` | — | Event linked to the category. |

<a id="mod-event"></a>

## 2. Module `event`

### 2.1 `event`

**Description:** PENDING

**Created in changeset:** `039-create-event.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDING |
| `site_id` | `bigint` | NO | UQ, FK → `site.site_id` | — | PENDING |
| `event_name` | `character varying(100)` | NO | UQ | — | PENDING |
| `description` | `character varying(255)` | NO | — | — | PENDING |
| `start_date` | `date` | NO | UQ | — | PENDING CHECK constraint: `CHECK ((finish_date > start_date))`. |
| `finish_date` | `date` | NO | — | — | PENDING CHECK constraint: `CHECK ((finish_date > start_date))`. |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDING Allowed values (CHECK): `DRAFT`, `PENDING_REVIEW`, `PUBLISHED`, `REJECTED`, `CANCELLED`, `COMPLETED`. |
| `is_public` | `boolean` | NO | — | `true` | PENDING |
| `available_seats` | `integer` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |
| `rejection_reason` | `text` | YES | — | — | Rejection reason; filled when the status is REJECTED and cleared when it returns to DRAFT. |

### 2.2 `event_layout`

**Description:** PENDING

**Created in changeset:** `041-create-event-layout.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_layout_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `layout_data` | `jsonb` | NO | — | — | PENDING |

### 2.3 `event_log`

**Description:** PENDING

**Created in changeset:** `093-create-event-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `action` | `character varying(100)` | NO | — | — | PENDING |
| `old_value` | `text` | YES | — | — | PENDING |
| `new_value` | `text` | YES | — | — | PENDING |
| `occurred_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |

### 2.4 `event_media`

**Description:** PENDING

**Created in changeset:** `042-create-event-media.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `media_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `img_url` | `character varying(255)` | NO | — | — | PENDING |

### 2.5 `event_media_log`

**Description:** PENDING

**Created in changeset:** `043-create-event-media-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `media_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `media_id` | `bigint` | NO | FK → `event_media.media_id` | — | PENDING |
| `img_url` | `character varying(255)` | NO | — | — | PENDING |
| `version` | `integer` | NO | — | — | PENDING |
| `is_visible` | `boolean` | NO | — | `true` | PENDING |

### 2.6 `event_rating`

**Description:** PENDING

**Created in changeset:** `044-create-event-rating.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `rating_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDING |
| `rating` | `integer` | YES | — | — | PENDING CHECK constraint: `CHECK (((rating IS NULL) OR ((rating >= 1) AND (rating <= 5))))`. |
| `comment` | `character varying()` | NO | — | — | PENDING |
| `is_visible` | `boolean` | NO | — | `true` | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `parent_rating_id` | `bigint` | YES | FK → `event_rating.rating_id` | — | Comment being replied to; null for a top-level comment (cascade delete). |
| `edited_at` | `timestamp without time zone` | YES | — | — | Date and time of the last comment edit. |
| `reply_to_user_id` | `bigint` | YES | — | — | ID of the user being replied to directly (for mentions). |
| `reply_to_user_name` | `character varying(100)` | YES | — | — | Name of the user being replied to (to display @Name). |

### 2.7 `event_status_log`

**Description:** PENDING

**Created in changeset:** `040-create-event-status-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `status_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `old_status` | `character varying(20)` | YES | — | — | PENDING |
| `new_status` | `character varying(20)` | NO | — | — | PENDING |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `changed_by` | `bigint` | YES | FK → `app_user.user_id` | — | PENDING |
| `reason` | `text` | YES | — | — | Administrator rejection reason when the new status is REJECTED; null otherwise. |

<a id="mod-geolocation"></a>

## 3. Module `geolocation`

### 3.1 `city`

**Description:** PENDING

**Created in changeset:** `026-create-city-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `city_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `department_id` | `integer` | NO | FK → `department.department_id` | — | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `code` | `character varying(10)` | NO | UQ | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 3.2 `department`

**Description:** PENDING

**Created in changeset:** `025-create-department-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `department_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `code` | `character varying(10)` | NO | UQ | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 3.3 `site`

**Description:** PENDING

**Created in changeset:** `027-create-site-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `site_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `city_id` | `integer` | NO | FK → `city.city_id` | — | PENDING |
| `name` | `character varying(150)` | NO | — | — | PENDING |
| `address` | `character varying(200)` | NO | — | — | PENDING |
| `capacity` | `integer` | NO | — | — | PENDING |
| `latitude` | `numeric(9,6)` | NO | — | — | PENDING |
| `longitude` | `numeric(9,6)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

<a id="mod-language"></a>

## 4. Module `language`

### 4.1 `action_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `action` | `character varying(100)` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_description` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.2 `category_translation`

**Description:** PENDING

**Created in changeset:** `088-create-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | PENDING |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `translated_description` | `character varying(255)` | YES | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDING Allowed values (CHECK): `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |

### 4.3 `channel_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `channel_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | YES | — | — | PENDING |
| `translated_description` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.4 `event_comment_reply_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `reply_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_reply_text` | `character varying(255)` | YES | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.5 `event_rating_translation`

**Description:** PENDING

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `rating_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_comment` | `character varying(255)` | YES | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.6 `event_translation`

**Description:** PENDING

**Created in changeset:** `088-create-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | UQ, FK → `event.event_id` | — | PENDING |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDING |
| `translated_name` | `character varying(100)` | YES | — | — | PENDING |
| `translated_description` | `character varying(255)` | YES | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDING Allowed values (CHECK): `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |

### 4.7 `language`

**Description:** PENDING

**Created in changeset:** `084-create-language-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `language_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `code` | `character varying(10)` | NO | UQ | — | PENDING |
| `name` | `character varying(50)` | NO | — | — | PENDING |
| `is_active` | `boolean` | NO | — | `true` | PENDING |
| `is_default` | `boolean` | NO | — | `false` | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(50)` | NO | — | — | PENDING |
| `updated_by` | `character varying(50)` | NO | — | — | PENDING |

### 4.8 `module_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `module` | `character varying(50)` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.9 `notification_translation`

**Description:** Notification translations (Javadoc of `NotificationTranslation`).

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `notification_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_subject` | `text` | YES | — | — | PENDING |
| `translated_body` | `text` | YES | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.10 `notification_type_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `notification_type_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `translated_description` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.11 `profile_translation`

**Description:** PENDING

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `profile_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | UQ, FK → `language.language_id` | — | PENDING |
| `translated_bio` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.12 `review_translation`

**Description:** PENDING

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `review_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_comment` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.13 `seat_block_translation`

**Description:** PENDING

**Created in changeset:** `090-create-more-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `seat_block_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.14 `section_type_translation`

**Description:** PENDING

**Created in changeset:** `091-create-final-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `section_type_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.15 `theme_translation`

**Description:** PENDING

**Created in changeset:** `089-create-additional-translation-tables.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `theme_id` | `integer` | NO | UQ | — | PENDING |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDING |
| `translated_name` | `character varying(100)` | NO | — | — | PENDING |
| `translated_description` | `character varying(255)` | NO | — | — | PENDING |
| `source` | `character varying(50)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDING |

### 4.16 `translation_job`

**Description:** PENDING

**Created in changeset:** `087-translation-job-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `job_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `entity_type` | `character varying(50)` | NO | UQ | — | PENDING |
| `entity_id` | `bigint` | NO | UQ | — | PENDING |
| `source_language_id` | `bigint` | NO | FK → `language.language_id` | — | PENDING |
| `target_language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDING |
| `source_hash` | `character varying(64)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `PENDING`, `PROCESSING`, `COMPLETED`, `FAILED`. |
| `provider` | `character varying(20)` | NO | — | — | PENDING |
| `attempts` | `integer` | NO | — | `0` | PENDING |
| `last_error` | `character varying(1000)` | YES | — | — | PENDING |
| `next_retry_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `completed_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDING |

<a id="mod-notification"></a>

## 5. Module `notification`

### 5.1 `channel`

**Description:** PENDING

**Created in changeset:** `079-create-channel-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `channel_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(50)` | NO | UQ | — | PENDING |
| `description` | `character varying(100)` | NO | — | — | PENDING |
| `active` | `boolean` | NO | — | `true` | PENDING |
| `config` | `jsonb` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 5.2 `notification`

**Description:** PENDING

**Created in changeset:** `081-create-notification-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `channel_id` | `bigint` | NO | FK → `channel.channel_id` | — | PENDING |
| `notification_type_id` | `bigint` | NO | FK → `notification_type.notification_type_id` | — | PENDING |
| `entity_type` | `character varying(30)` | NO | — | — | PENDING |
| `entity_id` | `bigint` | NO | — | — | PENDING |
| `subject` | `character varying(150)` | NO | — | — | PENDING |
| `body` | `text` | NO | — | — | PENDING |
| `sent_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `idempotency_key` | `character varying(150)` | NO | UQ | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 5.3 `notification_type`

**Description:** PENDING

**Created in changeset:** `080-create-notification-type-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_type_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(50)` | NO | UQ | — | PENDING |
| `description` | `character varying(100)` | NO | — | — | PENDING |
| `active` | `boolean` | NO | — | `true` | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 5.4 `notification_user`

**Description:** PENDING

**Created in changeset:** `082-create-notification-user-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `notification_user_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `notification_id` | `bigint` | NO | UQ, FK → `notification.notification_id` | — | PENDING |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | PENDING |
| `email_address` | `character varying(255)` | YES | — | — | PENDING |
| `delivered_status` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `PENDING`, `SENT`, `DELIVERED`, `FAILED`. |
| `error_message` | `text` | YES | — | — | PENDING |
| `read_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

<a id="mod-payment"></a>

## 6. Module `payment`

### 6.1 `payment`

**Description:** PENDING

**Created in changeset:** `069-create-payment-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `payment_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | PENDING |
| `gateway` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `FAKE`, `WOMPI`. |
| `gateway_transaction_id` | `character varying(100)` | NO | UQ | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDING Allowed values (CHECK): `PENDING`, `APPROVED`, `REJECTED`, `ERROR`, `REFUNDED`. |
| `amount` | `numeric(19,4)` | NO | — | — | PENDING |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDING |
| `payment_method` | `character varying(20)` | YES | — | — | PENDING Allowed values (CHECK): `CARD`, `PSE`, `NEQUI`, `CASH`, `QR`. |
| `processed_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |
| `wallet_amount_applied` | `numeric(19,4)` | NO | — | `0` | PENDING CHECK constraint: `CHECK ((wallet_amount_applied >= (0)::numeric))`. |
| `wallet_transaction_id` | `bigint` | YES | FK → `wallet_transaction.transaction_id` | — | PENDING |

### 6.2 `payment_log`

**Description:** Audit of payment status changes (Javadoc of `PaymentLogEntity`).

**Created in changeset:** `070-create-payment-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `payment_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDING |
| `old_status` | `character varying(20)` | NO | — | — | PENDING |
| `new_status` | `character varying(20)` | NO | — | — | PENDING |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `reason` | `character varying(500)` | YES | — | — | PENDING |

### 6.3 `refund`

**Description:** PENDING

**Created in changeset:** `072-create-refund-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `refund_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'REQUESTED'::character varying` | PENDING Allowed values (CHECK): `REQUESTED`, `APPROVED`, `PROCESSED`, `FAILED`. |
| `reason` | `character varying(500)` | YES | — | — | PENDING |
| `requested_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `processed_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 6.4 `transaction_webhook`

**Description:** Audit of received webhooks (Javadoc of `TransactionWebhookEntity`).

**Created in changeset:** `071-create-transaction-webhook-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `webhook_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDING |
| `gateway_event_id` | `character varying(100)` | NO | UQ | — | PENDING |
| `payload` | `text` | NO | — | — | PENDING |
| `received_at` | `timestamp without time zone` | NO | — | — | PENDING |

<a id="mod-profile"></a>

## 7. Module `profile`

### 7.1 `profile`

**Description:** PENDING

**Created in changeset:** `032-create-profile-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `profile_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id`, UQ | — | PENDING |
| `city_id` | `integer` | YES | FK → `city.city_id` | — | PENDING |
| `stored_file_id` | `integer` | YES | FK → `stored_file.stored_file_id` | — | Profile picture file (integer, no JPA relation to the storage module). |
| `full_name` | `character varying(30)` | NO | — | — | PENDING |
| `bio` | `character varying(255)` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |
| `name_changed_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `preferred_language_id` | `bigint` | YES | FK → `language.language_id` | — | User's preferred language for displaying content. |

### 7.2 `profile_log`

**Description:** PENDING

**Created in changeset:** `033-create-profile-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `profile_id` | `bigint` | NO | FK → `profile.profile_id` | — | PENDING |
| `action` | `character varying(50)` | YES | — | — | PENDING |
| `old_value` | `character varying(255)` | YES | — | — | PENDING |
| `new_value` | `character varying(255)` | YES | — | — | PENDING |
| `occurred_at` | `timestamp without time zone` | YES | — | — | PENDING |

<a id="mod-seat"></a>

## 8. Module `seat`

### 8.1 `seat`

**Description:** PENDING

**Created in changeset:** `056-create-seat.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `seat_block_id` | `integer` | NO | FK → `seat_block.seat_block_id` | — | PENDING |
| `event_section_id` | `integer` | NO | UQ, FK → `event_section.event_section_id` | — | PENDING |
| `code` | `character varying(20)` | NO | UQ | — | PENDING |
| `row` | `integer` | NO | — | — | PENDING |
| `position` | `integer` | NO | — | — | PENDING |
| `type` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `REGULAR`, `COURTESY`. |
| `status` | `character varying(20)` | NO | — | `'available'::character varying` | PENDING Allowed values (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `reserved_by` | `integer` | YES | FK → `app_user.user_id` | — | PENDING |
| `reserved_until` | `timestamp without time zone` | YES | — | — | PENDING |

### 8.2 `seat_block`

**Description:** PENDING

**Created in changeset:** `055-create-seat-block.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_block_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_section_id` | `integer` | NO | FK → `event_section.event_section_id` | — | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `capacity` | `integer` | NO | — | — | PENDING CHECK constraint: `CHECK ((capacity > 0))`. |

### 8.3 `seat_log`

**Description:** PENDING

**Created in changeset:** `057-create-seat-log.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `seat_id` | `integer` | NO | FK → `seat.seat_id` | — | PENDING |
| `old_status` | `character varying(20)` | YES | — | — | PENDING Allowed values (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `new_status` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | PENDING |
| `changed_by` | `integer` | YES | FK → `app_user.user_id` | — | PENDING |
| `reason` | `character varying(255)` | YES | — | — | PENDING |

<a id="mod-section"></a>

## 9. Module `section`

### 9.1 `event_section`

**Description:** PENDING

**Created in changeset:** `053-create-event-section.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `event_section_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `integer` | NO | FK → `event.event_id`, UQ | — | PENDING |
| `section_type_id` | `integer` | NO | UQ, FK → `section_type.section_type_id` | — | PENDING |
| `capacity` | `integer` | NO | — | — | PENDING CHECK constraint: `CHECK ((capacity > 0))`. CHECK constraint: `CHECK ((available_seats <= capacity))`. |
| `available_seats` | `integer` | NO | — | — | PENDING CHECK constraint: `CHECK ((available_seats <= capacity))`. |
| `price` | `numeric(10,2)` | NO | — | — | PENDING CHECK constraint: `CHECK ((price >= (0)::numeric))`. |
| `is_active` | `boolean` | NO | — | `true` | PENDING |

### 9.2 `section_type`

**Description:** PENDING

**Created in changeset:** `052-create-section-type.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `section_type_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `active` | `boolean` | NO | — | `true` | PENDING |

<a id="mod-sectiontype"></a>

## 10. Module `sectiontype`

The `sectiontype` module has no tables of its own: the section type is stored in `section_type` (`section` module) and its translations in `section_type_translation` (`language` module).

<a id="mod-security"></a>

## 11. Module `security`

### 11.1 `account_activation`

**Description:** PENDING

**Created in changeset:** `007-create-account-activation-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `account_activation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `activation_code` | `character varying(8)` | NO | — | — | PENDING |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `activated` | `boolean` | NO | — | `false` | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.2 `account_lockout`

**Description:** PENDING

**Created in changeset:** `008-create-account-lockout-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `account_lockout_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `failed_attempts` | `integer` | NO | — | `0` | PENDING |
| `window_started_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `locked_until` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.3 `account_reactivation_token`

**Description:** PENDING

**Created in changeset:** `060-create-account-reactivation-token-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `reactivation_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `token` | `character varying(8)` | NO | — | — | PENDING |
| `token_status` | `boolean` | NO | — | `false` | PENDING |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.4 `app_user`

**Description:** PENDING

**Created in changeset:** `004-create-user-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | PENDING |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | PENDING |
| `alias` | `character varying(50)` | NO | UQ | — | PENDING |
| `activated` | `boolean` | NO | — | `false` | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 11.5 `auth_session`

**Description:** PENDING

**Created in changeset:** `009-create-auth-session-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `auth_session_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `access_token` | `character varying(512)` | NO | — | — | PENDING |
| `issued_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `ip_address` | `character varying(45)` | YES | — | — | PENDING |
| `user_agent` | `character varying(200)` | YES | — | — | PENDING |
| `revoked` | `boolean` | NO | — | `false` | PENDING |
| `revoked_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.6 `login_credentials`

**Description:** PENDING

**Created in changeset:** `006-create-login-credentials-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `login_credentials_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `password_hash` | `character varying(255)` | NO | — | — | PENDING |
| `email` | `character varying(255)` | NO | UQ | — | PENDING |
| `last_login_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.7 `oauth_account`

**Description:** PENDING

**Created in changeset:** `013-create-oauth-account-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `oauth_account_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | PENDING |
| `provider` | `character varying(30)` | NO | UQ | — | PENDING |
| `provider_user_id` | `character varying(100)` | NO | UQ | — | PENDING |
| `email` | `character varying(255)` | YES | — | — | PENDING |
| `linked_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.8 `organizer_petition`

**Description:** PENDING

**Created in changeset:** `015-create-organizer-petition-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `organizer_petition_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `application_date` | `timestamp without time zone` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |
| `stored_file_id` | `integer` | YES | FK → `stored_file.stored_file_id` | — | PENDING |
| `document_type` | `character varying(50)` | YES | — | — | PENDING |

### 11.9 `password_history`

**Description:** PENDING

**Created in changeset:** `012-create-password-history-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `password_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `password_hash` | `character varying(255)` | NO | — | — | PENDING |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDING |

### 11.10 `permission`

**Description:** PENDING

**Created in changeset:** `003-create-permission-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `code` | `character varying(50)` | NO | UQ | — | PENDING |
| `name` | `character varying(80)` | NO | — | — | PENDING |
| `description` | `character varying(150)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 11.11 `recover_password`

**Description:** PENDING

**Created in changeset:** `011-create-recover-password-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `recover_password_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `code` | `character varying(8)` | NO | — | — | PENDING |
| `code_status` | `boolean` | NO | — | `false` | PENDING |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `last_password_hash` | `character varying(255)` | YES | — | — | PENDING |

### 11.12 `refresh_token`

**Description:** PENDING

**Created in changeset:** `010-create-refresh-token-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `refresh_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `auth_session_id` | `integer` | NO | FK → `auth_session.auth_session_id` | — | PENDING |
| `token` | `character varying(512)` | NO | — | — | PENDING |
| `issued_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `revoked` | `boolean` | NO | — | `false` | PENDING |
| `revoked_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 11.13 `role`

**Description:** PENDING

**Created in changeset:** `002-create-role-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `role_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `code` | `character varying(50)` | NO | UQ | — | PENDING |
| `name` | `character varying(80)` | NO | — | — | PENDING |
| `description` | `character varying(150)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 11.14 `role_permission`

**Description:** PENDING

**Created in changeset:** `005-create-role-permission-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `role_permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | PENDING |
| `permission_id` | `integer` | NO | FK → `permission.permission_id` | — | PENDING |

### 11.15 `user_status`

**Description:** PENDING

**Created in changeset:** `001-create-user-status-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_status_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `code` | `character varying(30)` | NO | UQ | — | PENDING |
| `name` | `character varying(80)` | NO | — | — | PENDING |
| `description` | `character varying(150)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 11.16 `user_status_history`

**Description:** PENDING

**Created in changeset:** `014-create-user-status-history-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_status_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | PENDING |
| `reason` | `character varying(150)` | NO | — | — | PENDING |

<a id="mod-storage"></a>

## 12. Module `storage`

### 12.1 `file_category`

**Description:** PENDING

**Created in changeset:** `019-create-file-category-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `file_category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `storage_provider_id` | `integer` | NO | FK → `storage_provider.storage_provider_id` | — | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `code` | `character varying(50)` | NO | UQ | — | PENDING |
| `is_public` | `boolean` | NO | — | `false` | PENDING |
| `allowed_extensions` | `character varying(100)` | NO | — | — | PENDING |
| `max_size_mb` | `integer` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 12.2 `storage_operation_log`

**Description:** Immutable log of storage operations: rows are only appended, never updated (Javadoc of `StorageOperationLogEntity`).

**Created in changeset:** `021-create-storage-operation-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `stored_file_id` | `integer` | NO | FK → `stored_file.stored_file_id` | — | PENDING |
| `performed_by` | `integer` | NO | FK → `app_user.user_id` | — | PENDING |
| `operation` | `character varying(20)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | — | PENDING |
| `error_message` | `character varying(500)` | YES | — | — | PENDING |
| `occurred_at` | `timestamp without time zone` | NO | — | — | PENDING |

### 12.3 `storage_provider`

**Description:** PENDING

**Created in changeset:** `018-create-storage-provider-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `storage_provider_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(100)` | NO | — | — | PENDING |
| `code` | `character varying(20)` | NO | UQ | — | PENDING |
| `is_active` | `boolean` | NO | — | `false` | PENDING |
| `config` | `jsonb` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

### 12.4 `stored_file`

**Description:** PENDING

**Created in changeset:** `020-create-stored-file-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `stored_file_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `file_category_id` | `integer` | NO | FK → `file_category.file_category_id` | — | PENDING |
| `uploaded_by` | `integer` | NO | FK → `app_user.user_id` | — | ID of the user who uploaded the file. |
| `s3_key` | `character varying(512)` | NO | — | — | PENDING |
| `original_filename` | `character varying(255)` | NO | — | — | PENDING |
| `content_type` | `character varying(100)` | NO | — | — | PENDING |
| `size_bytes` | `bigint` | NO | — | — | PENDING |
| `public_url` | `character varying(512)` | YES | — | — | PENDING |
| `owner_entity_id` | `integer` | YES | — | — | PENDING |
| `owner_entity_type` | `character varying(50)` | YES | — | — | PENDING |
| `deleted` | `boolean` | NO | — | `false` | PENDING |
| `uploaded_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `created_by` | `character varying(50)` | YES | — | — | PENDING |
| `updated_by` | `character varying(50)` | YES | — | — | PENDING |

<a id="mod-theme"></a>

## 13. Module `theme`

### 13.1 `theme`

**Description:** PENDING

**Created in changeset:** `034-create-theme-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `theme_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `name` | `character varying(100)` | NO | UQ | — | PENDING |
| `description` | `character varying(255)` | NO | — | — | PENDING |
| `default_palette` | `jsonb` | NO | — | — | PENDING |

### 13.2 `theme_customization`

**Description:** PENDING

**Created in changeset:** `036-create-theme-customization-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `customization_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_theme_id` | `bigint` | NO | UQ, FK → `user_theme.user_theme_id` | — | Customized user theme. |
| `property` | `character varying(100)` | NO | UQ | — | PENDING |
| `value` | `character varying(255)` | NO | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 13.3 `theme_log`

**Description:** Theme audit log: rows are only appended, never updated (Javadoc of `ThemeLogEntity`).

**Created in changeset:** `037-create-theme-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_theme_id` | `bigint` | NO | FK → `user_theme.user_theme_id` | — | PENDING |
| `action` | `character varying(50)` | NO | — | — | PENDING |
| `property` | `character varying(100)` | YES | — | — | PENDING |
| `old_value` | `character varying(255)` | YES | — | — | PENDING |
| `new_value` | `character varying(255)` | YES | — | — | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |

### 13.4 `user_theme`

**Description:** PENDING

**Created in changeset:** `035-create-user-theme-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `user_theme_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | User the theme belongs to. |
| `theme_id` | `integer` | NO | UQ, FK → `theme.theme_id` | — | Selected theme. |
| `is_active` | `boolean` | NO | — | `true` | PENDING |
| `created_at` | `timestamp without time zone` | YES | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | YES | — | — | PENDING |

<a id="mod-ticket"></a>

## 14. Module `ticket`

### 14.1 `order`

**Description:** PENDING

**Created in changeset:** `064-create-order-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `order_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `total_amount` | `numeric(19,4)` | NO | — | — | PENDING |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDING |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDING Allowed values (CHECK): `DRAFT`, `PAYMENT_PENDING`, `PAID`, `CANCELLED`, `REFUNDED`, `USED`. |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 14.2 `seat_ticket`

**Description:** N:M relationship between seat and ticket, with the price captured at purchase time (Javadoc of `SeatTicketEntity`).

**Created in changeset:** `066-create-seat-ticket-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `seat_ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `seat_id` | `integer` | NO | UQ, FK → `seat.seat_id` | — | PENDING |
| `ticket_id` | `bigint` | NO | UQ, FK → `ticket.ticket_id` | — | PENDING |
| `price` | `numeric(19,4)` | NO | — | — | PENDING |

### 14.3 `ticket`

**Description:** PENDING

**Created in changeset:** `065-create-ticket-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDING |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDING |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | PENDING |
| `code` | `character varying(50)` | NO | UQ | — | PENDING |
| `qr_code` | `character varying(500)` | NO | — | — | PENDING |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDING Allowed values (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `expiration_date` | `timestamp without time zone` | YES | — | — | PENDING |
| `total_price` | `numeric(19,4)` | NO | — | — | PENDING |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 14.4 `ticket_checkin`

**Description:** PENDING

**Created in changeset:** `067-create-ticket-checkin-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `checkin_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id`, UQ | — | PENDING |
| `checkin_time` | `timestamp without time zone` | NO | — | — | PENDING |
| `validated_by` | `bigint` | NO | FK → `app_user.user_id` | — | PENDING |

### 14.5 `ticket_log`

**Description:** Immutable ticket audit (Javadoc of `TicketLogEntity`).

**Created in changeset:** `068-create-ticket-log-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `ticket_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id` | — | PENDING |
| `old_status` | `character varying(20)` | YES | — | — | PENDING Allowed values (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `new_status` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `changed_by` | `character varying(100)` | YES | — | — | PENDING |
| `reason` | `character varying(255)` | YES | — | — | PENDING |

<a id="mod-wallet"></a>

## 15. Module `wallet`

### 15.1 `wallet`

**Description:** Wallet. Uses optimistic locking (`@Version`): if two transactions modify the same wallet at once, the second one fails (Javadoc of `WalletEntity`).

**Created in changeset:** `074-create-wallet-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `wallet_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `user_id` | `bigint` | NO | UQ | — | PENDING |
| `balance` | `numeric(19,4)` | NO | — | `0` | PENDING CHECK constraint: `CHECK ((balance >= (0)::numeric))`. |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDING Allowed values (CHECK): `COP`. |
| `version` | `bigint` | NO | — | `0` | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
| `updated_by` | `character varying(100)` | YES | — | — | PENDING |

### 15.2 `wallet_reference`

**Description:** Wallet movement reference. Immutable: it has no audit or version columns (Javadoc of `WalletReferenceEntity`).

**Created in changeset:** `076-create-wallet-reference-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `wallet_reference_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `transaction_id` | `bigint` | NO | FK → `wallet_transaction.transaction_id` | — | PENDING |
| `entity_type` | `character varying(30)` | NO | — | — | PENDING Allowed values (CHECK): `EVENT_CANCELLATION`, `ORDER`, `TICKET`, `ADMIN_ADJUSTMENT`. |
| `entity_id` | `bigint` | YES | — | — | PENDING |

### 15.3 `wallet_transaction`

**Description:** Wallet transaction. Immutable: it only has `created_at` and `created_by` (Javadoc of `WalletTransactionEntity`).

**Created in changeset:** `075-create-wallet-transaction-table.yaml`

| Column | Type | Null | Key | Default value | Description |
|---|---|---|---|---|---|
| `transaction_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDING |
| `wallet_id` | `bigint` | NO | FK → `wallet.wallet_id` | — | PENDING |
| `type` | `character varying(20)` | NO | — | — | PENDING Allowed values (CHECK): `CREDIT`, `PAYMENT`, `REVERSAL`, `ADJUSTMENT`. |
| `amount` | `numeric(19,4)` | NO | — | — | PENDING CHECK constraint: `CHECK ((amount > (0)::numeric))`. |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDING Allowed values (CHECK): `PENDING`, `COMPLETED`, `FAILED`. |
| `balance_after` | `numeric(19,4)` | YES | — | — | PENDING |
| `idempotency_key` | `character varying(100)` | NO | UQ | — | PENDING |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDING |
| `created_by` | `character varying(100)` | YES | — | — | PENDING |
