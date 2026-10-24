---
title: "Diccionario de datos"
lang: es
source: "06_Base_Datos/Script_BD_implementado.sql"
generated_from: "lozano2303/TuEvento origin/develop 2d259e7 (Liquibase 4.31.1, PostgreSQL 17.10)"
generated_on: 2026-10-24
status: borrador
reviewed_by: ""
---
# Diccionario de datos — Tu Evento

> **Borrador generado del esquema implementado.** Este diccionario se generó el 2026-10-24 a partir de [`Script_BD_implementado.sql`](Script_BD_implementado.sql): los 171 changesets de Liquibase 4.31.1 de `lozano2303/TuEvento` (`origin/develop` / `2d259e7`) aplicados sobre un PostgreSQL 17.10 temporal. Los nombres, tipos, nulidad, claves y valores por defecto salen del esquema. Las descripciones salen de los comentarios de la base de datos y del código (Javadoc); donde no hay ninguna, dice **PENDIENTE** para que el equipo la complete. El módulo de cada tabla sale de la entidad JPA que la mapea.
>
> Resumen: 75 tablas, 570 columnas, 555 descripciones de columna pendientes.
>
> La versión anterior de este documento (diccionario de diseño convertido del XLSX `04_Diseno_Software/Diccionario de datos Tu-Evento.xlsx`) se conserva en el historial de Git: `git show 5e68501:es/06_Base_Datos/Diccionario_Datos.md`.

**Leyenda de la columna Clave:** PK = clave primaria · FK → `tabla.columna` = clave foránea · UQ = forma parte de una restricción UNIQUE.

**Contenido**

1. [`category`](#mod-category) — 2 tablas
2. [`event`](#mod-event) — 7 tablas
3. [`geolocation`](#mod-geolocation) — 3 tablas
4. [`language`](#mod-language) — 16 tablas
5. [`notification`](#mod-notification) — 4 tablas
6. [`payment`](#mod-payment) — 4 tablas
7. [`profile`](#mod-profile) — 2 tablas
8. [`seat`](#mod-seat) — 3 tablas
9. [`section`](#mod-section) — 2 tablas
10. [`sectiontype`](#mod-sectiontype) — 0 tablas
11. [`security`](#mod-security) — 16 tablas
12. [`storage`](#mod-storage) — 4 tablas
13. [`theme`](#mod-theme) — 4 tablas
14. [`ticket`](#mod-ticket) — 5 tablas
15. [`wallet`](#mod-wallet) — 3 tablas

<a id="mod-category"></a>

## 1. Módulo `category`

### 1.1 `category`

**Descripción:** PENDIENTE

**Creada en el changeset:** `047-create-category.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `description` | `character varying(100)` | NO | — | — | PENDIENTE |
| `active` | `boolean` | NO | — | `true` | PENDIENTE |
| `visible` | `boolean` | NO | — | `true` | PENDIENTE |
| `dad_id` | `integer` | SÍ | FK → `category.category_id` | — | Categoría padre; nulo si es una categoría raíz. |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | NO | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | NO | — | — | PENDIENTE |

### 1.2 `category_event`

**Descripción:** PENDIENTE

**Creada en el changeset:** `048-create-category-event.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `category_event_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | Categoría asociada al evento. |
| `event_id` | `integer` | NO | UQ, FK → `event.event_id` | — | Evento asociado a la categoría. |

<a id="mod-event"></a>

## 2. Módulo `event`

### 2.1 `event`

**Descripción:** PENDIENTE

**Creada en el changeset:** `039-create-event.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `event_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `site_id` | `bigint` | NO | UQ, FK → `site.site_id` | — | PENDIENTE |
| `event_name` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `start_date` | `date` | NO | UQ | — | PENDIENTE Restricción CHECK: `CHECK ((finish_date > start_date))`. |
| `finish_date` | `date` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((finish_date > start_date))`. |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDIENTE Valores permitidos (CHECK): `DRAFT`, `PENDING_REVIEW`, `PUBLISHED`, `REJECTED`, `CANCELLED`, `COMPLETED`. |
| `is_public` | `boolean` | NO | — | `true` | PENDIENTE |
| `available_seats` | `integer` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `rejection_reason` | `text` | SÍ | — | — | Motivo de rechazo; se llena cuando el estado es REJECTED y se borra al volver a DRAFT. |

### 2.2 `event_layout`

**Descripción:** PENDIENTE

**Creada en el changeset:** `041-create-event-layout.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `event_layout_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `layout_data` | `jsonb` | NO | — | — | PENDIENTE |

### 2.3 `event_log`

**Descripción:** PENDIENTE

**Creada en el changeset:** `093-create-event-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `action` | `character varying(100)` | NO | — | — | PENDIENTE |
| `old_value` | `text` | SÍ | — | — | PENDIENTE |
| `new_value` | `text` | SÍ | — | — | PENDIENTE |
| `occurred_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |

### 2.4 `event_media`

**Descripción:** PENDIENTE

**Creada en el changeset:** `042-create-event-media.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `media_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `img_url` | `character varying(255)` | NO | — | — | PENDIENTE |

### 2.5 `event_media_log`

**Descripción:** PENDIENTE

**Creada en el changeset:** `043-create-event-media-log.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `media_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `media_id` | `bigint` | NO | FK → `event_media.media_id` | — | PENDIENTE |
| `img_url` | `character varying(255)` | NO | — | — | PENDIENTE |
| `version` | `integer` | NO | — | — | PENDIENTE |
| `is_visible` | `boolean` | NO | — | `true` | PENDIENTE |

### 2.6 `event_rating`

**Descripción:** PENDIENTE

**Creada en el changeset:** `044-create-event-rating.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `rating_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `rating` | `integer` | SÍ | — | — | PENDIENTE Restricción CHECK: `CHECK (((rating IS NULL) OR ((rating >= 1) AND (rating <= 5))))`. |
| `comment` | `character varying()` | NO | — | — | PENDIENTE |
| `is_visible` | `boolean` | NO | — | `true` | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `parent_rating_id` | `bigint` | SÍ | FK → `event_rating.rating_id` | — | Comentario al que responde; nulo si es un comentario principal (borrado en cascada). |
| `edited_at` | `timestamp without time zone` | SÍ | — | — | Fecha y hora de la última edición del comentario. |
| `reply_to_user_id` | `bigint` | SÍ | — | — | ID del usuario al que se responde directamente (para menciones). |
| `reply_to_user_name` | `character varying(100)` | SÍ | — | — | Nombre del usuario al que se responde (para mostrar @Nombre). |

### 2.7 `event_status_log`

**Descripción:** PENDIENTE

**Creada en el changeset:** `040-create-event-status-log.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `status_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `old_status` | `character varying(20)` | SÍ | — | — | PENDIENTE |
| `new_status` | `character varying(20)` | NO | — | — | PENDIENTE |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `changed_by` | `bigint` | SÍ | FK → `app_user.user_id` | — | PENDIENTE |
| `reason` | `text` | SÍ | — | — | Motivo de rechazo del administrador cuando el nuevo estado es REJECTED; nulo en otro caso. |

<a id="mod-geolocation"></a>

## 3. Módulo `geolocation`

### 3.1 `city`

**Descripción:** PENDIENTE

**Creada en el changeset:** `026-create-city-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `city_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `department_id` | `integer` | NO | FK → `department.department_id` | — | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `code` | `character varying(10)` | NO | UQ | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 3.2 `department`

**Descripción:** PENDIENTE

**Creada en el changeset:** `025-create-department-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `department_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `code` | `character varying(10)` | NO | UQ | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 3.3 `site`

**Descripción:** PENDIENTE

**Creada en el changeset:** `027-create-site-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `site_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `city_id` | `integer` | NO | FK → `city.city_id` | — | PENDIENTE |
| `name` | `character varying(150)` | NO | — | — | PENDIENTE |
| `address` | `character varying(200)` | NO | — | — | PENDIENTE |
| `capacity` | `integer` | NO | — | — | PENDIENTE |
| `latitude` | `numeric(9,6)` | NO | — | — | PENDIENTE |
| `longitude` | `numeric(9,6)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

<a id="mod-language"></a>

## 4. Módulo `language`

### 4.1 `action_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `action` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.2 `category_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `088-create-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `category_id` | `integer` | NO | UQ, FK → `category.category_id` | — | PENDIENTE |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `translated_description` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDIENTE Valores permitidos (CHECK): `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |

### 4.3 `channel_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `channel_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `translated_description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.4 `event_comment_reply_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `reply_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_reply_text` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.5 `event_rating_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `090-create-more-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `rating_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_comment` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.6 `event_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `088-create-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | UQ, FK → `event.event_id` | — | PENDIENTE |
| `language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDIENTE |
| `translated_name` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `translated_description` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDIENTE Valores permitidos (CHECK): `DRAFT`, `PUBLISHED`, `PENDING_REVIEW`. |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |

### 4.7 `language`

**Descripción:** PENDIENTE

**Creada en el changeset:** `084-create-language-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `language_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `code` | `character varying(10)` | NO | UQ | — | PENDIENTE |
| `name` | `character varying(50)` | NO | — | — | PENDIENTE |
| `is_active` | `boolean` | NO | — | `true` | PENDIENTE |
| `is_default` | `boolean` | NO | — | `false` | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | NO | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | NO | — | — | PENDIENTE |

### 4.8 `module_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `module` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.9 `notification_translation`

**Descripción:** Traducción de notificaciones (Javadoc de `NotificationTranslation`).

**Creada en el changeset:** `089-create-additional-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `notification_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_subject` | `text` | SÍ | — | — | PENDIENTE |
| `translated_body` | `text` | SÍ | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.10 `notification_type_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `notification_type_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `translated_description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.11 `profile_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `089-create-additional-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `profile_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | UQ, FK → `language.language_id` | — | PENDIENTE |
| `translated_bio` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.12 `review_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `090-create-more-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `review_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_comment` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.13 `seat_block_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `090-create-more-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `seat_block_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.14 `section_type_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `091-create-final-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `section_type_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.15 `theme_translation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `089-create-additional-translation-tables.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `translation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `theme_id` | `integer` | NO | UQ | — | PENDIENTE |
| `language_id` | `integer` | NO | FK → `language.language_id`, UQ | — | PENDIENTE |
| `translated_name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `translated_description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `source` | `character varying(50)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'draft'::character varying` | PENDIENTE |

### 4.16 `translation_job`

**Descripción:** PENDIENTE

**Creada en el changeset:** `087-translation-job-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `job_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `entity_type` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `entity_id` | `bigint` | NO | UQ | — | PENDIENTE |
| `source_language_id` | `bigint` | NO | FK → `language.language_id` | — | PENDIENTE |
| `target_language_id` | `bigint` | NO | UQ, FK → `language.language_id` | — | PENDIENTE |
| `source_hash` | `character varying(64)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `PENDING`, `PROCESSING`, `COMPLETED`, `FAILED`. |
| `provider` | `character varying(20)` | NO | — | — | PENDIENTE |
| `attempts` | `integer` | NO | — | `0` | PENDIENTE |
| `last_error` | `character varying(1000)` | SÍ | — | — | PENDIENTE |
| `next_retry_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `completed_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `created_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |
| `updated_by` | `character varying(255)` | NO | — | `'system'::character varying` | PENDIENTE |

<a id="mod-notification"></a>

## 5. Módulo `notification`

### 5.1 `channel`

**Descripción:** PENDIENTE

**Creada en el changeset:** `079-create-channel-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `channel_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `description` | `character varying(100)` | NO | — | — | PENDIENTE |
| `active` | `boolean` | NO | — | `true` | PENDIENTE |
| `config` | `jsonb` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 5.2 `notification`

**Descripción:** PENDIENTE

**Creada en el changeset:** `081-create-notification-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `notification_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `channel_id` | `bigint` | NO | FK → `channel.channel_id` | — | PENDIENTE |
| `notification_type_id` | `bigint` | NO | FK → `notification_type.notification_type_id` | — | PENDIENTE |
| `entity_type` | `character varying(30)` | NO | — | — | PENDIENTE |
| `entity_id` | `bigint` | NO | — | — | PENDIENTE |
| `subject` | `character varying(150)` | NO | — | — | PENDIENTE |
| `body` | `text` | NO | — | — | PENDIENTE |
| `sent_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `idempotency_key` | `character varying(150)` | NO | UQ | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 5.3 `notification_type`

**Descripción:** PENDIENTE

**Creada en el changeset:** `080-create-notification-type-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `notification_type_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `description` | `character varying(100)` | NO | — | — | PENDIENTE |
| `active` | `boolean` | NO | — | `true` | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 5.4 `notification_user`

**Descripción:** PENDIENTE

**Creada en el changeset:** `082-create-notification-user-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `notification_user_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `notification_id` | `bigint` | NO | UQ, FK → `notification.notification_id` | — | PENDIENTE |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | PENDIENTE |
| `email_address` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `delivered_status` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `PENDING`, `SENT`, `DELIVERED`, `FAILED`. |
| `error_message` | `text` | SÍ | — | — | PENDIENTE |
| `read_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

<a id="mod-payment"></a>

## 6. Módulo `payment`

### 6.1 `payment`

**Descripción:** PENDIENTE

**Creada en el changeset:** `069-create-payment-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `payment_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | PENDIENTE |
| `gateway` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `FAKE`, `WOMPI`. |
| `gateway_transaction_id` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDIENTE Valores permitidos (CHECK): `PENDING`, `APPROVED`, `REJECTED`, `ERROR`, `REFUNDED`. |
| `amount` | `numeric(19,4)` | NO | — | — | PENDIENTE |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDIENTE |
| `payment_method` | `character varying(20)` | SÍ | — | — | PENDIENTE Valores permitidos (CHECK): `CARD`, `PSE`, `NEQUI`, `CASH`, `QR`. |
| `processed_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `wallet_amount_applied` | `numeric(19,4)` | NO | — | `0` | PENDIENTE Restricción CHECK: `CHECK ((wallet_amount_applied >= (0)::numeric))`. |
| `wallet_transaction_id` | `bigint` | SÍ | FK → `wallet_transaction.transaction_id` | — | PENDIENTE |

### 6.2 `payment_log`

**Descripción:** Auditoría de cambios de estado de los pagos (Javadoc de `PaymentLogEntity`).

**Creada en el changeset:** `070-create-payment-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `payment_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDIENTE |
| `old_status` | `character varying(20)` | NO | — | — | PENDIENTE |
| `new_status` | `character varying(20)` | NO | — | — | PENDIENTE |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `reason` | `character varying(500)` | SÍ | — | — | PENDIENTE |

### 6.3 `refund`

**Descripción:** PENDIENTE

**Creada en el changeset:** `072-create-refund-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `refund_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'REQUESTED'::character varying` | PENDIENTE Valores permitidos (CHECK): `REQUESTED`, `APPROVED`, `PROCESSED`, `FAILED`. |
| `reason` | `character varying(500)` | SÍ | — | — | PENDIENTE |
| `requested_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `processed_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 6.4 `transaction_webhook`

**Descripción:** Auditoría de los webhooks recibidos (Javadoc de `TransactionWebhookEntity`).

**Creada en el changeset:** `071-create-transaction-webhook-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `webhook_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `payment_id` | `bigint` | NO | FK → `payment.payment_id` | — | PENDIENTE |
| `gateway_event_id` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `payload` | `text` | NO | — | — | PENDIENTE |
| `received_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |

<a id="mod-profile"></a>

## 7. Módulo `profile`

### 7.1 `profile`

**Descripción:** PENDIENTE

**Creada en el changeset:** `032-create-profile-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `profile_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id`, UQ | — | PENDIENTE |
| `city_id` | `integer` | SÍ | FK → `city.city_id` | — | PENDIENTE |
| `stored_file_id` | `integer` | SÍ | FK → `stored_file.stored_file_id` | — | Archivo de la foto de perfil (entero, sin relación JPA con el módulo storage). |
| `full_name` | `character varying(30)` | NO | — | — | PENDIENTE |
| `bio` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `name_changed_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `preferred_language_id` | `bigint` | SÍ | FK → `language.language_id` | — | Idioma preferido del usuario para mostrar el contenido. |

### 7.2 `profile_log`

**Descripción:** PENDIENTE

**Creada en el changeset:** `033-create-profile-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `profile_id` | `bigint` | NO | FK → `profile.profile_id` | — | PENDIENTE |
| `action` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `old_value` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `new_value` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `occurred_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

<a id="mod-seat"></a>

## 8. Módulo `seat`

### 8.1 `seat`

**Descripción:** PENDIENTE

**Creada en el changeset:** `056-create-seat.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `seat_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `seat_block_id` | `integer` | NO | FK → `seat_block.seat_block_id` | — | PENDIENTE |
| `event_section_id` | `integer` | NO | UQ, FK → `event_section.event_section_id` | — | PENDIENTE |
| `code` | `character varying(20)` | NO | UQ | — | PENDIENTE |
| `row` | `integer` | NO | — | — | PENDIENTE |
| `position` | `integer` | NO | — | — | PENDIENTE |
| `type` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `REGULAR`, `COURTESY`. |
| `status` | `character varying(20)` | NO | — | `'available'::character varying` | PENDIENTE Valores permitidos (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `reserved_by` | `integer` | SÍ | FK → `app_user.user_id` | — | PENDIENTE |
| `reserved_until` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 8.2 `seat_block`

**Descripción:** PENDIENTE

**Creada en el changeset:** `055-create-seat-block.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `seat_block_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_section_id` | `integer` | NO | FK → `event_section.event_section_id` | — | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `capacity` | `integer` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((capacity > 0))`. |

### 8.3 `seat_log`

**Descripción:** PENDIENTE

**Creada en el changeset:** `057-create-seat-log.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `seat_log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `seat_id` | `integer` | NO | FK → `seat.seat_id` | — | PENDIENTE |
| `old_status` | `character varying(20)` | SÍ | — | — | PENDIENTE Valores permitidos (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `new_status` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `AVAILABLE`, `RESERVED`, `SOLD`, `COURTESY`. |
| `changed_at` | `timestamp without time zone` | NO | — | `now()` | PENDIENTE |
| `changed_by` | `integer` | SÍ | FK → `app_user.user_id` | — | PENDIENTE |
| `reason` | `character varying(255)` | SÍ | — | — | PENDIENTE |

<a id="mod-section"></a>

## 9. Módulo `section`

### 9.1 `event_section`

**Descripción:** PENDIENTE

**Creada en el changeset:** `053-create-event-section.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `event_section_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `integer` | NO | FK → `event.event_id`, UQ | — | PENDIENTE |
| `section_type_id` | `integer` | NO | UQ, FK → `section_type.section_type_id` | — | PENDIENTE |
| `capacity` | `integer` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((capacity > 0))`. Restricción CHECK: `CHECK ((available_seats <= capacity))`. |
| `available_seats` | `integer` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((available_seats <= capacity))`. |
| `price` | `numeric(10,2)` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((price >= (0)::numeric))`. |
| `is_active` | `boolean` | NO | — | `true` | PENDIENTE |

### 9.2 `section_type`

**Descripción:** PENDIENTE

**Creada en el changeset:** `052-create-section-type.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `section_type_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `active` | `boolean` | NO | — | `true` | PENDIENTE |

<a id="mod-sectiontype"></a>

## 10. Módulo `sectiontype`

El módulo `sectiontype` no tiene tablas propias: el tipo de sección se guarda en `section_type` (módulo `section`) y sus traducciones en `section_type_translation` (módulo `language`).

<a id="mod-security"></a>

## 11. Módulo `security`

### 11.1 `account_activation`

**Descripción:** PENDIENTE

**Creada en el changeset:** `007-create-account-activation-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `account_activation_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `activation_code` | `character varying(8)` | NO | — | — | PENDIENTE |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `activated` | `boolean` | NO | — | `false` | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.2 `account_lockout`

**Descripción:** PENDIENTE

**Creada en el changeset:** `008-create-account-lockout-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `account_lockout_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `failed_attempts` | `integer` | NO | — | `0` | PENDIENTE |
| `window_started_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `locked_until` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.3 `account_reactivation_token`

**Descripción:** PENDIENTE

**Creada en el changeset:** `060-create-account-reactivation-token-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `reactivation_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `token` | `character varying(8)` | NO | — | — | PENDIENTE |
| `token_status` | `boolean` | NO | — | `false` | PENDIENTE |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.4 `app_user`

**Descripción:** PENDIENTE

**Creada en el changeset:** `004-create-user-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `user_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | PENDIENTE |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | PENDIENTE |
| `alias` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `activated` | `boolean` | NO | — | `false` | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 11.5 `auth_session`

**Descripción:** PENDIENTE

**Creada en el changeset:** `009-create-auth-session-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `auth_session_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `access_token` | `character varying(512)` | NO | — | — | PENDIENTE |
| `issued_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `ip_address` | `character varying(45)` | SÍ | — | — | PENDIENTE |
| `user_agent` | `character varying(200)` | SÍ | — | — | PENDIENTE |
| `revoked` | `boolean` | NO | — | `false` | PENDIENTE |
| `revoked_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.6 `login_credentials`

**Descripción:** PENDIENTE

**Creada en el changeset:** `006-create-login-credentials-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `login_credentials_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `password_hash` | `character varying(255)` | NO | — | — | PENDIENTE |
| `email` | `character varying(255)` | NO | UQ | — | PENDIENTE |
| `last_login_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.7 `oauth_account`

**Descripción:** PENDIENTE

**Creada en el changeset:** `013-create-oauth-account-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `oauth_account_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | PENDIENTE |
| `provider` | `character varying(30)` | NO | UQ | — | PENDIENTE |
| `provider_user_id` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `email` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `linked_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.8 `organizer_petition`

**Descripción:** PENDIENTE

**Creada en el changeset:** `015-create-organizer-petition-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `organizer_petition_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `application_date` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `stored_file_id` | `integer` | SÍ | FK → `stored_file.stored_file_id` | — | PENDIENTE |
| `document_type` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 11.9 `password_history`

**Descripción:** PENDIENTE

**Creada en el changeset:** `012-create-password-history-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `password_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `password_hash` | `character varying(255)` | NO | — | — | PENDIENTE |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |

### 11.10 `permission`

**Descripción:** PENDIENTE

**Creada en el changeset:** `003-create-permission-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `code` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `name` | `character varying(80)` | NO | — | — | PENDIENTE |
| `description` | `character varying(150)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 11.11 `recover_password`

**Descripción:** PENDIENTE

**Creada en el changeset:** `011-create-recover-password-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `recover_password_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `code` | `character varying(8)` | NO | — | — | PENDIENTE |
| `code_status` | `boolean` | NO | — | `false` | PENDIENTE |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `last_password_hash` | `character varying(255)` | SÍ | — | — | PENDIENTE |

### 11.12 `refresh_token`

**Descripción:** PENDIENTE

**Creada en el changeset:** `010-create-refresh-token-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `refresh_token_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `auth_session_id` | `integer` | NO | FK → `auth_session.auth_session_id` | — | PENDIENTE |
| `token` | `character varying(512)` | NO | — | — | PENDIENTE |
| `issued_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `expires_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `revoked` | `boolean` | NO | — | `false` | PENDIENTE |
| `revoked_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 11.13 `role`

**Descripción:** PENDIENTE

**Creada en el changeset:** `002-create-role-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `role_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `code` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `name` | `character varying(80)` | NO | — | — | PENDIENTE |
| `description` | `character varying(150)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 11.14 `role_permission`

**Descripción:** PENDIENTE

**Creada en el changeset:** `005-create-role-permission-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `role_permission_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `role_id` | `integer` | NO | FK → `role.role_id` | — | PENDIENTE |
| `permission_id` | `integer` | NO | FK → `permission.permission_id` | — | PENDIENTE |

### 11.15 `user_status`

**Descripción:** PENDIENTE

**Creada en el changeset:** `001-create-user-status-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `user_status_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `code` | `character varying(30)` | NO | UQ | — | PENDIENTE |
| `name` | `character varying(80)` | NO | — | — | PENDIENTE |
| `description` | `character varying(150)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 11.16 `user_status_history`

**Descripción:** PENDIENTE

**Creada en el changeset:** `014-create-user-status-history-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `user_status_history_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `user_status_id` | `integer` | NO | FK → `user_status.user_status_id` | — | PENDIENTE |
| `reason` | `character varying(150)` | NO | — | — | PENDIENTE |

<a id="mod-storage"></a>

## 12. Módulo `storage`

### 12.1 `file_category`

**Descripción:** PENDIENTE

**Creada en el changeset:** `019-create-file-category-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `file_category_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `storage_provider_id` | `integer` | NO | FK → `storage_provider.storage_provider_id` | — | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `code` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `is_public` | `boolean` | NO | — | `false` | PENDIENTE |
| `allowed_extensions` | `character varying(100)` | NO | — | — | PENDIENTE |
| `max_size_mb` | `integer` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 12.2 `storage_operation_log`

**Descripción:** Registro inmutable de operaciones de almacenamiento: solo se agregan filas, nunca se actualizan (Javadoc de `StorageOperationLogEntity`).

**Creada en el changeset:** `021-create-storage-operation-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `log_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `stored_file_id` | `integer` | NO | FK → `stored_file.stored_file_id` | — | PENDIENTE |
| `performed_by` | `integer` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `operation` | `character varying(20)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | — | PENDIENTE |
| `error_message` | `character varying(500)` | SÍ | — | — | PENDIENTE |
| `occurred_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |

### 12.3 `storage_provider`

**Descripción:** PENDIENTE

**Creada en el changeset:** `018-create-storage-provider-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `storage_provider_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(100)` | NO | — | — | PENDIENTE |
| `code` | `character varying(20)` | NO | UQ | — | PENDIENTE |
| `is_active` | `boolean` | NO | — | `false` | PENDIENTE |
| `config` | `jsonb` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

### 12.4 `stored_file`

**Descripción:** PENDIENTE

**Creada en el changeset:** `020-create-stored-file-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `stored_file_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `file_category_id` | `integer` | NO | FK → `file_category.file_category_id` | — | PENDIENTE |
| `uploaded_by` | `integer` | NO | FK → `app_user.user_id` | — | ID del usuario que subió el archivo. |
| `s3_key` | `character varying(512)` | NO | — | — | PENDIENTE |
| `original_filename` | `character varying(255)` | NO | — | — | PENDIENTE |
| `content_type` | `character varying(100)` | NO | — | — | PENDIENTE |
| `size_bytes` | `bigint` | NO | — | — | PENDIENTE |
| `public_url` | `character varying(512)` | SÍ | — | — | PENDIENTE |
| `owner_entity_id` | `integer` | SÍ | — | — | PENDIENTE |
| `owner_entity_type` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `deleted` | `boolean` | NO | — | `false` | PENDIENTE |
| `uploaded_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `created_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(50)` | SÍ | — | — | PENDIENTE |

<a id="mod-theme"></a>

## 13. Módulo `theme`

### 13.1 `theme`

**Descripción:** PENDIENTE

**Creada en el changeset:** `034-create-theme-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `theme_id` | `integer` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `name` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `description` | `character varying(255)` | NO | — | — | PENDIENTE |
| `default_palette` | `jsonb` | NO | — | — | PENDIENTE |

### 13.2 `theme_customization`

**Descripción:** PENDIENTE

**Creada en el changeset:** `036-create-theme-customization-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `customization_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_theme_id` | `bigint` | NO | UQ, FK → `user_theme.user_theme_id` | — | Tema de usuario personalizado. |
| `property` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `value` | `character varying(255)` | NO | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 13.3 `theme_log`

**Descripción:** Registro de auditoría de temas: solo se agregan filas, nunca se actualizan (Javadoc de `ThemeLogEntity`).

**Creada en el changeset:** `037-create-theme-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_theme_id` | `bigint` | NO | FK → `user_theme.user_theme_id` | — | PENDIENTE |
| `action` | `character varying(50)` | NO | — | — | PENDIENTE |
| `property` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `old_value` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `new_value` | `character varying(255)` | SÍ | — | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

### 13.4 `user_theme`

**Descripción:** PENDIENTE

**Creada en el changeset:** `035-create-user-theme-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `user_theme_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `integer` | NO | UQ, FK → `app_user.user_id` | — | Usuario al que pertenece el tema. |
| `theme_id` | `integer` | NO | UQ, FK → `theme.theme_id` | — | Tema seleccionado. |
| `is_active` | `boolean` | NO | — | `true` | PENDIENTE |
| `created_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |

<a id="mod-ticket"></a>

## 14. Módulo `ticket`

### 14.1 `order`

**Descripción:** PENDIENTE

**Creada en el changeset:** `064-create-order-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `order_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `total_amount` | `numeric(19,4)` | NO | — | — | PENDIENTE |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'DRAFT'::character varying` | PENDIENTE Valores permitidos (CHECK): `DRAFT`, `PAYMENT_PENDING`, `PAID`, `CANCELLED`, `REFUNDED`, `USED`. |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 14.2 `seat_ticket`

**Descripción:** Relación N:M entre asiento y ticket, con el precio guardado al momento de la compra (Javadoc de `SeatTicketEntity`).

**Creada en el changeset:** `066-create-seat-ticket-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `seat_ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `seat_id` | `integer` | NO | UQ, FK → `seat.seat_id` | — | PENDIENTE |
| `ticket_id` | `bigint` | NO | UQ, FK → `ticket.ticket_id` | — | PENDIENTE |
| `price` | `numeric(19,4)` | NO | — | — | PENDIENTE |

### 14.3 `ticket`

**Descripción:** PENDIENTE

**Creada en el changeset:** `065-create-ticket-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `ticket_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `event_id` | `bigint` | NO | FK → `event.event_id` | — | PENDIENTE |
| `user_id` | `bigint` | NO | FK → `app_user.user_id` | — | PENDIENTE |
| `order_id` | `bigint` | NO | FK → `order.order_id` | — | PENDIENTE |
| `code` | `character varying(50)` | NO | UQ | — | PENDIENTE |
| `qr_code` | `character varying(500)` | NO | — | — | PENDIENTE |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDIENTE Valores permitidos (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `expiration_date` | `timestamp without time zone` | SÍ | — | — | PENDIENTE |
| `total_price` | `numeric(19,4)` | NO | — | — | PENDIENTE |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 14.4 `ticket_checkin`

**Descripción:** PENDIENTE

**Creada en el changeset:** `067-create-ticket-checkin-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `checkin_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id`, UQ | — | PENDIENTE |
| `checkin_time` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `validated_by` | `bigint` | NO | FK → `app_user.user_id` | — | PENDIENTE |

### 14.5 `ticket_log`

**Descripción:** Auditoría inmutable de tickets (Javadoc de `TicketLogEntity`).

**Creada en el changeset:** `068-create-ticket-log-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `ticket_log_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `ticket_id` | `bigint` | NO | FK → `ticket.ticket_id` | — | PENDIENTE |
| `old_status` | `character varying(20)` | SÍ | — | — | PENDIENTE Valores permitidos (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `new_status` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `PENDING`, `PROCESSING`, `PAID`, `REFUNDED`, `USED`, `CANCELLED`. |
| `changed_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `changed_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `reason` | `character varying(255)` | SÍ | — | — | PENDIENTE |

<a id="mod-wallet"></a>

## 15. Módulo `wallet`

### 15.1 `wallet`

**Descripción:** Billetera. Usa bloqueo optimista (`@Version`): si dos transacciones modifican la misma billetera a la vez, la segunda falla (Javadoc de `WalletEntity`).

**Creada en el changeset:** `074-create-wallet-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `wallet_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `user_id` | `bigint` | NO | UQ | — | PENDIENTE |
| `balance` | `numeric(19,4)` | NO | — | `0` | PENDIENTE Restricción CHECK: `CHECK ((balance >= (0)::numeric))`. |
| `currency` | `character varying(3)` | NO | — | `'COP'::character varying` | PENDIENTE Valores permitidos (CHECK): `COP`. |
| `version` | `bigint` | NO | — | `0` | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `updated_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
| `updated_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |

### 15.2 `wallet_reference`

**Descripción:** Referencia de movimientos de billetera. Inmutable: no tiene columnas de auditoría ni versión (Javadoc de `WalletReferenceEntity`).

**Creada en el changeset:** `076-create-wallet-reference-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `wallet_reference_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `transaction_id` | `bigint` | NO | FK → `wallet_transaction.transaction_id` | — | PENDIENTE |
| `entity_type` | `character varying(30)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `EVENT_CANCELLATION`, `ORDER`, `TICKET`, `ADMIN_ADJUSTMENT`. |
| `entity_id` | `bigint` | SÍ | — | — | PENDIENTE |

### 15.3 `wallet_transaction`

**Descripción:** Movimiento de billetera. Inmutable: solo tiene `created_at` y `created_by` (Javadoc de `WalletTransactionEntity`).

**Creada en el changeset:** `075-create-wallet-transaction-table.yaml`

| Columna | Tipo | Nulo | Clave | Valor por defecto | Descripción |
|---|---|---|---|---|---|
| `transaction_id` | `bigint` | NO | PK | `IDENTITY (BY DEFAULT)` | PENDIENTE |
| `wallet_id` | `bigint` | NO | FK → `wallet.wallet_id` | — | PENDIENTE |
| `type` | `character varying(20)` | NO | — | — | PENDIENTE Valores permitidos (CHECK): `CREDIT`, `PAYMENT`, `REVERSAL`, `ADJUSTMENT`. |
| `amount` | `numeric(19,4)` | NO | — | — | PENDIENTE Restricción CHECK: `CHECK ((amount > (0)::numeric))`. |
| `status` | `character varying(20)` | NO | — | `'PENDING'::character varying` | PENDIENTE Valores permitidos (CHECK): `PENDING`, `COMPLETED`, `FAILED`. |
| `balance_after` | `numeric(19,4)` | SÍ | — | — | PENDIENTE |
| `idempotency_key` | `character varying(100)` | NO | UQ | — | PENDIENTE |
| `created_at` | `timestamp without time zone` | NO | — | — | PENDIENTE |
| `created_by` | `character varying(100)` | SÍ | — | — | PENDIENTE |
