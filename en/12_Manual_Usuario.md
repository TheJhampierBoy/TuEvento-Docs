---
title: "User manual"
lang: en
documents: [TE-0158, TE-0159]
status: borrador
---
# User manual — Tu Evento

> Consolidated Tu Evento document. It gathers the following documents, whose content is kept unchanged; the conversion metadata of each one is in an HTML comment at the start of its section.

**Contents**

1. [User manual — web](#doc-te-0158)
2. [User manual — mobile app and installation](#doc-te-0159)

---

<a id="doc-te-0158"></a>

<!--
ruta_anterior: en/09_Manuales/Manual_de_usuario/Manual_web.md
id: TE-0158
title: "Manual (web)"
lang: en
source: 09_Manuales/Manual de usuario/Manual (web).docx
source_sha256: 8522404d169774cdf8be50d77857b91e52ab77242a69e4a84706fb94bd793671
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the interface texts and messages in quotation marks are translated and the Spanish literal is added in parentheses («…»), because the real English text of the interface is not known."
  - "Translation: the anchors of the table of contents links are translated so that they point to the English headings; «#section» is kept as in the Spanish version."
  - "Translation: the text inside the screenshots and the alternative texts that are image names (login, login-3, maquetacion-1, eventos-1, categoria, erro pdf) are not translated."
status: borrador
reviewed_by: ""
translation_of: es/12_Manual_Usuario.md#doc-te-0158
es_sha256: 7cacc898b0ed43a35fbf4c679ff58b3ab5479b4af89bbce85457273a8c1bd446
-->

# User manual — web

**Web Manual**

Lozano Contreras Cristofer David

Santos Ortiz Jhampier

Análisis y Desarrollo de Software (Software Analysis and Development)

\(3145556\)

Servicio Nacional de Aprendizaje (National Learning Service)

October 1, 2025

# **Contents**

[Web User [5](#web-user)](#web-user)

[Organizer User [22](#section)](#section)

[Administrator User [23](#administrator-user)](#administrator-user)

**Introduction**

The purpose of this user manual is to describe clearly and in detail the main features of the "Tu Evento" web application, developed by CapySoft. This version is designed as a comprehensive platform that allows the different types of users (attendees, organizers and administrator) to interact with events simply and efficiently from web browsers such as Google Chrome and Microsoft Edge.

Unlike the mobile application, the web version incorporates a broader set of features that allow not only the participation of attendees in events, but also their management and supervision by organizers and administrators.

In the web version:

1.  The attendee user can create an account, log in, manage their profile, view and filter events, register for them and participate through comments.

2.  The organizer has advanced tools to create, edit, publish and delete events, as well as to carry out the layout design of spaces and control their distribution.

3.  The administrator has the capacity to supervise the platform, manage users and, specifically, accept or deny registration requests to become an organizer, thus ensuring transparency and the correct use of the system.

# Web User

1.  **Main interface**

When opening the "Tu Evento" website, the user will be taken to a home landing page, which presents the main options of the platform clearly and attractively. On this initial screen, highlighted sections are shown, such as:

- **About us (Nosotros):** Information about the platform and its purpose.

- **Create (Crear):** Dynamic option that varies according to the user's status:

1.  If the user has not logged in, they will be redirected to the Create account option.

2.  If the user has logged in, but is not yet registered as an organizer, they will be taken to the company registration form (RUT or other required data).

3.  If the user is already registered as an organizer, they will be taken to the event creation and management section.

- **Events (Eventos):** It allows viewing the events available on the platform.

- **Log In (Iniciar Sesión):** To access with previously registered credentials.

> <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image2.png" style="width:6.5in;height:3.51528in" />

- **Login interface:**

The login interface offers users secure and flexible access to the platform, allowing them to enter through the traditional method with email and password, create a new account if not registered, recover the password if forgotten, or log in more quickly through the credentials of linked social networks, thus providing several authentication alternatives according to the user's preference.

> <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image3.png" style="width:6.5in;height:3.24375in" />

.

- **Create an account through social networks**

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image4.png" style="width:3.65972in;height:3.60417in" /><img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image5.png" style="width:4.36458in;height:3.32708in" />The “Tu Evento” web application offers the option of logging in through social networks, allowing users to access quickly and easily using their credentials from external platforms such as Google or Facebook. This feature avoids the need to create a new password within the system, making it possible to enter with a single click and maintaining security thanks to the direct validation carried out by each social network. In this way, users have a practical alternative to the traditional login with email and password, speeding up access to the platform.

- **Account creation in the traditional way:**

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image6.png" style="width:6.1875in;height:3.26042in" />The create account option allows new users to register on the platform through a simple form, in which they must enter basic data such as full name, email and a secure password. Once the registration is completed, the system sends a verification code to the email provided, which must be entered to validate and activate the account. In this way, it is guaranteed that only users with valid emails can access the system, providing greater security and reliability in the registration process.

> <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image7.png" style="width:6.19792in;height:2.89514in" />
>
> <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image8.png" style="width:3.55208in;height:3.15764in" />

# 

# 

# 

# 

# 

# 

- **Recover password:**

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image9.png" style="width:5.66597in;height:2.57292in" />The recover password option allows users to restore access to their account if they forget it. To do this, they must enter the registered email, after which the system sends a verification code to it. Once the code has been validated, the form to define a new password is enabled; the new password immediately replaces the previous one and will be the only valid one for future logins, thus guaranteeing secure and controlled access to the platform.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image10.png" style="width:5.28125in;height:2.79167in" />

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image11.png" style="width:3.41736in;height:3.34444in" />

# Login:

Login allows users to access the platform using the previously registered credentials, made up of their email and password. Once the data has been validated, the system redirects the user to the corresponding interface according to their role, whether attendee, organizer or administrator, ensuring that each profile has only the features that correspond to it. In case of an error in the credentials, the system shows a warning message and invites the user to try again or use the password recovery option.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image12.png" style="width:6.5in;height:3.15139in" />

- **Request to become an organizer:**

The request to become an organizer option allows a registered user to request the organizer role within the platform. To do this, they must complete a form in which the company's RUT is requested; once the request is sent, it remains pending review by the administrator, who will have the power to accept or reject it. If it is approved, the user acquires the organizer role and accesses the exclusive features for creating, editing and managing events.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image13.png" style="width:6.5in;height:3.29097in" />

- **Viewing events:**

The event viewing feature allows users to explore all the events available on the platform easily. This section shows basic details such as the name of the event, date, location, description and available places, which makes it easier for the attendee to identify those of interest.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image14.png" style="width:6.5in;height:2.48056in" />

# Organizer User

- **Manage events:**

The event management function allows the user with the organizer role to control their events within the platform comprehensively. Through this feature, the organizer can create new events, design the layout of the venue structure, and publish the events so that they are visible to users.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image15.png" style="width:6.5in;height:3.05347in" /><img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image16.png" style="width:6.5in;height:2.72014in" />

# Administrator User

The user administration section is intended for the administrator of the platform and allows supervising and managing all the registered users. From this feature, the administrator can view the basic information of each user, their role within the system (attendee, organizer or administrator), as well as the status of their account. In addition, they have the capacity to approve or reject organizer requests, assign or revoke permissions and, when necessary, suspend or delete users. In this way, adequate control of the community and the correct operation of the platform are guaranteed.

<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image17.png" style="width:6.5in;height:2.75625in" />

# System errors

1.  During the login process, the system may show validation messages when the data entered does not meet the established requirements. These errors help to guarantee that the user's information is correct and secure before allowing access to the platform.<img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image18.png" style="width:6.48889in;height:2.90417in" alt="login" />

### Error Description – Login

Screen: System login\
Location: User authentication form\
Type of error: Input data validation

#### Description

When trying to log in, an error message is shown below the email field that indicates:

> “We only support Gmail emails” («Solo tenemos soporte para correos de Gmail»)

This happens because the user entered an email address that does not belong to the Gmail domain, in this case: aaaaa@hotmal.com.

In addition, the system shows a second validation message below the password field:

> “The password must have at least 8 characters” («La contraseña debe tener al menos 8 caracteres»)

This means that the password entered does not meet the minimum length required by the platform.

#### Cause of the error

> The system is configured to accept only email addresses with the @gmail.com domain.
>
> The password entered contains fewer than 8 characters, which does not comply with the established security policies.

####  Recommended solution

> Verify that the email entered has a valid format and belongs to the allowed domain (@gmail.com).\
> Correct example: usuario@gmail.com
>
> Make sure that the password contains at least 8 characters, combining letters, numbers and symbols if possible.

2.  During the password recovery process, the system validates that the email entered exists in the database. If the address is not registered or contains spelling errors, a warning message will be shown to avoid sending instructions to an invalid email.

### Error Description – Password Recovery

Screen: Forgot my password\
Location: Access recovery form\
Type of error: User validation

####  Description

When trying to recover the password, the system shows the following message below the email field:

> “User not found” («Usuario no encontrado»)

This happens because the email address entered does not match any user registered on the platform or has a typographical error.\
In this case, the email entered is: aaaaaaaaaaaa@hotmaail.com, which contains an error in the domain (hotmaail.com instead of hotmail.com).

####  Cause of the error

> The email entered does not exist in the database of registered users.
>
> The email has spelling errors or does not follow the correct format.

####  Recommended solution

> Verify that the email is correctly written and belongs to a registered user.\
> Correct example: usuario@hotmail.com or usuario@gmail.com
>
> If the email is correct and the error is still shown, contact technical support to verify the registration of the account.

3.  During the registration process, the system validates the data entered to guarantee that the new user's information meets the format, security and compatibility requirements. If any of the fields do not comply with the established rules, error messages are shown that indicate the type of correction needed before continuing with the registration.

    <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image19.png" style="width:6.49861in;height:3.09306in" alt="login-3" />

### Error Description – User Registration

Screen: New user registration\
Location: Account creation form\
Type of error: Input data validation

####  Description

When trying to register, the system shows several validation messages:

> Below the name field, the message appears:
>
> “Please enter first name and last name” («Por favor ingresa nombre y apellido»)\
> This indicates that the field only contains a first name and the system requires the complete first name and last name.
>
> Below the email field, the message appears:
>
> “We only support Gmail emails” («Solo tenemos soporte para correos de Gmail»)\
> This is because the address entered (aaaaa@hotmal.com) does not belong to the Gmail domain and also has a typographical error (“hotmal” instead of “hotmail”).
>
> Below the password field, the system shows:
>
> “The password must have at least 8 characters” («La contraseña debe tener al menos 8 caracteres»)\
> This means that the password entered does not meet the minimum length required by the security policies.

####  Cause of the error

> The name field is incomplete (the last name is missing).
>
> The email does not belong to the allowed domain (@gmail.com) or has a spelling error.
>
> The password contains fewer than 8 characters.

#### Recommended solution

> Enter the complete first name and last name, for example: Ana López.
>
> Verify that the email is valid and ends in @gmail.com.\
> Correct example: usuario@gmail.com
>
> Set a password of at least 8 characters, combining letters, numbers and symbols for greater security.

4.  During the management and publication of events, the system validates that all the steps prior to the launch have been correctly completed. Among them is the layout design of the event, which defines the visual structure and the elements that will be shown to the public. If this step has not been carried out, the system prevents publication to avoid display errors or incomplete information.

    <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image20.png" style="width:6.48889in;height:3.07222in" alt="maquetacion-1" />

### Error Description – Event Publication

Screen: Event Management\
Location: “My Events” («Mis Eventos») section\
Type of error: Validation prior to publication

#### Description

When trying to publish an event from the management dashboard, a pop-up window appears with the following error message:

> “Error publishing the event: The event must have a layout design before being published.” («Error al publicar el evento: El evento debe tener una maquetación antes de publicarse.»)

This message indicates that the selected event does not have an assigned or completed layout design, so the system blocks its publication until this requirement is met.

#### Cause of the error

> The event does not have a created or saved layout design.
>
> The layout design process was not completed correctly or was not linked to the current event.

#### Recommended solution

> Click the “Layout design” («Maquetación») button corresponding to the event.
>
> Complete the design process or visual structure of the event.
>
> Save the changes and verify that the status of the event indicates that it is “Ready to publish” («Listo para publicar»)
>
> Once completed, try the publication again.

5.  During the process of creating an event, the system validates that the basic information entered meets the minimum requirements of length and date consistency. This guarantees that the events created are clear, complete and correctly configured before moving on to the next stages of the registration.

    <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image21.png" style="width:6.48611in;height:3.27361in" alt="eventos-1" />

###  Error Description – Event Creation

Screen: Event creation – Step 1 (Basic information)\
Location: Event registration form\
Type of error: Validation of mandatory fields

####  Description

When trying to advance to the next step of the form, the system shows several validation messages in red.

> Field “Event Name” («Nombre del Evento»)
>
> “The event name must have at least 3 characters” («El nombre del evento debe tener al menos 3 caracteres»)\
> This indicates that the name entered (a) does not meet the minimum length required to be valid.
>
> Field “Description” («Descripción»)
>
> “The event description must have at least 10 characters” («La descripción del evento debe tener al menos 10 caracteres»)\
> The text entered (a) is too short and does not provide enough information about the event.
>
> Fields “Start Date” («Fecha de Inicio») and “End Date” («Fecha de Fin»)
>
> “The start date cannot be earlier than today” («La fecha de inicio no puede ser anterior a hoy»)\
> In addition, the selected dates (30/09/2025 and 29/09/2025) are invalid, since the end date is earlier than the start date, which is not allowed.

#### Cause of the error

> The event name does not meet the minimum length of 3 characters.The description is shorter than 10 characters.
>
> The dates entered are incorrect or inconsistent (the end date cannot be before the start date).

#### Recommended solution

> Write a clear and descriptive event name (minimum 3 characters).\
> Example: Festival de Música.
>
> Write a complete description that explains the purpose or details of the event (minimum 10 characters).\
> Example: Concierto de bandas locales en el centro de la ciudad.
>
> Make sure that the start date is equal to or later than the current day, and that the end date is later than the start date.

6.  In the final stage of creating an event, the system requires the user to select a main category and a subcategory that correctly describe the type of event. These categories make it possible to classify the events appropriately and make them easier to find within the platform.

    <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image22.png" style="width:6.48889in;height:2.78125in" alt="categoria" />

### Error Description – Category Selection

Screen: Event creation – Step 2 (Category selection)\
Location: Category and subcategory selection form\
Type of error: Validation of mandatory fields

#### Description

When trying to click the “Create Event” («Crear Evento») button without having selected a category, the system shows a pop-up warning message:

> “Select an item from the list” («Selecciona un elemento de la lista»)

This message indicates that no main category or subcategory has been selected, so the system cannot continue with the creation of the event.

#### Cause of the error

> The user did not select a main category from the drop-down menu.
>
> Consequently, the subcategory cannot be loaded or selected.
>
> The system requires both fields to be completed before continuing.

- 

#### Recommended solution

> Open the “Main Category” («Categoría Principal») drop-down menu and select an option from the list.
>
> Wait for the corresponding options to load in the “Subcategory” («Subcategoría») field.
>
> Select a valid subcategory.
>
> Once both fields have been selected, click “Create Event” to complete the registration.

7.  In the Organizer Request section, users must upload a document that supports their request to be approved as event organizers within the platform. This process ensures that the information presented meets the established formal requirements.

    <img src="../_assets/09_Manuales/Manual_de_usuario/Manual_web/media/image23.png" style="width:6.49861in;height:3.18819in" alt="erro pdf" />

#### Error Description – File type not allowed

**Screen:** Organizer Request\
**Location:** Document upload form\
**Type of error:** File format validation

#### Description

When trying to upload a file in **.jpeg** format, the system shows a red alert with the message:

> “Unexpected error: Only PDF files are allowed” («Error inesperado: Solo se permiten archivos PDF»)

This indicates that the system **only accepts documents in PDF format**, since it is the standard required to validate official requests.

#### Cause of the error

> The user tries to upload a file with an extension that is **not allowed** (for example: .jpeg, .png, .jpg, .docx, etc.).
>
> The backend validation detects the file type and blocks the upload process.

#### Recommended solution

> Convert the document or image to **.PDF** format before uploading it.
>
> Make sure that the file meets the established maximum size requirements (if applicable).
>
> Upload the document again using the **“Change file” («Cambiar archivo»)** button.
>
> Verify that the message **“Valid file” («Archivo válido»)** appears in the status bar before continuing with sending the request.


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «0»<br>![Header of the original](../_assets/09_Manuales/Manual_de_usuario/Manual_web/header_footer/image1.png)

---

<a id="doc-te-0159"></a>

<!--
ruta_anterior: en/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion.md
id: TE-0159
title: "manual mobile e instalacion"
lang: en
source: 09_Manuales/Manual de usuario/manual mobile e instalacion.docx
source_sha256: a92e3107d13fab5b6fc476da03be20d311f2cd59517b8f333b1a69cdbca59ef4
conversion: "pandoc 3.9 (-t gfm --wrap=none --extract-media) + extraction of headers/footers; without manual review. English translation of md/es: Claude Opus 5.5 (claude-opus-5-5); without manual review"
converted_on: 2026-10-23
fidelity: parcial
losses:
  - "The original does not use heading styles; the visual headings remain as bold text, without # hierarchy. Pending manual marking."
  - "Headers and footers extracted separately (pandoc does not convert them); in the original they are repeated on every page. The fields are shown as {PAGE}, {NUMPAGES}."
  - "Translation: the interface texts in quotation marks are translated and the Spanish literal is added in parentheses («…»), because the real English text of the interface is not known."
  - "Translation: the text inside the screenshots is not translated."
status: borrador
reviewed_by: ""
translation_of: es/12_Manual_Usuario.md#doc-te-0159
es_sha256: 454310b9d6d396a152a05836eaff265255c7ca73f388b5b5dc7886a108f6703c
-->

# User manual — mobile app and installation

**Mobile application manual**

Lozano Contreras Cristofer David

Santos Ortiz Jhampier

Análisis y Desarrollo de Software (Software Analysis and Development)

\(3145556\)

Servicio Nacional de Aprendizaje (National Learning Service)

October 1, 2025

**Introduction**

The purpose of this user manual is to describe clearly and in detail the main features of the "Tu Evento" mobile application, developed by CapySoft. This application is designed to provide attendees with a practical, simple and accessible tool that makes it easier to interact with events quickly and efficiently from their mobile devices.

Unlike the web version, the mobile application focuses on offering the essential features for end users, such as: account creation, login, viewing the available events, participation through comments and payment validation by scanning QR codes. With these tools, an agile, intuitive experience adapted to the portability of Android devices is guaranteed.

**System requirements**

- **Operating system:**

> **Minimum:** Android 11
>
> **Recommended:** Android 13 or later

- **RAM memory:**

> **Minimum:** 3 GB
>
> **Recommended:** 4 GB or more

- **Available internal storage:**

> **Minimum:** 200 MB free for the installation and temporary data

- **Connectivity:**

> Stable Internet connection (Wi-Fi or mobile data).
>
> Access to the rear camera for scanning QR codes.

**Installation**

To install the mobile application, the user must go from their Android device to the official website of the system using their mobile browser. Once there, they must select the option “Download APK” («Descargar APK»), located in the device compatibility section.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image1.png" style="width:3.44792in;height:2.58333in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image2.png" style="width:3.80486in;height:2.59364in" />

Once the APK file has been downloaded, the user must enable the option “Install unknown apps” («Instalar apps desconocidas») on their Android device. To do this, they must go to the system settings and allow installation from the source; then, when the downloaded file is opened, the system will ask for confirmation to install the application\
After accepting, the installation process will start, and once it is finished, a message will be shown indicating that the application has been installed correctly. Finally, the user can select the option “Open” («Abrir») to run the application or “Done” («Listo») to close it and access it later from the main menu of the device.

1.  <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image3.png" style="width:2.33333in;height:3.875in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image4.png" style="width:2.30208in;height:3.88542in" />

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image5.png" style="width:2.34408in;height:2.07321in" />

**Access to and use of the application**

1.  **Main interface**

When opening the "Tu Evento" mobile application, the user will be taken to the login screen. In this section, the system will request the previously registered credentials (email and password) to allow secure access to the platform.

Likewise, from this screen the user will have additional options available, such as:

1.  Create a new account, if not registered.

2.  Recover password, if it has been forgotten.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image6.png" style="width:2.76042in;height:4.71875in" />In this way, it is guaranteed that each user can access the main features of the application in a personalized way.

1.  **Create account interface**

The mobile application allows new users to register quickly and easily to access all the available features. When the option “Create account” («Crear cuenta») is selected from the login screen, the registration form will open, in which the system will request the following data:

1.  Full name: Personal information that will identify the user within the platform.

2.  Email: Unique data used as a means of contact and as the user name to log in.

3.  Password: Personal key that will guarantee the security of access to the account.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image7.png" style="width:2.37403in;height:4.25581in" />Once the fields have been filled in, the user must press the “Next” («Siguiente») button to send the information.

1.  **Account creation verification code**

Once the account creation process has been completed, the system will automatically send a verification code to the email registered by the user. This step is mandatory to validate the authenticity of the account and enable its use within the mobile application. On the verification screen, the user must:

1.  Enter the verification code received in their email.

2.  Press the “Verify” («Verificar») button to confirm the validity of the code.

**Possible results:**

**Successful verification:**\
If the code entered is correct and still within its validity period, the system will confirm the activation of the account and allow immediate access to the application.

> <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image8.png" style="width:2.34408in;height:4.12558in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image9.png" style="width:2.5316in;height:4.34436in" />

1.  **Password recovery**

The "Tu Evento" mobile application offers the option to recover access in case the user forgets their password. To do this, from the login screen the link “Forgot your password?” («¿Olvidó su contraseña?») must be selected, which will enable the recovery process.

**Process steps:**

**Entering the email:**\
The system will ask the user to type the email associated with their account.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image10.png" style="width:2.10417in;height:4.69767in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image11.png" style="width:2.32324in;height:4.68815in" />

2.  **Verification code and renewal**

When access recovery is requested, the system sends a unique verification code to the registered email. This code serves to confirm the identity of the user before allowing the access key to be modified.

Once the code has been validated, the system enables the form so that the user can register their new password. The previous password is invalidated, and from that moment on it will only be possible to access with the newly defined key.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image12.png" style="width:2.27972in;height:3.4645in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image13.png" style="width:2.13403in;height:3.40698in" />

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image14.png" style="width:2.22917in;height:2.70833in" />

3.  **Login**

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image15.png" style="width:2.76119in;height:4.74583in" />If the credentials entered are correct, the system will validate the data and redirect the user to the main screen, where they will be able to view the available events and access the features offered.

4.  **Filter event by name**

it allows the user to search for events quickly and precisely through a filter by name. This feature makes it easier to locate a specific event without having to go through the whole available list.

**Usage process:**

1.  The user accesses the screen of available events.

2.  In the search bar, they type the full or partial name of the event they want to locate.

3.  <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image16.png" style="width:2.20864in;height:4.51105in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image17.png" style="width:2.15655in;height:4.53188in" />The system processes the query and shows on screen only the events that match the text entered.

    1.  **Comment on an event**

The system allows users to comment on the events available within the application, encouraging interaction and the exchange of opinions between attendees. To do this, the user must access the event they are interested in, select the Comment (Comentar) option and enter the text in the enabled field. Once the comment has been written, they must press the save (guardar) button, with which their contribution will be recorded and visible to other users of the platform.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image18.png" style="width:2.64998in;height:4.22292in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image19.png" style="width:2.30208in;height:4.33333in" />

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image20.png" style="width:2.125in;height:3.75412in" />

2.  **Renewal of personal data**

The system offers users the possibility of renewing or updating their personal data simply and securely, in order to keep their information always current within the platform. To do this, the user accesses the Profile (Perfil) menu, where a form is enabled that allows them to modify fields such as telephone number, date of birth and address; once the changes have been made, they must press the Save changes (Guardar cambios) button so that the update is recorded successfully

> <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image21.png" style="width:2.3024in;height:4.7715in" /> <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image22.png" style="width:2.21906in;height:4.75066in" />

3.  **Log out**

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image23.png" style="width:2.36491in;height:4.80275in" />The system gives users the option to log out, guaranteeing the protection of the account. To do so, the user must access the main or Profile menu, select the Log out (Cerrar sesión) option and confirm the action. Once done, the application will automatically redirect to the login screen, ensuring that access remains restricted until the correct credentials are entered again.

1.  **Account deactivation**

The system offers users the possibility of voluntarily deactivating their account if they no longer wish to use the application. To do this, the user must go to the Profile menu and select the Deactivate account (Desactivar cuenta) option. Once the action has been confirmed, the account will be disabled, which means that it will not be able to access the features of the application or appear in the active events.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image24.png" style="width:2.37533in;height:4.85484in" />

2.  **Scanning and validation of the QR ticket**

The application includes a feature that allows users to scan the QR code associated with their event ticket, in order to validate their access quickly and securely. When the scanning option is used, the system checks the authenticity of the ticket in real time, verifying that it is registered and that the payment has previously been confirmed by the organizer.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image25.png" style="width:2.2399in;height:4.37561in" /><img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image26.png" style="width:2.31282in;height:3.88596in" />

2.  **Error cases**

- **Login interface**

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image27.png" style="width:2.73125in;height:5.01493in" />If the user enters incorrect credentials (email or password), the system will show an error message indicating “email not registered” («email no registrado»).

- **Recover password interface**

If the user enters a nonexistent account or one not registered on the platform, the system will show an error message indicating:\
**“User not found” («Usuario no encontrado»)**.

In this way, it is guaranteed that only previously registered users can recover their access, maintaining the security and integrity of the application.

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image28.png" style="width:2.39617in;height:3.22962in" />

- **Logging in to a deactivated account**

If a user tries to log in with a previously deactivated account, the system will show a message reporting that the account is inactive and that it is not possible to access the features of the application.

> <img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image29.png" style="width:2.78734in;height:3.99884in" />

- **Update data**

<img src="../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/media/image30.png" style="width:2.21875in;height:4.90625in" />If no data has been modified, the system will show an informative message indicating: “There are no changes to save” («No hay cambios para guardar»), guaranteeing that only new or updated data is stored. In this way, it is ensured that the user's information on the platform always remains current and consistent with reality.


---

## Headers and footers of the original

- **Header** (`word/header1.xml`): text «0»<br>![Header of the original](../_assets/09_Manuales/Manual_de_usuario/manual_mobile_e_instalacion/header_footer/image31.png)
