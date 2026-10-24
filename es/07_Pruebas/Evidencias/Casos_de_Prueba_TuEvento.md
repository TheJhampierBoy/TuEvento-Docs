---
id: TE-0152
title: "Casos_de_Prueba_TuEvento"
lang: es
source: 06_Pruebas/Casos_de_Prueba_TuEvento.xlsx
source_sha256: 0cdad68243cc439bb95e6f354aa5a25ba754a54a4f111a0028815586c2871737
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
# Casos_de_Prueba_TuEvento

> Conversión de `06_Pruebas/Casos_de_Prueba_TuEvento.xlsx`: 2 hojas (Resumen, Casos de prueba), 102 fórmulas. Las columnas se nombran con la letra de Excel y cada fila con su número original.

## Hoja: Resumen

Rango usado: `A1:H33` · 33 filas × 8 columnas · celdas combinadas: 1

| Fila | A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|---|
| 1 | Resumen de ejecución — Tu Evento |  |  |  |  |  |  |  |
| 2 | Los totales se calculan solos desde la hoja «Casos de prueba». Solo edita las columnas Resultado obtenido, Estado, Fecha, Responsable y Observaciones. El estado se elige de la lista. |  |  |  |  |  |  |  |
| 4 | Módulo | Total | Aprobados | Fallidos | Bloqueados | Pendientes | % Aprobado |  |
| 5 | Autenticación | 32 | 0 | 0 | 0 | 32 | 0.0% |  |
| 6 | Usuarios | 9 | 0 | 0 | 0 | 9 | 0.0% |  |
| 7 | Administración | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 8 | Perfil | 5 | 0 | 0 | 0 | 5 | 0.0% |  |
| 9 | Eventos | 21 | 0 | 0 | 0 | 21 | 0.0% |  |
| 10 | Media y layout | 7 | 0 | 0 | 0 | 7 | 0.0% |  |
| 11 | Ratings y comentarios | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 12 | Categorías y sitios | 7 | 0 | 0 | 0 | 7 | 0.0% |  |
| 13 | Secciones y sillas | 9 | 0 | 0 | 0 | 9 | 0.0% |  |
| 14 | Órdenes y tickets | 12 | 0 | 0 | 0 | 12 | 0.0% |  |
| 15 | Pagos | 16 | 0 | 0 | 0 | 16 | 0.0% |  |
| 16 | Wallet | 5 | 0 | 0 | 0 | 5 | 0.0% |  |
| 17 | Notificaciones | 4 | 0 | 0 | 0 | 4 | 0.0% |  |
| 18 | Temas e idiomas | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 19 | Seguridad y almacenamiento | 6 | 0 | 0 | 0 | 6 | 0.0% |  |
| 20 | TOTAL | 151 | 0 | 0 | 0 | 151 | 0.0% |  |
| 22 | Por tipo de prueba |  |  |  |  |  |  |  |
| 23 | Tipo | Total |  |  |  |  |  |  |
| 24 | Positivo | 42 |  |  |  |  |  |  |
| 25 | Negativo | 66 |  |  |  |  |  |  |
| 26 | Límite | 11 |  |  |  |  |  |  |
| 27 | Seguridad | 22 |  |  |  |  |  |  |
| 28 | Concurrencia | 2 |  |  |  |  |  |  |
| 29 | Integración | 8 |  |  |  |  |  |  |
| 32 | Casos que verifican huecos conocidos (se espera que fallen hoy) |  |  |  |  |  |  |  |
| 33 | Ver la columna Observaciones con el texto «Hueco conocido» en la hoja de casos. |  |  |  |  |  |  |  |

**Celdas combinadas** (el valor aparece solo en la celda superior izquierda): `A2:H2`


**Fórmulas de esta hoja** (celda · fórmula · valor en caché):

| Celda | Fórmula | Valor en caché |
|---|---|---|
| B5 | `=COUNTIF('Casos de prueba'!$B:$B,A5)` | 32 |
| C5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F5 | `=COUNTIFS('Casos de prueba'!$B:$B,$A5,'Casos de prueba'!$L:$L,"Pendiente")` | 32 |
| G5 | `=IF(B5=0,0,C5/B5)` | 0.0% |
| B6 | `=COUNTIF('Casos de prueba'!$B:$B,A6)` | 9 |
| C6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F6 | `=COUNTIFS('Casos de prueba'!$B:$B,$A6,'Casos de prueba'!$L:$L,"Pendiente")` | 9 |
| G6 | `=IF(B6=0,0,C6/B6)` | 0.0% |
| B7 | `=COUNTIF('Casos de prueba'!$B:$B,A7)` | 6 |
| C7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F7 | `=COUNTIFS('Casos de prueba'!$B:$B,$A7,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G7 | `=IF(B7=0,0,C7/B7)` | 0.0% |
| B8 | `=COUNTIF('Casos de prueba'!$B:$B,A8)` | 5 |
| C8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F8 | `=COUNTIFS('Casos de prueba'!$B:$B,$A8,'Casos de prueba'!$L:$L,"Pendiente")` | 5 |
| G8 | `=IF(B8=0,0,C8/B8)` | 0.0% |
| B9 | `=COUNTIF('Casos de prueba'!$B:$B,A9)` | 21 |
| C9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F9 | `=COUNTIFS('Casos de prueba'!$B:$B,$A9,'Casos de prueba'!$L:$L,"Pendiente")` | 21 |
| G9 | `=IF(B9=0,0,C9/B9)` | 0.0% |
| B10 | `=COUNTIF('Casos de prueba'!$B:$B,A10)` | 7 |
| C10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F10 | `=COUNTIFS('Casos de prueba'!$B:$B,$A10,'Casos de prueba'!$L:$L,"Pendiente")` | 7 |
| G10 | `=IF(B10=0,0,C10/B10)` | 0.0% |
| B11 | `=COUNTIF('Casos de prueba'!$B:$B,A11)` | 6 |
| C11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F11 | `=COUNTIFS('Casos de prueba'!$B:$B,$A11,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G11 | `=IF(B11=0,0,C11/B11)` | 0.0% |
| B12 | `=COUNTIF('Casos de prueba'!$B:$B,A12)` | 7 |
| C12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F12 | `=COUNTIFS('Casos de prueba'!$B:$B,$A12,'Casos de prueba'!$L:$L,"Pendiente")` | 7 |
| G12 | `=IF(B12=0,0,C12/B12)` | 0.0% |
| B13 | `=COUNTIF('Casos de prueba'!$B:$B,A13)` | 9 |
| C13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F13 | `=COUNTIFS('Casos de prueba'!$B:$B,$A13,'Casos de prueba'!$L:$L,"Pendiente")` | 9 |
| G13 | `=IF(B13=0,0,C13/B13)` | 0.0% |
| B14 | `=COUNTIF('Casos de prueba'!$B:$B,A14)` | 12 |
| C14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F14 | `=COUNTIFS('Casos de prueba'!$B:$B,$A14,'Casos de prueba'!$L:$L,"Pendiente")` | 12 |
| G14 | `=IF(B14=0,0,C14/B14)` | 0.0% |
| B15 | `=COUNTIF('Casos de prueba'!$B:$B,A15)` | 16 |
| C15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F15 | `=COUNTIFS('Casos de prueba'!$B:$B,$A15,'Casos de prueba'!$L:$L,"Pendiente")` | 16 |
| G15 | `=IF(B15=0,0,C15/B15)` | 0.0% |
| B16 | `=COUNTIF('Casos de prueba'!$B:$B,A16)` | 5 |
| C16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F16 | `=COUNTIFS('Casos de prueba'!$B:$B,$A16,'Casos de prueba'!$L:$L,"Pendiente")` | 5 |
| G16 | `=IF(B16=0,0,C16/B16)` | 0.0% |
| B17 | `=COUNTIF('Casos de prueba'!$B:$B,A17)` | 4 |
| C17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F17 | `=COUNTIFS('Casos de prueba'!$B:$B,$A17,'Casos de prueba'!$L:$L,"Pendiente")` | 4 |
| G17 | `=IF(B17=0,0,C17/B17)` | 0.0% |
| B18 | `=COUNTIF('Casos de prueba'!$B:$B,A18)` | 6 |
| C18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F18 | `=COUNTIFS('Casos de prueba'!$B:$B,$A18,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G18 | `=IF(B18=0,0,C18/B18)` | 0.0% |
| B19 | `=COUNTIF('Casos de prueba'!$B:$B,A19)` | 6 |
| C19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Aprobado")` | 0 |
| D19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Fallido")` | 0 |
| E19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Bloqueado")` | 0 |
| F19 | `=COUNTIFS('Casos de prueba'!$B:$B,$A19,'Casos de prueba'!$L:$L,"Pendiente")` | 6 |
| G19 | `=IF(B19=0,0,C19/B19)` | 0.0% |
| B20 | `=SUM(B5:B19)` | 151 |
| C20 | `=SUM(C5:C19)` | 0 |
| D20 | `=SUM(D5:D19)` | 0 |
| E20 | `=SUM(E5:E19)` | 0 |
| F20 | `=SUM(F5:F19)` | 151 |
| G20 | `=IF(B20=0,0,C20/B20)` | 0.0% |
| B24 | `=COUNTIF('Casos de prueba'!$D:$D,A24)` | 42 |
| B25 | `=COUNTIF('Casos de prueba'!$D:$D,A25)` | 66 |
| B26 | `=COUNTIF('Casos de prueba'!$D:$D,A26)` | 11 |
| B27 | `=COUNTIF('Casos de prueba'!$D:$D,A27)` | 22 |
| B28 | `=COUNTIF('Casos de prueba'!$D:$D,A28)` | 2 |
| B29 | `=COUNTIF('Casos de prueba'!$D:$D,A29)` | 8 |

## Hoja: Casos de prueba

Rango usado: `A1:O152` · 152 filas × 15 columnas · celdas combinadas: 0

| Fila | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | ID | Módulo | Requisito / referencia | Tipo | Prioridad | Descripción | Precondiciones | Pasos | Datos de entrada | Resultado esperado | Resultado obtenido | Estado | Fecha | Responsable | Observaciones |
| 2 | CP-AUT-01 | Autenticación | 3.1 /register | Positivo | Alta | Registro exitoso con Gmail y datos válidos | Correo no registrado | 1. POST /api/v1/auth/register<br>2. Revisar el correo de activación | email: nuevo.usuario@gmail.com<br>password: Clave#2026<br>fullName: Cristofer Lozano | 201. Cuenta creada pendiente de activación y correo con código enviado |  | Pendiente |  |  |  |
| 3 | CP-AUT-02 | Autenticación | 3.1 /register | Negativo | Alta | Registro con correo que no es Gmail | Ninguna | 1. POST /register con correo de otro dominio | email: ana@hotmail.com | 400 INVALID_EMAIL |  | Pendiente |  |  |  |
| 4 | CP-AUT-03 | Autenticación | 4 Cuenta | Negativo | Alta | Registro con contraseña que incumple la política | Ninguna | 1. POST /register con clave sin mayúscula, dígito ni especial | password: clave1234 | 400 INVALID_PASSWORD |  | Pendiente |  |  |  |
| 5 | CP-AUT-04 | Autenticación | 4 Cuenta | Negativo | Media | Registro con nombre de una sola palabra o con números | Ninguna | 1. POST /register con fullName inválido | fullName: Juan / Ju4n P3r3z | 400 INVALID_NAME |  | Pendiente |  |  |  |
| 6 | CP-AUT-05 | Autenticación | 4 Cuenta | Límite | Media | Nombre de 31 caracteres (límite máximo 30) | Ninguna | 1. POST /register con nombre de 31 caracteres | fullName: 31 caracteres alfabéticos en dos palabras | 400 INVALID_NAME. Con 30 caracteres exactos debe aceptarse |  | Pendiente |  |  |  |
| 7 | CP-AUT-06 | Autenticación | 3.1 /register | Negativo | Alta | Registro con correo ya existente | Usuario ya registrado | 1. POST /register con el mismo correo | email existente | 400 EMAIL_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 8 | CP-AUT-07 | Autenticación | 3.1 /activate | Positivo | Alta | Activación de cuenta con código válido | Usuario registrado sin activar | 1. POST /activate con el código del correo<br>2. Iniciar sesión | email + activationCode válido | 200. La cuenta queda activa y el login funciona |  | Pendiente |  |  |  |
| 9 | CP-AUT-08 | Autenticación | 3.1 /activate | Negativo | Alta | Activación con código incorrecto | Usuario registrado sin activar | 1. POST /activate con código errado | activationCode: 000000 | 400 INVALID_ACTIVATION_CODE |  | Pendiente |  |  |  |
| 10 | CP-AUT-09 | Autenticación | 3.1 /activate | Negativo | Media | Activación con código vencido | Código generado y vencido | 1. Esperar el vencimiento<br>2. POST /activate | código vencido | 400 ACTIVATION_CODE_EXPIRED |  | Pendiente |  |  |  |
| 11 | CP-AUT-10 | Autenticación | 3.1 /activate | Negativo | Baja | Activar una cuenta que ya está activa | Cuenta activa | 1. POST /activate | email de cuenta activa | 400 ACCOUNT_ALREADY_ACTIVATED |  | Pendiente |  |  |  |
| 12 | CP-AUT-11 | Autenticación | 3.1 /resend-activation | Negativo | Baja | Reenviar activación a cuenta ya activada | Cuenta activa | 1. POST /resend-activation | email de cuenta activa | 400 EMAIL_ALREADY_ACTIVATED |  | Pendiente |  |  |  |
| 13 | CP-AUT-12 | Autenticación | 3.1 /login | Positivo | Alta | Login exitoso | Cuenta activa | 1. POST /login con credenciales válidas | email + password correctos | 200 con accessToken, refreshToken, userId, alias y role |  | Pendiente |  |  |  |
| 14 | CP-AUT-13 | Autenticación | 3.1 /login | Negativo | Alta | Login con cuenta sin activar | Cuenta registrada sin activar | 1. POST /login | credenciales correctas | 400 ACCOUNT_NOT_ACTIVATED |  | Pendiente |  |  |  |
| 15 | CP-AUT-14 | Autenticación | 3.1 /login | Negativo | Media | Login con correo inexistente | Ninguna | 1. POST /login | email no registrado | 404 USER_NOT_FOUND |  | Pendiente |  |  |  |
| 16 | CP-AUT-15 | Autenticación | 3.1 /login | Negativo | Alta | Login con contraseña incorrecta | Cuenta activa | 1. POST /login con clave errada | password incorrecto | 400 INVALID_CREDENTIALS |  | Pendiente |  |  |  |
| 17 | CP-AUT-16 | Autenticación | 4 Cuenta | Límite | Alta | Bloqueo tras 5 intentos fallidos en 15 minutos | Cuenta activa | 1. Hacer 5 logins fallidos seguidos<br>2. Intentar un sexto login con clave correcta<br>3. Esperar el tiempo de bloqueo<br>4. Reintentar | clave incorrecta x5 | 400 ACCOUNT_LOCKED en el sexto intento. Se desbloquea al vencer el plazo |  | Pendiente |  |  | El bloqueo hoy dura 1 minuto (TODO volver a 30) |
| 18 | CP-AUT-17 | Autenticación | 3.1 /login | Negativo | Media | Login con cuenta bloqueada, desactivada o eliminada | Cuentas en cada estado | 1. POST /login con cada cuenta | credenciales correctas | 400 ACCOUNT_BLOCKED / ACCOUNT_DEACTIVATED / ACCOUNT_DELETED según el caso |  | Pendiente |  |  |  |
| 19 | CP-AUT-18 | Autenticación | 3.1 /refresh | Positivo | Alta | Renovar tokens con refresh token válido | Sesión iniciada | 1. POST /refresh con el refreshToken | refreshToken vigente | 200 con nuevos tokens |  | Pendiente |  |  |  |
| 20 | CP-AUT-19 | Autenticación | 3.1 /refresh | Negativo | Alta | Refresh con token revocado tras logout | Logout realizado | 1. POST /logout<br>2. POST /refresh con el token anterior | refreshToken revocado | 400 REFRESH_TOKEN_REVOKED |  | Pendiente |  |  |  |
| 21 | CP-AUT-20 | Autenticación | 3.1 /refresh | Negativo | Media | Refresh con token vencido | Refresh token con más de 7 días | 1. POST /refresh | refreshToken vencido | 400 REFRESH_TOKEN_EXPIRED |  | Pendiente |  |  |  |
| 22 | CP-AUT-21 | Autenticación | 6 Registro/login | Integración | Media | Logout sincronizado entre pestañas (web) | Dos pestañas con sesión | 1. Cerrar sesión en la pestaña A<br>2. Observar la pestaña B | — | La pestaña B redirige a /login |  | Pendiente |  |  |  |
| 23 | CP-AUT-22 | Autenticación | 6 Registro/login | Integración | Alta | JWT de acceso vencido provoca refresh automático (web) | Sesión con access token de 15 min vencido | 1. Esperar 15 min<br>2. Ejecutar una acción protegida | — | El cliente recibe 401, renueva con refresh y repite la acción sin cerrar sesión. Si el refresh falla, hace logout |  | Pendiente |  |  |  |
| 24 | CP-AUT-23 | Autenticación | 3.1 /recover-password | Seguridad | Alta | Recuperación de contraseña no revela si el correo existe | Un correo registrado y otro no | 1. POST /recover-password con cada correo | email existente / inexistente | 200 con el mismo mensaje genérico en ambos casos |  | Pendiente |  |  |  |
| 25 | CP-AUT-24 | Autenticación | 3.1 /reset-password | Positivo | Alta | Restablecer contraseña con código válido | Código de recuperación recibido | 1. POST /reset-password<br>2. Login con la nueva clave | código + clave nueva y confirmación | 200 y login exitoso con la nueva clave |  | Pendiente |  |  |  |
| 26 | CP-AUT-25 | Autenticación | 3.1 /reset-password | Negativo | Media | Restablecer con código ya usado o vencido | Código usado / vencido | 1. POST /reset-password | código reutilizado o vencido | 400 RECOVERY_CODE_USED / RECOVERY_CODE_EXPIRED |  | Pendiente |  |  |  |
| 27 | CP-AUT-26 | Autenticación | 3.1 /reset-password | Negativo | Media | Restablecer con contraseñas que no coinciden | Código válido | 1. POST /reset-password | nueva ≠ confirmación | 400 PASSWORD_MISMATCH |  | Pendiente |  |  |  |
| 28 | CP-AUT-27 | Autenticación | 3.1 /oauth | Positivo | Media | Login con Google por OAuth2 (web) | Credenciales de Google configuradas | 1. Pulsar «Continuar con Google» en /login<br>2. Autorizar | cuenta Google válida | 302 a /login?oauth=true&token=... y sesión iniciada |  | Pendiente |  |  |  |
| 29 | CP-AUT-28 | Autenticación | 8 Bordes | Seguridad | Alta | Open redirect: frontend_redirect_uri fuera de la lista permitida | Ninguna | 1. GET /oauth/google con frontend_redirect_uri externo | frontend_redirect_uri: https://sitio-malicioso.com | La petición se rechaza. Nunca redirige al dominio externo |  | Pendiente |  |  |  |
| 30 | CP-AUT-29 | Autenticación | 3.1 /google | Negativo | Media | Login con ID token de Google inválido | Ninguna | 1. POST /google con token alterado | token inválido | 400 GOOGLE_TOKEN_INVALID |  | Pendiente |  |  |  |
| 31 | CP-AUT-30 | Autenticación | 6 Registro/login | Positivo | Media | Onboarding cuando el nombre de OAuth no cumple las reglas | Cuenta Google con nombre de una palabra | 1. Login con Google | — | Respuesta needsOnboarding y la web lleva a /complete-profile |  | Pendiente |  |  |  |
| 32 | CP-AUT-31 | Autenticación | 3.1 /reactivate | Positivo | Media | Reactivación de cuenta inactiva | Cuenta INACTIVE | 1. POST /reactivate-request<br>2. POST /reactivate-confirm con el token del correo<br>3. Login | email + token | 200 en ambos pasos y el login vuelve a funcionar |  | Pendiente |  |  |  |
| 33 | CP-AUT-32 | Autenticación | 3.1 /reactivate | Seguridad | Media | Reactivación no permite enumerar usuarios | Un correo registrado y otro no | 1. POST /reactivate-request con cada correo | email existente / inexistente | 200 siempre, con el mismo mensaje |  | Pendiente |  |  |  |
| 34 | CP-USR-01 | Usuarios | 3.2 /change-password | Positivo | Alta | Cambio de contraseña exitoso | Sesión iniciada | 1. POST /users/change-password | actual correcta, nueva válida y confirmación | 200. El login con la nueva clave funciona |  | Pendiente |  |  |  |
| 35 | CP-USR-02 | Usuarios | 3.2 /change-password | Negativo | Alta | Cambio con contraseña actual incorrecta | Sesión iniciada | 1. POST /users/change-password | actual errada | 400 INVALID_CURRENT_PASSWORD |  | Pendiente |  |  |  |
| 36 | CP-USR-03 | Usuarios | 3.2 /change-password | Negativo | Media | Reutilizar una contraseña reciente | Historial de contraseñas | 1. Cambiar a la contraseña anterior | nueva = una de las últimas | 400 PASSWORD_RECENTLY_USED |  | Pendiente |  |  |  |
| 37 | CP-USR-04 | Usuarios | 3.2 /oauth/link | Negativo | Baja | Vincular un proveedor OAuth ya vinculado | Cuenta con Google vinculado | 1. POST /users/oauth/link con el mismo proveedor | provider: google | 400 OAUTH_ALREADY_LINKED |  | Pendiente |  |  |  |
| 38 | CP-USR-05 | Usuarios | 3.2 /organizer-request | Positivo | Alta | Solicitud de organizador con documento PDF | Usuario con rol USER | 1. Abrir /organizer-petition-form<br>2. Adjuntar PDF y enviar | documento .pdf | Petición creada en estado pendiente y visible en GET /organizer-petition |  | Pendiente |  |  |  |
| 39 | CP-USR-06 | Usuarios | 3.2 /organizer-request | Negativo | Media | Solicitud duplicada mientras hay una pendiente | Petición pendiente | 1. POST /organizer-request de nuevo | — | 400 PETITION_ALREADY_PENDING |  | Pendiente |  |  |  |
| 40 | CP-USR-07 | Usuarios | 3.2 /organizer-request | Negativo | Media | Solicitud de un usuario que ya es organizador | Usuario ORGANIZER | 1. POST /organizer-request | — | 400 ALREADY_ORGANIZER |  | Pendiente |  |  |  |
| 41 | CP-USR-08 | Usuarios | 3.2 DELETE /me | Positivo | Media | Desactivar cuenta con contraseña correcta | Sesión iniciada | 1. DELETE /users/me con la contraseña<br>2. Intentar login | password correcta | 200 y el login responde ACCOUNT_DEACTIVATED |  | Pendiente |  |  |  |
| 42 | CP-USR-09 | Usuarios | 3.2 DELETE /me | Negativo | Media | Desactivar cuenta con contraseña incorrecta | Sesión iniciada | 1. DELETE /users/me | password errada | 400 INVALID_PASSWORD y la cuenta sigue activa |  | Pendiente |  |  |  |
| 43 | CP-ADM-01 | Administración | 3.3 organizer-requests | Positivo | Alta | Aprobar petición de organizador | Petición pendiente. Sesión ADMIN | 1. GET /admin/organizer-requests<br>2. PUT /{id}/approve<br>3. El usuario inicia sesión de nuevo | id de petición | 200. El usuario pasa a ORGANIZER |  | Pendiente |  |  |  |
| 44 | CP-ADM-02 | Administración | 3.3 organizer-requests | Positivo | Media | Rechazar petición de organizador | Petición pendiente. Sesión ADMIN | 1. PUT /{id}/reject | id de petición | 200. El usuario sigue como USER |  | Pendiente |  |  |  |
| 45 | CP-ADM-03 | Administración | 3.3 organizer-requests | Negativo | Media | Aprobar o rechazar una petición ya resuelta | Petición ya aprobada | 1. PUT /{id}/approve de nuevo | id resuelto | 400 PETITION_NOT_PENDING |  | Pendiente |  |  |  |
| 46 | CP-ADM-04 | Administración | 3.3 document | Negativo | Baja | Descargar documento de petición inexistente | Sesión ADMIN | 1. GET /organizer-requests/{id}/document | id inexistente | 404 PETITION_NOT_FOUND o FILE_NOT_FOUND |  | Pendiente |  |  |  |
| 47 | CP-ADM-05 | Administración | 5 Roles | Seguridad | Alta | USER intenta usar endpoints de administración | Sesión USER | 1. GET /api/v1/admin/organizer-requests | token de USER | 403 |  | Pendiente |  |  |  |
| 48 | CP-ADM-06 | Administración | 5 Roles | Seguridad | Alta | Endpoint de administración sin token | Ninguna | 1. GET /api/v1/admin/events sin Authorization | — | 401 |  | Pendiente |  |  |  |
| 49 | CP-PRF-01 | Perfil | 3.4 POST / | Positivo | Media | Crear perfil | Usuario sin perfil | 1. POST /profiles | userId, fullName válido | 201 |  | Pendiente |  |  |  |
| 50 | CP-PRF-02 | Perfil | 3.4 POST / | Negativo | Media | Crear perfil duplicado | Usuario con perfil | 1. POST /profiles de nuevo | mismo userId | 409 |  | Pendiente |  |  |  |
| 51 | CP-PRF-03 | Perfil | 8 Bordes | Negativo | Media | Bio con lenguaje inapropiado y leetspeak | Perfil existente | 1. PUT /profiles/{id} con bio ofensiva | bio con palabra prohibida escrita en leetspeak | 400 BIO_INAPPROPRIATE_LANGUAGE |  | Pendiente |  |  |  |
| 52 | CP-PRF-04 | Perfil | 3.4 PUT | Límite | Baja | Bio de 256 caracteres (máximo 255) | Perfil existente | 1. PUT /profiles/{id} | bio: 256 caracteres | 400. Con 255 caracteres debe aceptarse |  | Pendiente |  |  |  |
| 53 | CP-PRF-05 | Perfil | 3.4 GET | Negativo | Baja | Consultar perfil inexistente | Ninguna | 1. GET /profiles/999999 | — | 404 |  | Pendiente |  |  |  |
| 54 | CP-EVT-01 | Eventos | 3.5 POST | Positivo | Alta | Crear evento válido | Sesión ORGANIZER, sitio y categoría activos | 1. POST /events (o wizard /events/create) | eventName, siteId, startDate futura, finishDate ≥ startDate, availableSeats 500, categoryId | 201. Evento en estado DRAFT |  | Pendiente |  |  |  |
| 55 | CP-EVT-02 | Eventos | 4 Evento | Negativo | Alta | Fecha de inicio en el pasado | Sesión ORGANIZER | 1. POST /events | startDate: ayer | 400 EVENT_START_DATE_IN_PAST |  | Pendiente |  |  |  |
| 56 | CP-EVT-03 | Eventos | 4 Evento | Límite | Media | Fecha de inicio a más de 2 años | Sesión ORGANIZER | 1. POST /events | startDate: hoy + 2 años + 1 día | 400 EVENT_START_DATE_TOO_FAR |  | Pendiente |  |  |  |
| 57 | CP-EVT-04 | Eventos | 4 Evento | Negativo | Alta | Fecha de fin anterior al inicio | Sesión ORGANIZER | 1. POST /events | finishDate < startDate | 400 EVENT_END_BEFORE_START |  | Pendiente |  |  |  |
| 58 | CP-EVT-05 | Eventos | 4 Evento | Negativo | Media | Fechas obligatorias ausentes | Sesión ORGANIZER | 1. POST /events sin startDate ni finishDate | — | 400 EVENT_DATES_REQUIRED |  | Pendiente |  |  |  |
| 59 | CP-EVT-06 | Eventos | 4 Evento | Negativo | Media | Evento duplicado (mismo nombre, fecha y sitio) | Evento ya creado | 1. POST /events con los mismos datos | nombre + startDate + siteId iguales | 400 EVENT_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 60 | CP-EVT-07 | Eventos | 4 Evento | Límite | Alta | Aforo en los límites 0, 1, 100000 y 100001 | Sesión ORGANIZER | 1. POST /events variando availableSeats | 0 / 1 / 100000 / 100001 | 0 y 100001 dan 400. 1 y 100000 se aceptan si caben en el sitio |  | Pendiente |  |  |  |
| 61 | CP-EVT-08 | Eventos | 4 Evento | Negativo | Alta | Aforo mayor que la capacidad del sitio | Sitio con capacidad 200 | 1. POST /events | availableSeats: 201 | 400 SEATS_EXCEED_CAPACITY |  | Pendiente |  |  |  |
| 62 | CP-EVT-09 | Eventos | 4 Evento | Negativo | Media | Categoría inactiva o inexistente | Categoría desactivada | 1. POST /events | categoryId inactivo | 400 CATEGORY_NOT_FOUND_OR_INACTIVE |  | Pendiente |  |  |  |
| 63 | CP-EVT-10 | Eventos | 5 Roles | Seguridad | Alta | Organizador edita el evento de otro organizador | Dos organizadores | 1. Iniciar sesión como organizador B<br>2. PUT /events/{id de A} | — | Acceso denegado EVENT_ACCESS_DENIED |  | Pendiente |  |  |  |
| 64 | CP-EVT-11 | Eventos | 4 Evento | Negativo | Alta | Enviar a revisión con menos de 3 o más de 9 imágenes | Evento DRAFT con 2 imágenes | 1. PATCH /events/{id}/status a PENDING_REVIEW<br>2. Repetir con 10 imágenes | 2 y 10 imágenes | 400 EVENT_PUBLISH_MEDIA_COUNT_INVALID |  | Pendiente |  |  |  |
| 65 | CP-EVT-12 | Eventos | 4 Evento | Negativo | Alta | Enviar a revisión sin secciones con sillas | Evento DRAFT con 3 imágenes y sin secciones | 1. PATCH status a PENDING_REVIEW | — | 400 EVENT_SECTIONS_REQUIRED |  | Pendiente |  |  |  |
| 66 | CP-EVT-13 | Eventos | 4 Estados | Positivo | Alta | Flujo completo DRAFT → PENDING_REVIEW → PUBLISHED | Evento con 3–9 imágenes y secciones con sillas | 1. Organizador envía a revisión<br>2. ADMIN publica desde /admin-events<br>3. Abrir /events sin sesión | — | El evento queda PUBLISHED y aparece en el catálogo público |  | Pendiente |  |  |  |
| 67 | CP-EVT-14 | Eventos | 4 Estados | Negativo | Media | Admin rechaza sin motivo | Evento PENDING_REVIEW | 1. PATCH /admin/events/{id}/status newStatus REJECTED sin reason | reason vacío | 400. El motivo es obligatorio al rechazar |  | Pendiente |  |  |  |
| 68 | CP-EVT-15 | Eventos | 4 Estados | Negativo | Alta | Admin intenta publicar desde DRAFT | Evento DRAFT | 1. PATCH /admin/events/{id}/status a PUBLISHED | — | 400 EVENT_INVALID_STATUS_TRANSITION |  | Pendiente |  |  |  |
| 69 | CP-EVT-16 | Eventos | 4 Estados | Negativo | Media | Completar evento antes del día siguiente a finishDate | Evento PUBLISHED que termina hoy | 1. PATCH status a COMPLETED | — | 400 EVENT_COMPLETE_TOO_EARLY |  | Pendiente |  |  |  |
| 70 | CP-EVT-17 | Eventos | 4 Estados | Positivo | Media | Cancelar evento publicado | Evento PUBLISHED con tickets vendidos | 1. PATCH status a CANCELLED | — | Evento CANCELLED. Los tickets no se revierten solos y la UI avisa que el reembolso es aparte |  | Pendiente |  |  |  |
| 71 | CP-EVT-18 | Eventos | 3.5 DELETE | Negativo | Media | Eliminar un evento publicado | Evento PUBLISHED | 1. DELETE /events/{id} | — | 400 EVENT_DELETE_NOT_ALLOWED |  | Pendiente |  |  |  |
| 72 | CP-EVT-19 | Eventos | 3.5 público | Positivo | Media | Filtros públicos por ciudad, categoría y rango de fechas | Eventos publicados | 1. GET /events/public/city/{id}<br>2. GET /public/category/{id}<br>3. GET /public/date-range?from&to | IDs y fechas válidas | 200 con los eventos que cumplen cada filtro |  | Pendiente |  |  |  |
| 73 | CP-EVT-20 | Eventos | 3.5 público | Negativo | Baja | Rango de fechas inválido | Ninguna | 1. GET /events/public/date-range?from=2026-12-31&to=2026-01-01 | from > to | 400 INVALID_DATE_RANGE |  | Pendiente |  |  |  |
| 74 | CP-EVT-21 | Eventos | 3.5 público | Seguridad | Alta | Eventos en DRAFT no aparecen en el catálogo público | Evento DRAFT | 1. GET /events/public | — | El evento DRAFT no está en la lista |  | Pendiente |  |  |  |
| 75 | CP-MED-01 | Media y layout | 3.6 media | Positivo | Alta | Subir imagen válida al evento | Sesión ORGANIZER dueña del evento | 1. POST /events/{id}/media (multipart) | imagen .jpg de 2 MB | 200/201 y la imagen aparece en GET /media |  | Pendiente |  |  |  |
| 76 | CP-MED-02 | Media y layout | 8 Bordes | Negativo | Alta | Imagen rechazada por moderación | Sesión ORGANIZER | 1. POST /events/{id}/media con imagen inapropiada | imagen que activa NSFW o Sightengine | 422 por política de imagen |  | Pendiente |  |  |  |
| 77 | CP-MED-03 | Media y layout | 3.16 Storage | Límite | Media | Archivo mayor al límite de 10 MB | Sesión ORGANIZER | 1. POST media con archivo de 11 MB | archivo de 11 MB | Rechazo por tamaño (FILE_TOO_LARGE o error multipart) |  | Pendiente |  |  |  |
| 78 | CP-MED-04 | Media y layout | 4 Evento | Negativo | Alta | Editar layout con el evento en revisión | Evento PENDING_REVIEW | 1. PUT /events/{id}/layout | — | 400 EVENT_LAYOUT_EDIT_NOT_ALLOWED |  | Pendiente |  |  |  |
| 79 | CP-MED-05 | Media y layout | 4 Evento | Negativo | Alta | Regenerar sillas con reservas o ventas | Evento con sillas RESERVED o SOLD | 1. PUT /events/{id}/layout cambiando secciones | — | 400 SEAT_REGENERATION_CONFLICT |  | Pendiente |  |  |  |
| 80 | CP-MED-06 | Media y layout | 3.6 layout | Seguridad | Alta | PUT de layout por usuario que no es dueño | Evento de otro organizador | 1. PUT /events/{id}/layout | — | Acceso denegado |  | Pendiente |  |  |  |
| 81 | CP-MED-07 | Media y layout | 3.6 layout | Positivo | Media | Editor de layout: crear secciones, bloques y sillas (web) | Evento DRAFT | 1. Abrir /events/:id/layout<br>2. Crear sección con precio<br>3. Generar sillas<br>4. Guardar y recargar | — | El layout persiste y las sillas generadas coinciden con el editor |  | Pendiente |  |  |  |
| 82 | CP-RAT-01 | Ratings y comentarios | 3.6 ratings | Positivo | Media | Calificar y comentar un evento publicado | Usuario USER, evento PUBLISHED público | 1. POST /events/{id}/ratings | rating 4, comentario válido | 201 y se ve en GET /ratings |  | Pendiente |  |  |  |
| 83 | CP-RAT-02 | Ratings y comentarios | 3.6 ratings | Negativo | Media | Segunda calificación numérica del mismo usuario | Usuario ya calificó | 1. POST ratings con otra nota | rating 2 | Solo se acepta como comentario. No se crea una segunda nota |  | Pendiente |  |  |  |
| 84 | CP-RAT-03 | Ratings y comentarios | 3.6 ratings | Negativo | Media | El organizador califica su propio evento | Sesión ORGANIZER dueña | 1. POST ratings con rating | rating 5 | Se rechaza la nota del organizador |  | Pendiente |  |  |  |
| 85 | CP-RAT-04 | Ratings y comentarios | 3.6 ratings | Negativo | Media | Calificar evento que no está publicado o completado | Evento DRAFT o CANCELLED | 1. POST ratings | — | EVENT_RATING_NOT_ALLOWED |  | Pendiente |  |  |  |
| 86 | CP-RAT-05 | Ratings y comentarios | 3.6 ratings | Límite | Baja | Comentario vacío y comentario de 501 caracteres | Evento PUBLISHED | 1. POST ratings con comentario en blanco<br>2. POST con 501 caracteres | — | COMMENT_BLANK y COMMENT_TOO_LONG. Con 500 caracteres se acepta |  | Pendiente |  |  |  |
| 87 | CP-RAT-06 | Ratings y comentarios | 3.6 ratings | Límite | Baja | Antispam: dos comentarios en menos de 10 segundos | Evento PUBLISHED | 1. POST comentario<br>2. POST otro comentario de inmediato | — | COMMENT_RATE_LIMITED en el segundo |  | Pendiente |  |  |  |
| 88 | CP-CAT-01 | Categorías y sitios | 3.7 categorías | Positivo | Media | Admin crea categoría | Sesión ADMIN | 1. POST /categories | nombre nuevo | 201 |  | Pendiente |  |  |  |
| 89 | CP-CAT-02 | Categorías y sitios | 3.7 categorías | Negativo | Media | Categoría con nombre repetido | Categoría existente | 1. POST /categories con el mismo nombre | nombre duplicado | CATEGORY_NAME_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 90 | CP-CAT-03 | Categorías y sitios | 5 Roles | Seguridad | Alta | Organizador intenta crear categoría | Sesión ORGANIZER | 1. POST /categories | — | 403 |  | Pendiente |  |  |  |
| 91 | CP-CAT-04 | Categorías y sitios | 3.8 geolocalización | Positivo | Media | Organizador crea sitio válido | Sesión ORGANIZER, ciudad existente | 1. POST /geolocation/sites | name, address, capacity 500, latitude 2.93, longitude -75.28 | 201 |  | Pendiente |  |  |  |
| 92 | CP-CAT-05 | Categorías y sitios | 3.8 geolocalización | Límite | Media | Sitio con capacidad 0 y coordenadas fuera de rango | Sesión ORGANIZER | 1. POST sitio con capacity 0<br>2. POST con latitude 91<br>3. POST con longitude -181 | capacity 0, lat 91, lon -181 | 400 en cada caso |  | Pendiente |  |  |  |
| 93 | CP-CAT-06 | Categorías y sitios | 3.8 geolocalización | Negativo | Baja | Sitio duplicado | Sitio existente | 1. POST sitio con los mismos datos | — | 409 |  | Pendiente |  |  |  |
| 94 | CP-CAT-07 | Categorías y sitios | 3.8 geolocalización | Positivo | Baja | Búsqueda de sitios cercanos | Sitios con coordenadas | 1. GET sitios cercanos con latitude, longitude y radiusKm | radiusKm: 10 | Lista de sitios dentro del radio |  | Pendiente |  |  |  |
| 95 | CP-SIL-01 | Secciones y sillas | 3.9 secciones | Límite | Media | Sección con capacidad 0 o precio negativo | Evento DRAFT | 1. POST /event-sections con capacidad 0<br>2. POST con precio -1 | — | 400 en ambos. Capacidad 1 y precio 0 se aceptan |  | Pendiente |  |  |  |
| 96 | CP-SIL-02 | Secciones y sillas | 3.9 secciones | Negativo | Baja | Sección duplicada en el mismo evento | Sección existente | 1. POST /event-sections repetida | — | EVENT_SECTION_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 97 | CP-SIL-03 | Secciones y sillas | 3.9 seats | Positivo | Alta | Reservar una silla disponible | Evento PUBLISHED. Usuario autenticado | 1. Seleccionar silla en /events/:id<br>2. POST /seats/{id}/reserve | seatId AVAILABLE | Silla RESERVED por 10 min y el cambio se publica por WebSocket a otros clientes |  | Pendiente |  |  |  |
| 98 | CP-SIL-04 | Secciones y sillas | 3.9 seats | Negativo | Alta | Reservar una silla ya reservada por otro usuario | Silla RESERVED por usuario A | 1. Usuario B hace POST /seats/{id}/reserve | — | SEAT_NOT_AVAILABLE |  | Pendiente |  |  |  |
| 99 | CP-SIL-05 | Secciones y sillas | 3.9 seats | Concurrencia | Alta | Dos usuarios reservan la misma silla al mismo tiempo | Silla AVAILABLE. Dos sesiones | 1. Enviar las dos peticiones de reserva simultáneas | — | Solo una reserva tiene éxito. La otra recibe SEAT_NOT_AVAILABLE. No hay doble reserva |  | Pendiente |  |  |  |
| 100 | CP-SIL-06 | Secciones y sillas | 4 Sillas | Positivo | Alta | La reserva vence a los 10 minutos | Silla RESERVED | 1. Esperar 10 min sin crear la orden | — | La silla vuelve a AVAILABLE y se notifica por WebSocket |  | Pendiente |  |  |  |
| 101 | CP-SIL-07 | Secciones y sillas | 3.9 seats | Negativo | Media | Liberar silla ajena, no reservada o propia | Sillas en distintos estados | 1. POST /seats/{id}/release en cada caso | — | Propia: éxito. Ajena: UNAUTHORIZED_RELEASE. No reservada: SEAT_NOT_RESERVED |  | Pendiente |  |  |  |
| 102 | CP-SIL-08 | Secciones y sillas | 3.9 seats | Negativo | Baja | Cambio de estado idéntico y código de silla duplicado | Organizador del evento | 1. PATCH /seats con el mismo estado<br>2. POST /seats con código repetido | — | SEAT_STATUS_UNCHANGED y SEAT_CODE_ALREADY_EXISTS |  | Pendiente |  |  |  |
| 103 | CP-SIL-09 | Secciones y sillas | 3.9 WebSocket | Seguridad | Media | Handshake WebSocket sin JWT | Ninguna | 1. Conectar a /ws sin token | — | La conexión se rechaza |  | Pendiente |  |  |  |
| 104 | CP-ORD-01 | Órdenes y tickets | 3.10 /orders | Positivo | Alta | Crear orden con sillas reservadas | Usuario con sillas RESERVED vigentes | 1. POST /orders | eventId, seatIds [1,2] | Orden DRAFT, tickets PENDING con QR. Total = suma de precios de sección |  | Pendiente |  |  |  |
| 105 | CP-ORD-02 | Órdenes y tickets | 3.10 /orders | Negativo | Alta | Orden con una silla no reservada por el usuario | Silla reservada por otro | 1. POST /orders | seatIds con silla ajena | 400 |  | Pendiente |  |  |  |
| 106 | CP-ORD-03 | Órdenes y tickets | 3.10 /orders | Negativo | Alta | Orden con reserva vencida | Reserva de más de 10 min | 1. POST /orders | seatIds vencidos | 400 |  | Pendiente |  |  |  |
| 107 | CP-ORD-04 | Órdenes y tickets | 3.10 /orders | Negativo | Media | Orden sin sillas | Sesión iniciada | 1. POST /orders con seatIds vacío | seatIds: [] | 400 por validación (mínimo 1) |  | Pendiente |  |  |  |
| 108 | CP-ORD-05 | Órdenes y tickets | 3.10 cancel | Positivo | Alta | Cancelar orden en DRAFT o PAYMENT_PENDING | Orden DRAFT | 1. POST /orders/{id}/cancel | — | Orden CANCELLED, tickets CANCELLED y sillas AVAILABLE |  | Pendiente |  |  |  |
| 109 | CP-ORD-06 | Órdenes y tickets | 4 Órdenes | Negativo | Alta | Cancelar una orden ya pagada | Orden PAID | 1. POST /orders/{id}/cancel | — | 409 |  | Pendiente |  |  |  |
| 110 | CP-ORD-07 | Órdenes y tickets | 8 Huecos | Seguridad | Alta | Cancelar la orden de otro usuario | Orden del usuario A. Sesión del usuario B | 1. Usuario B hace POST /orders/{id de A}/cancel | — | Debería rechazarse (403) |  | Pendiente |  |  | Hueco conocido: hoy no se comprueba el dueño. Si se ejecuta la cancelación, registrar defecto |
| 111 | CP-ORD-08 | Órdenes y tickets | 8 Huecos | Seguridad | Alta | Consultar tickets de otro usuario por userId | Dos usuarios con tickets | 1. Usuario B hace GET /tickets/user/{id de A} | — | Debería rechazarse (403) |  | Pendiente |  |  | Hueco conocido: no se verifica que sea el mismo usuario |
| 112 | CP-ORD-09 | Órdenes y tickets | 3.10 checkin | Positivo | Alta | Check-in de un ticket pagado | Ticket PAID, no expirado | 1. POST /tickets/{id}/checkin | validatedBy: nombre del validador | 200. Ticket USED y registro en ticket_checkin |  | Pendiente |  |  |  |
| 113 | CP-ORD-10 | Órdenes y tickets | 3.10 checkin | Negativo | Alta | Check-in repetido del mismo ticket | Ticket USED | 1. POST /tickets/{id}/checkin otra vez | — | 400 por ticket ya usado |  | Pendiente |  |  |  |
| 114 | CP-ORD-11 | Órdenes y tickets | 3.10 checkin | Negativo | Alta | Check-in de ticket no pagado o expirado | Ticket PENDING / expirado | 1. POST /tickets/{id}/checkin | — | 400 |  | Pendiente |  |  |  |
| 115 | CP-ORD-12 | Órdenes y tickets | 8 Huecos | Seguridad | Alta | Check-in realizado por un usuario sin rol de organizador | Ticket PAID. Sesión USER | 1. POST /tickets/{id}/checkin con token de USER | — | Debería denegarse |  | Pendiente |  |  | Hueco conocido: no hay @PreAuthorize ni rol staff. Probar solo por API (no hay escáner QR) |
| 116 | CP-PAG-01 | Pagos | 3.11 /payments | Positivo | Alta | Crear pago por QR sin wallet | Orden DRAFT | 1. POST /payments con orderId y paymentMethod QR | applyWalletCredit: false | 201 (sin sobre ApiResponse). Pago PENDING y orden PAYMENT_PENDING |  | Pendiente |  |  |  |
| 117 | CP-PAG-02 | Pagos | 3.11 webhook | Integración | Alta | Webhook de pago aprobado | Pago PENDING en pasarela sandbox | 1. Aprobar el pago en la pasarela sandbox (puerto 4001)<br>2. Verificar orden, tickets y sillas | firma HMAC válida | Pago APPROVED, orden PAID, tickets PAID y sillas SOLD |  | Pendiente |  |  |  |
| 118 | CP-PAG-03 | Pagos | 3.11 webhook | Integración | Alta | Webhook de pago rechazado | Pago PENDING | 1. Rechazar el pago en la pasarela sandbox<br>2. Verificar estados | firma HMAC válida | Pago REJECTED. Sillas AVAILABLE, tickets y orden cancelados |  | Pendiente |  |  |  |
| 119 | CP-PAG-04 | Pagos | 3.11 webhook | Seguridad | Alta | Webhook con firma HMAC inválida | Ninguna | 1. POST /webhooks/payment con X-Signature alterada | firma incorrecta | 401 y ningún cambio de estado |  | Pendiente |  |  |  |
| 120 | CP-PAG-05 | Pagos | 8 Bordes | Concurrencia | Alta | Webhook duplicado (mismo gateway_event_id) | Webhook ya procesado | 1. Reenviar el mismo webhook | mismo eventId | 200 sin efecto doble (idempotente) |  | Pendiente |  |  |  |
| 121 | CP-PAG-06 | Pagos | 4 Estados | Negativo | Media | Pago de una orden que ya no está en DRAFT | Orden PAID o CANCELLED | 1. POST /payments | orderId de orden cerrada | 409 por transición inválida |  | Pendiente |  |  |  |
| 122 | CP-PAG-07 | Pagos | 8 Bordes | Integración | Alta | Pasarela caída al crear el pago | Pasarela sandbox apagada | 1. Apagar la pasarela<br>2. POST /payments con applyWalletCredit true | — | Error controlado. No queda reserva de wallet huérfana ni orden colgada (rollback) |  | Pendiente |  |  |  |
| 123 | CP-PAG-08 | Pagos | 4 Wallet | Positivo | Alta | Pago 100% con wallet | Saldo ≥ total de la orden | 1. POST /payments con applyWalletCredit true | — | APPROVED de inmediato, amount 0, walletAmountApplied = total y gatewayTransactionId con prefijo wallet_only_ |  | Pendiente |  |  |  |
| 124 | CP-PAG-09 | Pagos | 4 Wallet | Positivo | Alta | Pago mixto (wallet + pasarela) | Saldo menor al total | 1. POST /payments con applyWalletCredit true<br>2. Aprobar en la pasarela | — | Wallet reservada y luego descontada. La pasarela cobra solo la diferencia |  | Pendiente |  |  |  |
| 125 | CP-PAG-10 | Pagos | 4 Wallet | Positivo | Alta | Pago mixto rechazado libera el saldo | Pago mixto en curso | 1. Rechazar en la pasarela<br>2. Consultar GET /wallet/me | — | El saldo reservado vuelve a estar disponible |  | Pendiente |  |  |  |
| 126 | CP-PAG-11 | Pagos | 3.11 refund | Integración | Alta | Reembolso de pago por pasarela (ADMIN) | Pago APPROVED | 1. POST /payments/{id}/refund con motivo<br>2. Esperar webhook payment.refunded | reason: Evento cancelado | Pago, orden y tickets REFUNDED. Las sillas se mantienen SOLD según lo definido |  | Pendiente |  |  |  |
| 127 | CP-PAG-12 | Pagos | 4 Wallet | Positivo | Alta | Reembolso de pago solo wallet | Pago wallet_only APPROVED | 1. POST /payments/{id}/refund | reason válido | Cierre local. Pago, orden y tickets REFUNDED y saldo devuelto a la wallet |  | Pendiente |  |  |  |
| 128 | CP-PAG-13 | Pagos | 3.11 refund | Límite | Media | Reembolso sin motivo o con motivo de 501 caracteres | Pago APPROVED | 1. POST refund con reason vacío<br>2. POST con 501 caracteres | — | 400 en ambos. Con 500 caracteres se acepta |  | Pendiente |  |  |  |
| 129 | CP-PAG-14 | Pagos | 5 Roles | Seguridad | Alta | USER intenta reembolsar | Sesión USER | 1. POST /payments/{id}/refund | — | 403 |  | Pendiente |  |  |  |
| 130 | CP-PAG-15 | Pagos | 4 Estados | Negativo | Media | Reembolso de un pago que no está APPROVED | Pago PENDING | 1. POST /payments/{id}/refund | — | Rechazado. Solo se reembolsa un pago APPROVED |  | Pendiente |  |  |  |
| 131 | CP-PAG-16 | Pagos | 3.11 UI | Positivo | Media | Pantallas de checkout, pago pendiente y confirmado (web) | Orden creada | 1. Ir a /checkout<br>2. Pagar<br>3. Esperar /checkout/pending/:id hasta /checkout/confirmed/:id | — | La UI cambia de pendiente a confirmado al llegar el webhook |  | Pendiente |  |  |  |
| 132 | CP-WAL-01 | Wallet | 3.12 /wallet/me | Positivo | Media | Consultar wallet y movimientos propios | Usuario con wallet | 1. GET /wallet/me<br>2. GET /wallet/me/transactions | — | 200 con saldo y movimientos del dueño |  | Pendiente |  |  |  |
| 133 | CP-WAL-02 | Wallet | 3.12 /wallet/me | Negativo | Baja | Consultar wallet de un usuario sin wallet | Usuario sin wallet | 1. GET /wallet/me | — | 404 |  | Pendiente |  |  |  |
| 134 | CP-WAL-03 | Wallet | 3.12 /credit | Positivo | Media | Admin acredita saldo | Sesión ADMIN | 1. POST /wallet/credit | userId, monto | 200 y el saldo aumenta |  | Pendiente |  |  |  |
| 135 | CP-WAL-04 | Wallet | 5 Roles | Seguridad | Alta | Usuario común intenta acreditar o ajustar wallet | Sesión USER | 1. POST /wallet/credit<br>2. POST /wallet/adjust | — | 403 en ambos |  | Pendiente |  |  |  |
| 136 | CP-WAL-05 | Wallet | 3.12 /adjust | Negativo | Alta | Ajuste negativo mayor al saldo | Saldo 10.000 | 1. POST /wallet/adjust con -20.000 | monto: -20000 | 422 InsufficientWalletBalance. El saldo nunca queda negativo |  | Pendiente |  |  |  |
| 137 | CP-NOT-01 | Notificaciones | 3.13 | Positivo | Media | Listar notificaciones con paginación y solo no leídas | Usuario con notificaciones | 1. GET /notifications/me?page=0&size=20<br>2. GET con unreadOnly=true | — | 200 paginado y filtrado |  | Pendiente |  |  |  |
| 138 | CP-NOT-02 | Notificaciones | 3.13 | Positivo | Media | Marcar una y todas como leídas | Notificaciones sin leer | 1. PATCH /{id}/read<br>2. PATCH /me/read-all<br>3. GET /me/unread-count | — | El contador baja a 0 al final |  | Pendiente |  |  |  |
| 139 | CP-NOT-03 | Notificaciones | 7 Integraciones | Integración | Media | Notificación por correo en un evento de negocio | SMTP configurado | 1. Ejecutar un pago aprobado o una activación<br>2. Revisar la bandeja | — | Llega el correo y se crea la notificación in-app |  | Pendiente |  |  |  |
| 140 | CP-NOT-04 | Notificaciones | 3.13 | Seguridad | Alta | Un usuario no ve notificaciones de otro | Dos usuarios | 1. Marcar como leída con un notificationUserId ajeno | id de otro usuario | Rechazado o 404. Solo se opera sobre las propias |  | Pendiente |  |  |  |
| 141 | CP-TEM-01 | Temas e idiomas | 3.14 temas | Positivo | Baja | Activar, personalizar y restablecer un tema | Sesión iniciada | 1. POST activate de un tema<br>2. PUT customize<br>3. DELETE customize/{property} | tema dark | Se aplica, se personaliza y se revierte la propiedad |  | Pendiente |  |  |  |
| 142 | CP-TEM-02 | Temas e idiomas | 3.15 idiomas | Positivo | Baja | Solo se listan idiomas activos al público | Idiomas activos e inactivos | 1. GET /languages sin sesión | — | Solo idiomas activos |  | Pendiente |  |  |  |
| 143 | CP-TEM-03 | Temas e idiomas | 3.15 idiomas | Negativo | Media | Crear idioma con código existente | Idioma existente | 1. POST idioma con código repetido | code: es | LANGUAGE_CODE_EXISTS |  | Pendiente |  |  |  |
| 144 | CP-TEM-04 | Temas e idiomas | 3.15 idiomas | Negativo | Media | Desactivar el idioma por defecto | Idioma por defecto definido | 1. Desactivar el idioma por defecto | — | CANNOT_DEACTIVATE_DEFAULT_LANGUAGE |  | Pendiente |  |  |  |
| 145 | CP-TEM-05 | Temas e idiomas | 3.15 traducción | Positivo | Media | Solicitar traducción asíncrona (ADMIN) | LibreTranslate arriba. Sesión ADMIN | 1. POST /api/admin/translations/request<br>2. Consultar el job de la entidad | entityType, entityId, sourceLanguageCode | Job creado y traducción completada. Marcas y nombres propios no se traducen |  | Pendiente |  |  | El listado global de jobs pending devuelve vacío (TODO conocido) |
| 146 | CP-TEM-06 | Temas e idiomas | 5 Roles | Seguridad | Media | USER intenta solicitar traducciones | Sesión USER | 1. POST /api/admin/translations/request | — | 403 |  | Pendiente |  |  |  |
| 147 | CP-SEG-01 | Seguridad y almacenamiento | 3.16 Storage | Negativo | Media | Subida con extensión no permitida | Sesión iniciada | 1. POST /storage/upload con un .exe | archivo .exe | 400 INVALID_FILE_EXTENSION |  | Pendiente |  |  |  |
| 148 | CP-SEG-02 | Seguridad y almacenamiento | 8 Huecos | Seguridad | Alta | Subida a storage sin autenticación | Ninguna | 1. POST /storage/upload sin Authorization | — | Debería devolver 401 |  | Pendiente |  |  | Hueco conocido: la ruta está en permitAll |
| 149 | CP-SEG-03 | Seguridad y almacenamiento | 8 Huecos | Seguridad | Alta | Endpoint de desarrollo de código de activación | Entorno de producción | 1. GET /auth/dev/activate-code/{email} | email registrado | Debe estar deshabilitado (404 o 403) |  | Pendiente |  |  | Hueco conocido: existe solo para pruebas |
| 150 | CP-SEG-04 | Seguridad y almacenamiento | 7 Integraciones | Seguridad | Media | Exposición de Actuator y Swagger | Entorno de producción | 1. GET /actuator<br>2. GET /swagger-ui | — | No deben exponer información sensible sin autenticación |  | Pendiente |  |  | Hoy Actuator es público |
| 151 | CP-SEG-05 | Seguridad y almacenamiento | 5 Roles | Seguridad | Alta | Rutas protegidas del frontend según rol | Sesión USER | 1. Abrir /admin-panel y /events/create manualmente | — | ProtectedRoute redirige. El backend responde 403 al llamar la API |  | Pendiente |  |  |  |
| 152 | CP-SEG-06 | Seguridad y almacenamiento | 9 Pendiente | Integración | Media | Cobertura móvil: flujo de compra | App Expo, sesión iniciada | 1. Login<br>2. Detalle de evento<br>3. Checkout<br>4. PaymentPending | — | El flujo móvil completa la compra igual que la web |  | Pendiente |  |  |  |

**Configuración de la hoja**:

- Paneles inmovilizados en `C2`.
- Autofiltro en `A1:O152`.
- Validación de datos (list) en `L2:L152`: `"Pendiente,Aprobado,Fallido,Bloqueado"`.
- Formato condicional en `L2:L152`: tipo `cellIs`, operador `equal`, fórmula `"Aprobado"` (el estilo aplicado no se reproduce).
- Formato condicional en `L2:L152`: tipo `cellIs`, operador `equal`, fórmula `"Fallido"` (el estilo aplicado no se reproduce).
- Formato condicional en `L2:L152`: tipo `cellIs`, operador `equal`, fórmula `"Bloqueado"` (el estilo aplicado no se reproduce).

