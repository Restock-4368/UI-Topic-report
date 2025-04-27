# Capítulo V: Product Implementation, Validation & Deployment

## 5.1 Software Configuration Management

### 5.1.1. Software Development Environment Configuration

A continuación, se listan las herramientas y estándares adoptados por el equipo para el desarrollo colaborativo del sistema:

| Actividad | Herramienta / Guía | Propósito | Tipo de acceso / Ruta |
|-----------|--------------------|-----------|------------------------|
| Project Management | Jira Software | Seguimiento de backlog, tareas y sprints. | SaaS – [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira) |
| Requirements Management | Gherkin Conventions | Escritura legible de requisitos con formato Given/When/Then. | [https://cucumber.io/docs/gherkin/](https://cucumber.io/docs/gherkin/) |
| Product UX/UI Design | Figma | Prototipos y diseño responsive. | SaaS – [https://figma.com](https://figma.com) |
| Frontend Dev | HTML, CSS, JavaScript, Vue | Construcción de la interfaz web. | [https://vuejs.org/guide/introduction.html](https://vuejs.org/guide/introduction.html) |
| Backend Dev | C# + ASP.NET Core | Implementación de servicios y lógica del backend. | [https://learn.microsoft.com/en-us/aspnet/core](https://learn.microsoft.com/en-us/aspnet/core) |
| IDE | Rider + WebStorm | Desarrollo, testing y depuración. | [https://www.jetbrains.com/rider](https://www.jetbrains.com/rider) / [https://www.jetbrains.com/webstorm](https://www.jetbrains.com/webstorm) |
| Code Standards | Google HTML/CSS Style Guide, Vue Style Guide, MDN Guidelines, W3C JavaScript Style Guide, Google JavaScript Style Guide, C# Coding Conventions, Microsoft ASP.NET Core Guidelines | Aplicación de buenas prácticas de desarrollo en frontend y backend. | [https://developer.mozilla.org/](https://developer.mozilla.org/) / [https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style) |
| Version Control | Git + GitHub | Control de versiones y trabajo colaborativo. | SaaS – [https://github.com](https://github.com) |
| Software Deployment | Railway / Render | Despliegue continuo de la aplicación para ambientes de prueba y validación. | SaaS – [https://railway.app](https://railway.app) / [https://render.com](https://render.com) |
| Software Documentation | Notion + Postman | Documentación técnica del sistema y pruebas de API. | SaaS – [https://www.notion.so](https://www.notion.so) / [https://www.postman.com](https://www.postman.com) |

### 5.1.2 Source Code Management

En esta sección el equipo establece los medios y esquema de organización que aplicará para el seguimiento de modificaciones. Para ello se utilizará **GitHub** como plataforma y sistema de control de versiones.

A continuación se indican los URLs de los repositorios de GitHub para cada producto:

- **Landing Page**: [URL del repositorio aquí]
- **Web Services**: [URL del repositorio aquí]  
  _(Incluye el proyecto y los archivos de pruebas unitarias e integración/aceptación)_
- **Frontend Web Application**: [URL del repositorio aquí]

### GitFlow Workflow

Se implementará el modelo de ramificación propuesto por Vincent Driessen en su artículo *“A successful Git branching model”*, conocido como **GitFlow**. Este modelo organiza el trabajo en las siguientes ramas:

- `main`: Rama principal, contiene siempre el código en producción.
- `develop`: Rama de desarrollo principal, donde se integran las funcionalidades antes de pasar a producción.
- `feature/*`: Ramas creadas a partir de `develop` para desarrollar nuevas funcionalidades.  
  **Convención de nombres:** `feature/<nombre-corto-descriptivo>`  
  _Ejemplo: `feature/login-auth`_
- `release/*`: Ramas creadas desde `develop` cuando se prepara una nueva versión para producción.  
  **Convención de nombres:** `release/<versión>`  
  _Ejemplo: `release/1.2.0`_
- `hotfix/*`: Ramas creadas desde `main` para corregir errores críticos en producción.  
  **Convención de nombres:** `hotfix/<descripción-corta>`  
  _Ejemplo: `hotfix/fix-payment-bug`_

### Versionado Semántico

Se aplicará el esquema de **Semantic Versioning 2.0.0**, con el siguiente formato:

- **MAJOR**: Incompatibilidades en la API.
- **MINOR**: Nuevas funcionalidades sin romper compatibilidad.
- **PATCH**: Correcciones de errores menores y ajustes sin afectar funcionalidades.

_Ejemplo de versión:_ `v1.3.2`

### Convenciones de Commits

Se utilizará el estándar de **Conventional Commits** para los mensajes de commits. Esto facilitará la automatización en los procesos de integración continua y generación de changelogs.

**Ejemplos:**

- `feat: add login functionality`
- `fix: correct null pointer exception on user service`
- `chore: update dependencies`


## 5.1.3. Source Code Style Guide & Conventions

## Frontend (Landing Page - HTML, CSS, JavaScript)

### Convenciones generales:
- **Idioma**: Todo el código, incluyendo nombres de variables, funciones y clases, está escrito en **inglés**.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.html`, `.css`, `.js`
- **Estilo de código adoptado**:
  - [W3Schools HTML Style Guide](https://www.w3schools.com/html/html5_syntax.asp)
  - [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

### Nomenclatura:
- **Clases CSS**: `kebab-case` (ej. `main-container`)
- **IDs HTML**: `camelCase` (ej. `mainContent`)
- **Variables JS**: `camelCase` (ej. `userName`)
- **Funciones JS**: `camelCase` (ej. `handleClick()`)

---

## Frontend Web App (Vue.js + JavaScript)

### Convenciones generales:
- **Idioma**: Código completamente en **inglés**.
- **Estructura de carpetas**: Segregación por módulos y componentes.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.vue`, `.js`, `.css`

### Estilo de código adoptado:
- [Vue.js Style Guide (Oficial)](https://vuejs.org/guide/reusability/style-guide.html)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

### Nomenclatura:
- **Componentes Vue**: `PascalCase` (ej. `UserProfile.vue`)
- **Variables y funciones JS**: `camelCase` (ej. `userName`, `handleSubmit()`)
- **Archivos**: `kebab-case` (ej. `user-profile.vue`)
- **Props**: `camelCase` en JavaScript, `kebab-case` en templates HTML (ej. prop: `userProfile`, uso: `user-profile`)
- **Eventos personalizados**: `kebab-case` (ej. `user-logged-in`)
- **Clases CSS**: `kebab-case`

---

## Backend (ASP.NET + C#)

### Convenciones generales:
- **Idioma**: Código y documentación interna en **inglés**.
- **Indentación**: 4 espacios.
- **Formato de archivos**: `.cs`

### Estilo de código adoptado:
- [Microsoft C# Coding Conventions](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- [ASP.NET Core Best Practices](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/index)

### Nomenclatura:
- **Clases**: `PascalCase` (ej. `UserService`)
- **Métodos**: `PascalCase` (ej. `GetUserById()`)
- **Variables locales**: `camelCase` (ej. `userRepository`)
- **Constantes**: `PascalCase` o `UPPER_SNAKE_CASE` (según si es `const` o `readonly static`) (ej. `MaxUsers`)
- **Interfaces**: `IPascalCase` (ej. `IUserRepository`)
- **Endpoints (URLs)**: `kebab-case` (ej. `/api/user-profile`)
- **Namespaces**: `PascalCase` y estructurados jerárquicamente (ej. `ProjectName.ModuleName.FeatureName`)


### 5.1.4 Software Deployment Configuration


## 5.2 Landing Page, Services & Applications Implementation

## 5.2.1 Sprint 1

### 5.2.1.1. Sprint Planning 1

A continuación, se presenta la planificación correspondiente a nuestro Sprint 1, el cual tiene como enfoque principal el desarrollo de la landing page de Restock. En esta etapa inicial, el equipo definió el objetivo del sprint, seleccionó las historias de usuario más relevantes y estableció los entregables clave que permitirán construir una primera versión funcional y visualmente atractiva de la página. Esta planificación busca asegurar un entendimiento compartido entre todos los miembros del equipo y sentar las bases para comunicar eficazmente el valor de la plataforma a los usuarios potenciales.

| Sprint #     | Sprint 1                   | 
|--------------|----------------------------|
| **Sprint Planning Background**                |      
| Date                  | 2025-04-23             | 
| Time                  | 19:00 pm (GMT-5)|
| Location | Modalidad remota mediante la plataforma Discord |
| Prepared By | Shapiama Rivera, Gabriela Nicole |
| Attendees (to planning meeting) | Avendaño Balarezo, Williams Eduardo / Castro Alejos / Julio, Guerra Perez, José Jahaziel / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole |
| Sprint 0 Review Summary  | Dado que este es el sprint inicial, no se presenta un resumen del sprint anterior. |
| Sprint 0 Retrospective Summary | Dado que este es el sprint inicial, no se presenta una retroalimentación del sprint anterior. |
| **Sprint Goal & User Stories** |
| Sprint 1 Goal | Nos enfocamos en implementar la estructura principal y las funcionalidades clave de la landing page pública de Restock.<br>Creemos que esto aportará una percepción más sólida del producto y despertará mayor interés entre los usuarios potenciales, al comunicar de forma clara el valor y los beneficios de la plataforma.<br>Esto se confirmará cuando los visitantes puedan navegar de manera fluida por la página, comprendan fácilmente qué ofrece Restock y muestren intención de interactuar o registrarse. |
| Sprint 1 Velocity | 27 puntos |
| Sum of Story Points |  27 puntos |

#### 5.2.1.2 Aspect Leaders and Collaborators

#### 5.2.1.3 Sprint Backlog 1


El objetivo principal de este Sprint es diseñar, implementar y validar las secciones del landing page, asegurando una navegación fluida, una experiencia responsiva en todos los dispositivos y funcionalidades críticas como registro, inicio de sesión y recuperación de contraseña. Se busca garantizar que el usuario final pueda interactuar de manera sencilla y eficiente con la plataforma, mejorando su satisfacción y promoviendo el cumplimiento de los objetivos de negocio.

**screenshot del Board**

![board-sprint](assets/images/board-sprint.png)
![board-sprint-detail](assets/images/board-sprint-detallado.png)

https://trello.com/invite/b/680c05f1fac416bfdb0ea024/ATTI41428da9336a1d11b0878438a247c3531DFD7E76/sprint-backlog-1

<br>

| User Story ID | User Story Title                                | Task ID | Task Title                   | Task Description                                                   | Estimated Hours |
|---------------|--------------------------------------------------|---------|------------------------------|--------------------------------------------------------------------|-----------------|
| US-08         | Mostrar Mensaje de Valor en la Sección Principal | T001     | Diseñar sección               | Crear diseño visual para 'mostrar mensaje de valor en la sección principal'. | 1/2 h |
|               |                                                  | T002     | Implementar funcionalidad     | Codificar el componente necesario para 'mostrar mensaje de valor en la sección principal'. | 1h |
|               |                                                  | T003     | Realizar pruebas              | Verificar que 'mostrar mensaje de valor en la sección principal' funcione correctamente. | 1/2h |
| US-09         | Mostrar Beneficios Segmentados por Tipo de Usuario | T004     | Diseñar sección               | Crear diseño visual para 'mostrar beneficios segmentados por tipo de usuario'. | 1/2h |
|               |                                                  | T005     | Implementar funcionalidad     | Codificar el componente necesario para 'mostrar beneficios segmentados por tipo de usuario'. | 1h |
|               |                                                  | T006     | Realizar pruebas              | Verificar que 'mostrar beneficios segmentados por tipo de usuario' funcione correctamente. | 1/2h |
| US-10         | Incluir Llamados a la Acción (CTA) con Redirección y Descarga | T007     | Diseñar sección               | Crear diseño visual para 'incluir llamados a la acción (cta) con redirección y descarga'. | 1/2h |
|               |                                                  | T008     | Implementar funcionalidad     | Codificar el componente necesario para 'incluir llamados a la acción (cta) con redirección y descarga'. | 1h |
|               |                                                  | T009     | Realizar pruebas              | Verificar que 'incluir llamados a la acción (cta) con redirección y descarga' funcione correctamente. | 1/2h |
| US-05         | Visualización de la barra de navegación         | T010     | Diseñar sección               | Crear diseño visual para 'visualización de la barra de navegación'. | 1/2h |
|               |                                                  | T011     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de la barra de navegación'. | 1h |
|               |                                                  | T012     | Realizar pruebas              | Verificar que 'visualización de la barra de navegación' funcione correctamente. | 1/2h |
| US-06         | Visualización de pasos del funcionamiento       | T013     | Diseñar sección               | Crear diseño visual para 'visualización de pasos del funcionamiento'. | 1/2h |
|               |                                                  | T014     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de pasos del funcionamiento'. | 1h |
|               |                                                  | T015     | Realizar pruebas              | Verificar que 'visualización de pasos del funcionamiento' funcione correctamente. | 1/2h |
| US-07         | Alternativa con video explicativo               | T016     | Diseñar sección               | Crear diseño visual para 'alternativa con video explicativo'. | 1/2h |
|               |                                                  | T017     | Implementar funcionalidad     | Codificar el componente necesario para 'alternativa con video explicativo'. | 1h |
|               |                                                  | T018     | Realizar pruebas              | Verificar que 'alternativa con video explicativo' funcione correctamente. | 1/2h |
| US-04         | Visualización de footer en landing page         | T019     | Diseñar sección               | Crear diseño visual para 'visualización de footer en landing page'. | 1/2h |
|               |                                                  | T020     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de footer en landing page'. | 2h |
|               |                                                  | T021     | Realizar pruebas              | Verificar que 'visualización de footer en landing page' funcione correctamente. | 1/2h |
| US-01         | Ver testimonios de clientes                     | T022     | Diseñar sección               | Crear diseño visual para 'ver testimonios de clientes'. | 2h |
|               |                                                  | T023     | Implementar funcionalidad     | Codificar el componente necesario para 'ver testimonios de clientes'. | 1/2h |
|               |                                                  | T024     | Realizar pruebas              | Verificar que 'ver testimonios de clientes' funcione correctamente. | 1h |
| US-02         | Consultar Preguntas Frecuentes                  | T025     | Diseñar sección               | Crear diseño visual para 'consultar preguntas frecuentes'. | 1/2h |
|               |                                                  | T026     | Implementar funcionalidad     | Codificar el componente necesario para 'consultar preguntas frecuentes'. | 1h |
|               |                                                  | T027     | Realizar pruebas              | Verificar que 'consultar preguntas frecuentes' funcione correctamente. | 1/2h |
| US-03         | Enviar Formulario de Contacto                   | T028     | Diseñar sección               | Crear diseño visual para 'enviar formulario de contacto'. | 1h |
|               |                                                  | T029     | Implementar funcionalidad     | Codificar el componente necesario para 'enviar formulario de contacto'. | 1/2h |
|               |                                                  | T030     | Realizar pruebas              | Verificar que 'enviar formulario de contacto' funcione correctamente. | 1h |
| US-16         | Navegación fluida entre secciones               | T031     | Diseñar sección               | Crear diseño visual para 'navegación fluida entre secciones'. | 1/2h |
|               |                                                  | T032     | Implementar funcionalidad     | Codificar el componente necesario para 'navegación fluida entre secciones'. | 1h |
|               |                                                  | T033     | Realizar pruebas              | Verificar que 'navegación fluida entre secciones' funcione correctamente. | 1/2h |
| US-13         | Visualización responsive en desktop             | T034     | Diseñar sección               | Crear diseño visual para 'visualización responsive en desktop'. | 1/2h |
|               |                                                  | T035     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en desktop'. | 1h |
|               |                                                  | T036     | Realizar pruebas              | Verificar que 'visualización responsive en desktop' funcione correctamente. | 1/2h |
| US-15         | Visualización responsive en dispositivos móviles | T037     | Diseñar sección               | Crear diseño visual para 'visualización responsive en dispositivos móviles'. | 1h |
|               |                                                  | T038     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en dispositivos móviles'. | 1/2h |
|               |                                                  | T039     | Realizar pruebas              | Verificar que 'visualización responsive en dispositivos móviles' funcione correctamente. | 1/2h |
| US-14         | Visualización responsive en tablet              | T040     | Diseñar sección               | Crear diseño visual para 'visualización responsive en tablet'. | 1/2h |
|               |                                                  | T041     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en tablet'. | 1h |
|               |                                                  | T042     | Realizar pruebas              | Verificar que 'visualización responsive en tablet' funcione correctamente. | 1/2h |
| US-17         | Registro                                         | T043     | Diseñar sección               | Crear diseño visual para 'registro'. | 2h |
|               |                                                  | T044     | Implementar funcionalidad     | Codificar el componente necesario para 'registro'. | 2h |
|               |                                                  | T045     | Realizar pruebas              | Verificar que 'registro' funcione correctamente. | 1h |
| US-18         | Inicio de sesión                                 | T046     | Diseñar sección               | Crear diseño visual para 'inicio de sesión'. | 2h |
|               |                                                  | T047     | Implementar funcionalidad     | Codificar el componente necesario para 'inicio de sesión'. | 1h |
|               |                                                  | T048     | Realizar pruebas              | Verificar que 'inicio de sesión' funcione correctamente. | 1h |
| US-19         | Recuperación de contraseña                      | T049     | Diseñar sección               | Crear diseño visual para 'recuperación de contraseña'. | 2h |
|               |                                                  | T050     | Implementar funcionalidad     | Codificar el componente necesario para 'recuperación de contraseña'. | 1/2h |
|               |                                                  | T051     | Realizar pruebas              | Verificar que 'recuperación de contraseña' funcione correctamente. | 1h |


#### 5.2.1.4 Development Evidence for Sprint Review

En esta sección se presentan los avances de implementación realizados durante el Sprint 1, el cual tuvo como objetivo principal construir la Landing Page de la plataforma Restock.
Se desarrollaron múltiples secciones, aplicando principios de diseño responsivo, buenas prácticas de codificación y asegurando consistencia con el estilo visual definido para el proyecto. Los entregables principales de este sprint incluyen la creación de secciones como About Us, Benefits, Testimonials, FAQ, Tutorial, Contact, Footer, además de la implementación de mejoras de SEO, formularios de acceso, y enlaces de descarga.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date)|
|-|-|-|-|-|-|
| GabrielaShapiama/UI-Topic-landing | feature/acces | 798578d | fix(access): remove incorrect image. | Removed a misplaced or outdated image to maintain correct visuals in the access section. | 26/04/25 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 946e9ba | feat(tutorial-section): fix height | Adjusted the height of tutorial elements to ensure visual consistency across devices. | 26/04/25 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 23c3dd6 | feat(tutorial-section): fix tutorial links width | Corrected the width of tutorial links to improve responsiveness and readability. | 26/04/25 |
| Williams/UI-Topic-landing | feature/seo-tags-meta-tags | 6f1e249 | feat(seo-tags-meta-tags): adding seo tags and meta tags | Implemented basic SEO and meta tags to enhance page discoverability and improve search engine indexing. | 26/04/25 |
| Williams/UI-Topic-landing | feature/descargar | 7066dfa | feat(descargar): adding download section(html,css,js) | Created a new download section with layout, styles, and interaction scripts. | 26/04/25 |
| Williams/UI-Topic-landing | feature/preguntas | c01b5c2 | feat(preguntas): adding frecuent questions(html,css,js) | Developed the FAQ section with collapsible questions and styling for better UX. | 26/04/25 |
| Williams/UI-Topic-landing | feature/testimonios | bacb51d | feat(testimonios): adding testimonios(html,css) | Implemented the testimonials section including design and user reviews. | 26/04/25 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 8de1580 | feat(footer-section): add footer section, footer css file, and add icons | Built the footer layout, styling, and added social media icons for better navigation. | 26/04/25 |
| Yaku Guzman/UI-Topic-landing | feature/contacto-section | 1a2d460 | feat(contacto-section): add contacto section and contacto css file | Added a contact form section including input fields and responsive design. | 26/04/25 |
| jahazielgp/UI-Topic-landing | feature/benefits-section | 23713f3 | feat(benefits-section): add benefits section with their style. | Created the benefits section showcasing platform advantages with proper styling. | 26/04/25 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | d358944 | feat(tutorial-section): add tutorial section and tutorial images | Developed the tutorial section and incorporated tutorial-related images. | 26/04/25 |
| jahazielgp/UI-Topic-landing | feature/about-us-section | 9ace330 | feat(about-us): add about us template and styles. | Implemented the About Us section with a basic template and responsive design. | 26/04/25 |
| jahazielgp/UI-Topic-landing | feature/hero-section | 2ff0a3c | feat(hero-section): add template, scripts and styles components of hero section. | Created the hero section including main banner, call-to-action, and responsive layout. | 26/04/25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | bad294f | feat(access): add access forms. | Developed user access forms including login and registration interfaces. | 26/04/25 |
| jahazielgp/UI-Topic-landing | feature/develop | a66d307 | chore: initial commit | Initial setup of project structure and configurations. | 26/04/25 |
| jahazielgp/UI-Topic-landing | main | 15bf93a | Initial commit | Base initialization of the landing page project repository. | 26/04/25 |

#### Productos según alcance del Sprint
##### Landing Page
Durante el Sprint 1 se implementó la Landing Page de Restock. Los principales avances fueron:

- Diseño responsivo adaptado a diferentes tamaños de pantalla.

- Creación de secciones: Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutorial, Contacto y Footer.

- Aplicación de buenas prácticas de accesibilidad (uso de etiquetado semántico, contraste adecuado).

- Optimización inicial para motores de búsqueda (SEO básico) con metaetiquetas y atributos relevantes.

- Implementación de navegación fluida entre secciones mediante anclas y smooth scrolling.

- Validación de compatibilidad en navegadores modernos y dispositivos móviles.

#### 5.2.1.5 Execution Evidence for Sprint Review

#### 5.2.1.6 Services Documentation Evidence for Sprint Review
Durante este sprint se completó el diseño e implementación del Landing Page del sistema, el cual forma parte del acceso inicial al sistema y constituye un punto de entrada fundamental para los usuarios. Aunque no se implementaron endpoints tradicionales de tipo REST en este sprint, se documenta a continuación la URL del recurso publicado, junto con evidencia de despliegue, interacción y commits relacionados.

**Descripción del Logro:**

-Implementación del Landing Page estático.

-Deployment del landing page.

### 🌐 Recursos del Sprint

| Recurso      | Acción implementada   | Método HTTP | URL / Endpoint                      | Link de repositorio         |
|--------------|------------------------|-------------|-------------------------------------|---------------------------|
| Landing Page | Visualización inicial | GET         | https://desarrollo-de-app-web-curso-upc.github.io/UI-Topic-landing/               | https://github.com/Desarrollo-de-App-Open-Source-Curso-UPC/UI-Topic-landing   |

**Documentacion**
Commit 4d6b92f: Initial commit

#### 5.2.1.7 Software Deployment Evidence for Sprint Review

# Software Deployment Evidence for Sprint Review

## Introducción

Durante el Sprint 1 se llevó a cabo el desarrollo de la **Landing Page** del proyecto, cumpliendo con los requerimientos establecidos en el backlog del sprint. Para el proceso de **Deployment**, se realizó la configuración necesaria para publicar la Landing Page utilizando **GitHub Pages** en la organización de GitHub destinada al proyecto.

## Actividades Realizadas

### 1. Creación de la Organización en GitHub

- Se creó una nueva organización en GitHub para centralizar todos los repositorios del proyecto.
- Configuración de nombre, imagen y ajustes básicos de la organización.
- Adición de los miembros del equipo de desarrollo con los roles adecuados.

**Captura de creación de la organización:**

![Organización creada en GitHub](assets\images\software-deployment-evidence-1.png)

### 2. Creación del Repositorio para la Landing Page

- Se creó un nuevo repositorio llamado `landing-page` dentro de la organización.
- Configuración de visibilidad pública para permitir la publicación mediante GitHub Pages.
- Inicialización del repositorio con un archivo README y licencia adecuada.

**Captura del repositorio creado:**

![Repositorio Landing Page](assets\images\software-deployment-evidence-2.png)

### 3. Desarrollo de la Landing Page

- Se desarrolló la Landing Page siguiendo los requisitos definidos en el Sprint 1.
- Se implementaron funcionalidades como navegación, formularios de contacto, sección de beneficios, entre otros.
- El código fue versionado y gestionado mediante Git y GitHub.

**Captura de la estructura del proyecto:**

![Estructura de archivos de la Landing](assets\images\software-deployment-evidence-3.png)

### 4. Configuración de GitHub Pages

- Se configuró GitHub Pages para desplegar la página desde la rama `main` del repositorio.
- Se seleccionó la carpeta raíz (`/root`) como fuente de publicación.
- Se generó la URL pública para el acceso a la Landing Page.

**Captura de configuración de GitHub Pages:**

![Configuración GitHub Pages](ruta/a/la/imagen)

### 5. Deploy de la Landing Page

- Se realizó el primer deploy al terminar el desarrollo básico.
- Se verificó que la página cargara correctamente y que el contenido fuera accesible.
- Se hicieron pequeños ajustes de rutas y assets estáticos según necesidades.

**Captura de la página desplegada:**

![Página desplegada en GitHub Pages](ruta/a/la/imagen)

#### 5.2.1.8 Team Collaboration Insights during Sprint

Durante el Sprint 1, el equipo de desarrollo trabajó de forma colaborativa en la implementación de los productos asignados, principalmente enfocados en la **Landing Page**. Cada miembro del equipo participó activamente en el desarrollo de las funcionalidades, asegurando un flujo de trabajo ágil y eficiente a través del control de versiones en **GitHub**.

## Actividades de Implementación

- Distribución de tareas mediante la planificación en Jira.
- Creación de ramas específicas para cada feature o corrección.
- Uso de **Pull Requests** para revisión y fusión del código.
- Resolución de conflictos y seguimiento de buenas prácticas de Git.
- Participación activa de todos los miembros en el ciclo de desarrollo, asegurando cobertura y avance continuo en las tareas.

## Evidencias de Colaboración

A continuación se presentan las capturas que evidencian la colaboración del equipo a través de GitHub:

### Pulse Overview

_Resumen general del trabajo colaborativo realizado en GitHub durante el Sprint 1:_

![Pulse Overview](ruta/a/la/imagen)

- 23 Pull Requests merged.
- 6 autores contribuyendo activamente.
- 36 commits en total en las diferentes ramas de desarrollo.
- Distribución de actividades visible a través de las gráficas.

### Commits por Autor

_Captura que muestra la cantidad de commits realizados por cada miembro del equipo:_

![Commits por Autor](ruta/a/la/imagen)

- Todos los miembros participaron activamente en el ciclo de desarrollo.
- Se observa una distribución balanceada del esfuerzo y la contribución de código.

### Pull Requests

_Detalle de algunos Pull Requests relevantes:_

- `feat(navbar): add language switch icon and console log for future functionality`
- `fix(access): fix text position`
- `Feature/fix navbar`
- `feat(benefits): add benefits section`

**Captura de Pull Requests:**

![Pull Requests](ruta/a/la/imagen)