# Capítulo V: Product Implementation, Validation & Deployment

## 5.1 Software Configuration Management

### 5.1.1. Software Development Environment Configuration

A continuación, se listan las herramientas y estándares adoptados por el equipo para el desarrollo colaborativo del sistema:

| Actividad               | Herramienta / Guía                                                                                                                                                               | Propósito                                                                    | Tipo de acceso / Ruta                                                                                                                                                                                               |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Project Management      | Trello Software                                                                                                                                                                   | Seguimiento de backlog, tareas y sprints.                                     | SaaS –[https://trello.com/](https://trello.com/software/jira)                                                                                                                                                         |
| Requirements Management | Gherkin Conventions                                                                                                                                                               | Escritura legible de requisitos con formato Given/When/Then.                  | [https://cucumber.io/docs/gherkin/](https://cucumber.io/docs/gherkin/)                                                                                                                                                 |
| Product UX/UI Design    | Figma                                                                                                                                                                             | Prototipos y diseño responsive.                                              | SaaS –[https://figma.com](https://figma.com)                                                                                                                                                                          |
| Frontend Dev            | HTML, CSS, JavaScript, Vue                                                                                                                                                        | Construcción de la interfaz web.                                             | [https://vuejs.org/guide/introduction.html](https://vuejs.org/guide/introduction.html)                                                                                                                                 |
| Backend Dev             | C# + ASP.NET Core                                                                                                                                                                 | Implementación de servicios y lógica del backend.                           | [https://learn.microsoft.com/en-us/aspnet/core](https://learn.microsoft.com/en-us/aspnet/core)                                                                                                                         |
| IDE                     | Rider + WebStorm                                                                                                                                                                  | Desarrollo, testing y depuración.                                            | [https://www.jetbrains.com/rider](https://www.jetbrains.com/rider) / [https://www.jetbrains.com/webstorm](https://www.jetbrains.com/webstorm)                                                                             |
| Code Standards          | Google HTML/CSS Style Guide, Vue Style Guide, MDN Guidelines, W3C JavaScript Style Guide, Google JavaScript Style Guide, C# Coding Conventions, Microsoft ASP.NET Core Guidelines | Aplicación de buenas prácticas de desarrollo en frontend y backend.         | [https://developer.mozilla.org/](https://developer.mozilla.org/) / [https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style) |
| Version Control         | Git + GitHub                                                                                                                                                                      | Control de versiones y trabajo colaborativo.                                  | SaaS –[https://github.com](https://github.com)                                                                                                                                                                        |
| Software Deployment     | Github pages                                                                                                                                                                      | Despliegue continuo de la aplicación para ambientes de prueba y validación. | SaaS –[https://railway.app](https://railway.app) / [https://render.com](https://render.com)                                                                                                                              |
| Software Documentation  | Swagger                                                                                                                                                                           | Documentación técnica del sistema y pruebas de API.                         | SaaS –[https://swagger.io/](https://swagger.io/)                                                                                                                                                                      |

### 5.1.2 Source Code Management

En esta sección el equipo establece los medios y esquema de organización que aplicará para el seguimiento de modificaciones. Para ello se utilizará **GitHub** como plataforma y sistema de control de versiones.

A continuación se indican los URLs de los repositorios de GitHub para cada producto:

- **Landing Page**: [https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-landing](https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-landing)
- **Frontend Web Application**: [https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-frontend](https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-frontend)

### GitFlow Workflow

Se implementará el modelo de ramificación propuesto por Vincent Driessen en su artículo *“A successful Git branching model”*, conocido como **GitFlow**. Este modelo organiza el trabajo en las siguientes ramas:

- `main`: Rama principal, contiene siempre el código en producción.
- `develop`: Rama de desarrollo principal, donde se integran las funcionalidades antes de pasar a producción.
- `feature/*`: Ramas creadas a partir de `develop` para desarrollar nuevas funcionalidades.**Convención de nombres:** `feature/<nombre-corto-descriptivo>`_Ejemplo: `feature/login-auth`_
- `release/*`: Ramas creadas desde `develop` cuando se prepara una nueva versión para producción.**Convención de nombres:** `release/<versión>`_Ejemplo: `release/1.2.0`_
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

### 5.1.3. Source Code Style Guide & Conventions

#### Frontend (Landing Page - HTML, CSS, JavaScript)

##### Convenciones generales:

- **Idioma**: Todo el código, incluyendo nombres de variables, funciones y clases, está escrito en **inglés**.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.html`, `.css`, `.js`
- **Estilo de código adoptado**:
  - [W3Schools HTML Style Guide](https://www.w3schools.com/html/html5_syntax.asp)
  - [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

##### Nomenclatura:

- **Clases CSS**: `kebab-case` (ej. `main-container`)
- **IDs HTML**: `camelCase` (ej. `mainContent`)
- **Variables JS**: `camelCase` (ej. `userName`)
- **Funciones JS**: `camelCase` (ej. `handleClick()`)

#### Frontend Web App (Vue.js + JavaScript)

##### Convenciones generales:

- **Idioma**: Código completamente en **inglés**.
- **Estructura de carpetas**: Segregación por módulos y componentes.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.vue`, `.js`, `.css`

##### Estilo de código adoptado:

- Vue.js Style Guide (Oficial): https://vuejs.org/guide/reusability/style-guide.html
- Airbnb JavaScript Style Guide: https://github.com/airbnb/javascript

##### Nomenclatura:

- **Componentes Vue**: `PascalCase` (ej. `UserProfile.vue`)
- **Variables y funciones JS**: `camelCase` (ej. `userName`, `handleSubmit()`)
- **Archivos**: `kebab-case` (ej. `user-profile.vue`)
- **Props**: `camelCase` en JavaScript, `kebab-case` en templates HTML (ej. prop: `userProfile`, uso: `user-profile`)
- **Eventos personalizados**: `kebab-case` (ej. `user-logged-in`)
- **Clases CSS**: `kebab-case`

---

#### Backend (ASP.NET + C#)

##### Convenciones generales:

- **Idioma**: Código y documentación interna en **inglés**.
- **Indentación**: 4 espacios.
- **Formato de archivos**: `.cs`

##### Estilo de código adoptado:

- [Microsoft C# Coding Conventions](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions): https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions
- ASP.NET Core Best Practices: https://learn.microsoft.com/en-us/aspnet/core/fundamentals/index

##### Nomenclatura:

- **Clases**: `PascalCase` (ej. `UserService`)
- **Métodos**: `PascalCase` (ej. `GetUserById()`)
- **Variables locales**: `camelCase` (ej. `userRepository`)
- **Constantes**: `PascalCase` o `UPPER_SNAKE_CASE` (según si es `const` o `readonly static`) (ej. `MaxUsers`)
- **Interfaces**: `IPascalCase` (ej. `IUserRepository`)
- **Endpoints (URLs)**: `kebab-case` (ej. `/api/user-profile`)
- **Namespaces**: `PascalCase` y estructurados jerárquicamente (ej. `ProjectName.ModuleName.FeatureName`)

### 5.1.4. Software Deployment Configuration

Esta sección detalla los pasos necesarios para desplegar de forma satisfactoria los productos digitales que componen la solución: el landing page, la aplicación web (frontend) y los Web Services (backend), partiendo desde sus respectivos repositorios de código fuente.

**1. Landing Page – HTML, CSS y JavaScript**

**Tecnología Base**

- Lenguajes: HTML5, CSS3, JavaScript
- Hosting: GitHub Pages

**Configuración y Despliegue**

*Repositorio de Código Fuente:*
La Landing Page se desarrolla utilizando HTML, CSS y JavaScript puro. Todos los archivos del proyecto deben subirse a un repositorio público en GitHub. Es obligatorio que el archivo `index.html` esté ubicado en la raíz del repositorio (`/`) para que GitHub Pages lo detecte correctamente como punto de entrada del sitio.

*Pasos de despliegue en GitHub Pages:*

1. Acceder al repositorio en GitHub.
2. Ir a la sección **Settings** del repositorio.
3. En el menú lateral, seleccionar **Pages**.
4. En el campo **Source**, elegir:
   - Rama: `main`
   - Carpeta: `/ (root)`
5. Guardar los cambios.

*Publicación:*
GitHub generará automáticamente una URL pública donde la Landing Page estará disponible, con el formato:
`https://<usuario>.github.io/<repositorio>/`

*Actualizaciones:*
Cualquier nuevo commit en la rama `main` será desplegado automáticamente por GitHub Pages, sin necesidad de acciones adicionales.

**2. Frontend Web Application – Vue**

**Tecnología Base**

- Framework: Vue 3
- Build Tool: Vite / Vue CLI (`npm run build`)
- Hosting: GitHub Pages

**Configuración y Despliegue**

*Repositorio de Código Fuente:*
El proyecto frontend está alojado en GitHub. El directorio de salida del build (`/dist`) contiene los archivos que deben ser publicados.

*Build:*
Se ejecuta el comando:

```bash
npm run build
```

Esto genera los archivos estáticos listos para producción.

*Despliegue en GitHub Pages:*
Para publicar el contenido del directorio `/dist` en GitHub Pages, se puede usar la herramienta `gh-pages` (npm) o realizar el despliegue manual mediante una rama `gh-pages`. También se puede configurar una acción de GitHub Actions para automatizar el proceso.

*Variables de entorno:*
Las URLs de los servicios REST del backend están configuradas como variables de entorno (por ejemplo, `VITE_API_URL`) y no están hardcodeadas.

*Entornos diferenciados:*

- Desarrollo: Vue se ejecuta localmente (`npm run dev`) apuntando a un entorno de backend local.
- Producción: El entorno de producción utiliza las variables definidas para apuntar al backend desplegado en Render.

*Integración con backend:*
La aplicación consume servicios expuestos por el backend a través de HTTP, usando los endpoints públicos definidos en la API REST.

**3. Web Services – C# ASP.NET 9.0**

**Tecnología Base**

- Framework: ASP.NET Core 9.0
- Lenguaje: C#
- Build Tool: `dotnet build`
- Contenedorización: Docker
- Base de datos: MySQL (freesqldatabase.com)
- Hosting: Render

**Configuración y Despliegue**

*Contenerización:*
El proyecto backend contiene un archivo `Dockerfile` que define la imagen Docker a construir. Esta imagen se utiliza en Render para ejecutar la aplicación como contenedor.

*Repositorio vinculado:*
El servicio está vinculado directamente a un repositorio GitHub desde Render. Al detectar el `Dockerfile`, Render construye y despliega automáticamente la imagen.

*Build:*
Render ejecuta el proceso de build con:

```bash
dotnet build  
```

seguido del `dotnet run` o comandos equivalentes para levantar el servidor.

*Variables de entorno:*En Render se configuran las credenciales necesarias para conectarse a la base de datos MySQL remota. Las variables incluyen:

- `DB_HOST`
- `DB_PORT`
- `DB_NAME`
- `DB_USERNAME`
- `DB_PASSWORD`

*Acceso a la base de datos:*
Se usa una base de datos MySQL alojada en freesqldatabase.com. La conexión se configura a través del archivo `appsettings.json` o `appsettings.Production.json`, leyendo las variables de entorno.

*Exposición de servicios:*
El backend expone una API RESTful consumida por el frontend. Los endpoints siguen convenciones REST y están documentados usando Swagger u OpenAPI si corresponde.

*Deploy automático:*
Cada push en la rama principal del repositorio activa automáticamente un nuevo despliegue en Render, sin necesidad de configurar pipelines adicionales.

## 5.2 Landing Page, Services & Applications Implementation

### 5.2.1 Sprint 1

#### 5.2.1.1. Sprint Planning 1

A continuación, se presenta la planificación correspondiente a nuestro Sprint 1, el cual tiene como enfoque principal el desarrollo de la landing page de Restock. En esta etapa inicial, el equipo definió el objetivo del sprint, seleccionó las historias de usuario más relevantes y estableció los entregables clave que permitirán construir una primera versión funcional y visualmente atractiva de la página. Esta planificación busca asegurar un entendimiento compartido entre todos los miembros del equipo y sentar las bases para comunicar eficazmente el valor de la plataforma a los usuarios potenciales.

| Sprint #                             | Sprint 1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint Planning Background** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Date                                 | 2025-04-23                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Time                                 | 19:00 pm (GMT-5)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Location                             | Modalidad remota mediante la plataforma Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Prepared By                          | Shapiama Rivera, Gabriela Nicole                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Attendees (to planning meeting)      | Avendaño Balarezo, Williams Eduardo / Castro Alejos / Julio, Guerra Perez, José Jahaziel / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole                                                                                                                                                                                                                                                                                                                                                                          |
| Sprint 0 Review Summary              | Dado que este es el sprint inicial, no se presenta un resumen del sprint anterior.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Sprint 0 Retrospective Summary       | Dado que este es el sprint inicial, no se presenta una retroalimentación del sprint anterior.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Sprint Goal & User Stories** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sprint 1 Goal                        | Nos enfocamos en implementar la estructura principal y las funcionalidades clave de la landing page pública de Restock.<br />Creemos que esto aportará una percepción más sólida del producto y despertará mayor interés entre los usuarios potenciales, al comunicar de forma clara el valor y los beneficios de la plataforma.<br />Esto se confirmará cuando los visitantes puedan navegar de manera fluida por la página, comprendan fácilmente qué ofrece Restock y muestren intención de interactuar o registrarse. |
| Sprint 1 Velocity                    | 18 puntos                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Sum of Story Points                  | 18 puntos                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

#### 5.2.1.2 Aspect Leaders and Collaborators

Durante el Sprint 1, se han definido los principales aspectos a desarrollar, correspondientes a funcionalidades específicas como la visualización de contenido, navegación fluida, adaptabilidad responsiva y gestión de autenticación de usuarios.

Con el objetivo de asegurar una comunicación clara y eficiente dentro del equipo, se elaboró la siguiente matriz de liderazgo y colaboración (LACX), asignando para cada aspecto un líder responsable (L) y colaboradores de apoyo (C).

| Team Member (Last Name, First Name) | GitHub Username    | Questions and Tutorial | About us | Benefits | Testimonials | Contact and Download |
| :---------------------------------- | :----------------- | :--------------------- | :------- | :------- | :----------- | :------------------- |
| Vendaño Balarezo, Williams Eduardo | dev-willy-code     | L                      | C        | C        | C            | C                    |
| Castro Alejos, Julio                | JulioXC4           | C                      | L        | C        | C            | C                    |
| Guerra Perez, José Jahaziel        | jahazielgp         | C                      | C        | L        | C            |                      |
| Guzmán Cabrejos, Yaku Mateo        | yak-cod            | C                      | C        | C        | L            | C                    |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28 | C                      | C        | C        | C            | L                    |

#### 5.2.1.3 Sprint Backlog 1

El objetivo principal de este Sprint es diseñar, implementar y validar las secciones del landing page, asegurando una navegación fluida, una experiencia responsiva en todos los dispositivos y funcionalidades críticas como registro, inicio de sesión y recuperación de contraseña. Se busca garantizar que el usuario final pueda interactuar de manera sencilla y eficiente con la plataforma, mejorando su satisfacción y promoviendo el cumplimiento de los objetivos de negocio.

**Screenshot del Board**

![board-sprint](assets/images/board-sprint.png)
![board-sprint](assets/images/board-sprint-detallado.png)

https://trello.com/b/75YJ9YcB/sprint-backlog-1

<br>

| User Story ID | User Story Title                                                          | Task ID | Task Title   | Task Description                                                                                                                                                                                             | Estimated Hours |
| ------------- | ------------------------------------------------------------------------- | ------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------- |
| US-001        | Ver testimonios de clientes                                               | T001    | US001TASK001 | Diseñar una sección visualmente destacada para testimonios.                                                                                                                                                | 1/2 h           |
|               |                                                                           | T002    | US001TASK002 | Mostrar mínimo tres testimonios con nombre, rol y comentario.                                                                                                                                               | 1h              |
|               |                                                                           | T003    | US001TASK003 | Aplicar estilos consistentes (tipografía, colores, disposición).                                                                                                                                           | 1/2h            |
| US-0002       | Consultar Preguntas Frecuentes                                            | T004    | US002TASK001 | Definir al menos tres preguntas frecuentes con sus respuestas claras y breves.                                                                                                                               | 1/2h            |
|               |                                                                           | T005    | US002TASK002 | Incluir las preguntas y respuestas directamente en el contenido estático de la sección FAQ.                                                                                                                | 1h              |
|               |                                                                           | T006    | US002TASK003 | Verificar que las respuestas estén visibles de forma directa sin necesidad de interacción.                                                                                                                 | 1/2h            |
| US-003        | Consultas directas al equipo de la plataforma                             | T007    | US003TASK001 | Diseñar un formulario limpio con campos de nombre, correo y mensaje.                                                                                                                                        | 1/2h            |
|               |                                                                           | T008    | US003TASK002 | Aplicar validación visual (mensajes de error si faltan datos).                                                                                                                                              | 1h              |
|               |                                                                           | T009    | US003TASK003 | Mostrar un mensaje de confirmación claro tras el envío.                                                                                                                                                    | 1/2h            |
| US-004        | Visualización persistente de información institucional en todo el sitio | T010    | US004TASK001 | Implementar una sección fija en el pie de página con enlaces a redes sociales, contacto y aviso legal.                                                                                                     | 1/2h            |
|               |                                                                           | T011    | US004TASK002 | Crear la sección de "Términos y Condiciones" con contenido legal claro y accesible.                                                                                                                        | 1h              |
|               |                                                                           | T012    | US004TASK003 | Asegurar que la sección de información institucional esté visible en todas las vistas públicas del sitio.                                                                                                | 1/2h            |
| US-005        | Acceso a secciones principales del sitio                                  | T013    | US005TASK001 | Definir y estructurar las rutas internas para las secciones: Inicio, Beneficios, Cómo funciona y Contacto.                                                                                                  | 1/2h            |
|               |                                                                           | T014    | US005TASK002 | Implementar un menú de navegación accesible desde la página principal que enlace a las secciones principales del sitio.                                                                                   | 1h              |
|               |                                                                           | T015    | US005TASK003 | Asegurar que cada enlace de navegación redirija correctamente a su respectiva sección dentro del sitio.                                                                                                    | 1/2h            |
| US-006        | Conocer el funcionamiento general de la plataforma                        | T016    | US006TASK001 | Definir el contenido de las cuatro etapas que explican el funcionamiento general de la plataforma. explicativo'.                                                                                             | 1/2h            |
|               |                                                                           | T017    | US006TASK002 | Estructurar la sección informativa que describa paso a paso cómo utilizar la plataforma.                                                                                                                   | 1h              |
|               |                                                                           | T018    | US006TASK003 | Implementar la visualización de las cuatro etapas de forma secuencial y clara dentro del sitio.                                                                                                             | 1/2h            |
| US-007        | Opción de comprender el funcionamiento mediante recurso audiovisual      | T019    | US007TASK001 | Implementación de estructura necesarios para asegurar que el video explicativo se muestre correctamente                                                                                                     | 1/2h            |
| US-008        | Comprensión del propósito y valor desde el inicio                       | T020    | US008TASK001 | Implementación de estructura necesarios para asegurar que los beneficios se muestren correctamente                                                                                                          | 2h              |
| US-009        | Visualización de beneficios según perfil de usuario                     | T025    | US009TASK001 | Implementación de estructura necesarios para asegurar que los beneficios adaptados a mi perfil se muestre correctamente.                                                                                    | 1/2h            |
| US-011        | Selección de idioma para una experiencia personalizada                   | T028    | US011TASK001 | Preparar el contenido de la landing page y web application en dos idiomas (español e inglés).                                                                                                              | 1h              |
|               |                                                                           | T029    | US011TASK002 | Implementar botón que permita cambiar entre ambos idiomas.                                                                                                                                                  | 1/2h            |
|               |                                                                           | T030    | US011TASK003 | Guardar la selección del idioma para que se mantenga al recargar la página.                                                                                                                                | 1h              |
| US012         | Navegación accesible para personas con discapacidad visual               | T031    | US012TASK001 | Crear diseño visual para 'navegación fluida entre secciones'.                                                                                                                                              | 1/2h            |
|               |                                                                           | T032    | US012TASK002 | Codificar el componente necesario para 'navegación fluida entre secciones'.                                                                                                                                 | 1h              |
|               |                                                                           | T033    | US012TASK003 | Verificar que 'navegación fluida entre secciones' funcione correctamente.                                                                                                                                   | 1/2h            |
| US-013        | Optimización para pantallas de escritorio                                | T034    | US013TASK001 | Definir breakpoint específico para resolución ≥ 1280px en hoja de estilos principal (ej. media queries o framework CSS utilizado)                                                                         | 1/2h            |
|               |                                                                           | T035    | US013TASK002 | Reorganizar layout principal (header, sidebar, content) para aprovechar el espacio horizontal sin superposición ni columnas colapsadas                                                                      | 1h              |
|               |                                                                           | T036    | US013TASK003 | Ajustar tipografía, padding y márgenes para mejorar legibilidad en pantallas grandes                                                                                                                       | 1/2h            |
| US-014        | Optimización para pantallas de tablet                                    | T037    | US014TASK001 | Definir breakpoint específico para resolución ≥ 1024px en hoja de estilos principal (ej. media queries o framework CSS utilizado)                                                                         | 1h              |
|               |                                                                           | T038    | US014TASK002 | Reorganizar layout principal (header, sidebar, content) para aprovechar el espacio horizontal sin superposición ni columnas colapsadas                                                                      | 1/2h            |
|               |                                                                           | T039    | US014TASK003 | Ajustar tipografía, padding y márgenes para mejorar legibilidad en pantallas grandes                                                                                                                       | 1/2h            |
| US-015        | Optimización para dispositivos móviles                                  | T040    | US015TASK001 | Definir breakpoint específico para resolución ≥ 768px en hoja de estilos principal (ej. media queries o framework CSS utilizado)                                                                          | 1/2h            |
|               |                                                                           | T041    | US015TASK002 | Reorganizar layout principal (header, sidebar, content) para optimizar el espacio horizontal                                                                                                                 | 1h              |
|               |                                                                           | T042    | US015TASK003 | Ajustar tipografía, padding y márgenes para mejorar legibilidad en pantallas pequeñas                                                                                                                     | 1/2h            |
| US-016        | Navegación fluida entre secciones                                        | T043    | US016TASK001 | Implementar una experiencia de navegación fluida y sin interrupciones entre las diferentes secciones de la aplicación, garantizando transiciones rápidas, suaves y coherentes con la interfaz de usuario. | 2h              |

#### 5.2.1.4 Development Evidence for Sprint Review

En esta sección se presentan los avances de implementación realizados durante el Sprint 1, el cual tuvo como objetivo principal construir la Landing Page de la plataforma Restock.
Se desarrollaron múltiples secciones, aplicando principios de diseño responsivo, buenas prácticas de codificación y asegurando consistencia con el estilo visual definido para el proyecto. Los entregables principales de este sprint incluyen la creación de secciones como About Us, Benefits, Testimonials, FAQ, Tutorial, Contact, Footer, además de la implementación de mejoras de SEO, formularios de acceso, y enlaces de descarga.

| Repository                        | Branch                   | Commit Id | Commit Message                                                        | Commit Message Body                                                                      | Commited on (Date) |
| --------------------------------- | ------------------------ | --------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------ |
| GabrielaShapiama/UI-Topic-landing | feature/access           | 936d1db   | feat(access): add access forms.                                       | Implemented the login and registration forms with appropriate field validations.         | 27-04-2025         |
| Yaku Guzman/UI-Topic-landing      | feature/footer-section   | fc81879   | feat(footer-section): add footer section, footer css and icons        | Designed and styled the footer component, added navigation links and social media icons. | 27-04-2025         |
| Yaku Guzman/UI-Topic-landing      | feature/contacto-section | c4988c0   | feat(contacto-section): add contact section, contact css              | Developed the contact form section, added input fields and styling for responsiveness.   | 27-04-2025         |
| Yaku Guzman/UI-Topic-landing      | feature/tutorial-section | 1bda3eb   | feat(tutorial-section): add tutorial section, tutorial css and images | Created the tutorial guide section with step-by-step images and responsive layout.       | 27-04-2025         |
| Williams/UI-Topic-landing         | feature/descargar        | 219e86a   | feat(descargar): adding download section(html,css)                    | Built the download section including download buttons and responsive design.             | 27-04-2025         |
| Williams/UI-Topic-landing         | feature/preguntas        | bf2f8f9   | fix(preguntas): updating frecuent questions(html,css,js)              | Updated the FAQ section to improve its structure, styling, and dynamic functionality.    | 27-04-2025         |
| Williams/UI-Topic-landing         | feature/preguntas        | c2882d0   | feat(preguntas): adding frecuent questions(html,css)                  | Added the frequently asked questions section with collapsible answers.                   | 27-04-2025         |
| Williams/UI-Topic-landing         | feature/testimonios      | 4be7138   | feat(testimonios): adding testimonios(html,css)                       | Developed the testimonials section with client feedback and applied custom styles.       | 27-04-2025         |
| jahazielgg/UI-Topic-landing       | feature/benefits         | 34e3804   | feat(benefits): add benefits section.                                 | Created the benefits section highlighting key features and advantages.                   | 27-04-2025         |
| jahazielgg/UI-Topic-landing       | feature/about-us-section | ac7366b   | feat(about-us): add about us section.                                 | Implemented the about us section including company mission and vision statements.        | 27-04-2025         |
| jahazielgg/UI-Topic-landing       | feature/hero-section     | f9716bd   | feat(hero-section): add hero section.                                 | Built the hero section with main headline, supporting text, and CTA button.              | 27-04-2025         |
| jahazielgg/UI-Topic-landing       | feature/develop          | e10bc23   | chore: initial commit.                                                | Set up the initial project structure and configurations for the landing page.            | 27-04-2025         |
| jahazielgg/UI-Topic-landing       | main                     | 31a94bc   | Initial commit                                                        | Initialized the repository with basic project files.                                     | 27-04-2025         |

##### Productos según alcance del Sprint

###### Landing Page

Durante el Sprint 1 se implementó la Landing Page de Restock. Los principales avances fueron:

- Diseño responsivo adaptado a diferentes tamaños de pantalla.
- Creación de secciones: Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutorial, Contacto y Footer.
- Aplicación de buenas prácticas de accesibilidad (uso de etiquetado semántico, contraste adecuado).
- Optimización inicial para motores de búsqueda (SEO básico) con metaetiquetas y atributos relevantes.
- Implementación de navegación fluida entre secciones mediante anclas y smooth scrolling.
- Validación de compatibilidad en navegadores modernos y dispositivos móviles.

#### 5.2.1.5 Execution Evidence for Sprint Review

A continuación, se presenta el video de la landing page. Este muestra la interacción principal de los usuarios con la plataforma, destacando los flujos de navegación, diseño responsivo y la estructura general de la aplicación.

**Video de landing page:**

[https://shorturl.at/sFmpy](https://shorturl.at/sFmpy)
![Captura del video](assets\images\cap-5\evidence_sprint_1.png)

#### 5.2.1.6 Services Documentation Evidence for Sprint Review

Durante este sprint se completó el diseño e implementación del Landing Page del sistema, el cual forma parte del acceso inicial al sistema y constituye un punto de entrada fundamental para los usuarios. Aunque no se implementaron endpoints tradicionales de tipo REST en este sprint, se documenta a continuación la URL del recurso publicado, junto con evidencia de despliegue, interacción y commits relacionados.

**Descripción del Logro:**

-Implementación del Landing Page estático.

-Deployment del landing page.

##### Recursos del Sprint

| Recurso      | Acción implementada   | Método HTTP | URL / Endpoint                                                 | Link de repositorio                                                |
| ------------ | ---------------------- | ------------ | -------------------------------------------------------------- | ------------------------------------------------------------------ |
| Landing Page | Visualización inicial | GET          | https://aplicaciones-web-curso-upc.github.io/UI-Topic-landing/ | https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-landing.git |

**Documentacion**
Commit 4d6b92f: Initial commit

#### 5.2.1.7. Software Deployment Evidence for Sprint Review.

Durante este Sprint, se realizaron actividades de despliegue de la Landing Page utilizando GitHub Pages como plataforma de hosting. A continuación, se detallan los pasos ejecutados:

1- Se accedió a la sección Settings del repositorio.
Dentro de Pages, se seleccionó la rama (develop) y la carpeta (root) desde la cual GitHub Pages debía publicar el sitio.
Se guardaron los cambios para activar la publicación automática.

![Foto deployment step 1](assets/images/cap-5/step-1.png)

2- por default ya esta activado el https

![Foto deployment step 2](assets/images/cap-5/step-2.png)

3- En la seccion "All workflows" se puede ver que la app se esta deployando.

![Foto deployment step 3](assets/images/cap-5/step-3.png)

4- El landing page fue exitosamente deployado

![Foto deployment step 4](assets/images/cap-5/step-4.png)

5- Se obtuvo y verificó la URL pública proporcionada por GitHub Pages.

![Foto deployment step 5](assets/images/cap-5/step-5.png)

#### 5.2.1.8 Team Collaboration Insights during Sprint

##### Desarrollo de las Actividades de Implementación

Durante el Sprint 1, el equipo de Restock se enfocó en el desarrollo de la **Landing Page**.
Las actividades de implementación se llevaron a cabo de la siguiente manera:

- Se crearon ramas específicas para cada sección o funcionalidad (`feature/[nombre-de-seccion]`), permitiendo un trabajo paralelo organizado.
- Cada miembro del equipo asumió la responsabilidad de desarrollar una o más secciones de la Landing Page.
- Se realizaron commits frecuentes, registrando avances de manera continua y detallada.
- Las funcionalidades desarrolladas se integraron mediante Pull Requests hacia la rama `develop`.
- Se mantuvo una comunicación constante mediante la plataforma Discord para coordinar avances y resolver dudas en tiempo real.
- Se aplicaron buenas prácticas de programación, control de versiones y colaboración en equipo.

Gracias a esta organización, se logró cumplir de manera efectiva el objetivo del sprint, garantizando que todos los integrantes contribuyeran de forma activa en el desarrollo de la Landing Page.

##### Evidencia de Colaboración en GitHub

Se presenta a continuación la captura de los insights del repositorio de GitHub, correspondiente al Sprint 1:

![Captura Insights](assets/images/cap-5/team_ci_3_1.png)

**Insights:**

- **13 Pull Requests** fusionados correctamente.
- **5 autores** contribuyendo al repositorio.
- **76 commits** realizados en el periodo del Sprint.
- Participación activa de todos los miembros asignados al desarrollo de la Landing Page.

### 5.2.2 Sprint 2

#### 5.2.2.1. Sprint Planning 2

| Sprint #                             | Sprint 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint Planning Background** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Date                                 | 2025-05-05                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Time                                 | 07:00 pm (GMT-5)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Location                             | Modalidad remota mediante la plataforma Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Prepared By                          | Guzmán Cabrejos, Yaku Mateo                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Attendees (to planning meeting)      | Avendaño Balarezo, Williams Eduardo / Castro Alejos, Julio / Guerra Perez, José Jahaziel / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sprint 1 Review Summary              | Durante el Sprint 1 se logró implementar casi en su totalidad la Landing Page del sistema Restock, desarrollando secciones clave como el header, footer, sección de beneficios y preguntas frecuentes, así como la integración inicial de estilos globales y tipografía. Quedó faltante la funcionalidad de cambio de idioma, la cual será prioridad para el siguiente sprint. El equipo cumplió con los entregables establecidos, respetando el diseño de mockups y la guía de estilos. Se identificaron oportunidades de mejora en la velocidad de desarrollo y gestión de tiempos.                                                                                                                                                                                                   |
| Sprint 1 Retrospective Summary       | Durante el Sprint 1, el equipo logró avanzar de forma coordinada y efectiva en el desarrollo de la landing page, sin enfrentar mayores dificultades. Cada integrante cumplió puntualmente con las secciones asignadas, lo que permitió avanzar según lo planificado. La adopción de convenciones comunes en el código y el diseño contribuyó a mantener la coherencia del producto y facilitó la integración entre partes. Como mejora para el siguiente sprint, se acordó implementar revisiones diarias (daily reviews) que permitan alinear mejor los avances, detectar bloqueos tempranos y mejorar la comunicación continua entre miembros.                                                                                                                                       |
| **Sprint Goal & User Stories** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Sprint 2 Goal                        | Nuestro enfoque está en  brindar información clara y detallada a los visitantes de la plataforma, así como habilitar la gestión de inventario, configuración de perfil, notificaciones, resumen de datos y gestión deventas para los usuarios del sistema  interno.<br />Creemos que esto proporciona  mayor comprensión del propósito de la solución a los visitantes y mejora la eficiencia operativa de insumos de los administradores de restaurantes y proveedores.<br />Esto se confirmará cuando  los visitantes puedan explorar contenido relevante desde el acceso  público, y los usuarios autenticados naveguen por el panel principal y accedan a los módulos de gestión de inventario, configuración de perfil, notificaciones, resumen de datos y ventas del sistema. |
| Sprint 2 Velocity                    | 45                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Sum of Story Points                  | 42                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

#### 5.2.2.2 Aspect Leaders and Collaborators

##### Aspect Leaders and Collaborators

Durante el Sprint 2,  se ha definido el desarrollo e integración de los módulos principales del frontend de la aplicación web interna  Restock , abarcando funcionalidades clave como la gestión de productos, pedidos, inventario y compras. Estas implementaciones buscan optimizar los procesos internos y mejorar la trazabilidad del inventario, brindando mayor eficiencia a los administradores de restaurantes y su personal.

Con el fin de mantener una coordinación efectiva y una comunicación fluida entre los integrantes del equipo, se estructuró la matriz de liderazgo y colaboración (LACX), donde se asignó un líder (L) encargado de cada funcionalidad y colaboradores (C) que brindan apoyo en su implementación.

<div style="font-size: 0.75em; overflow-x: auto;">

| Team Member (Last Name, First Name) | GitHub Username    | Configuración de perfil | Panel de suscripción | Notificaciones y calificaciones | Registro de ventas | Registro de proveedores | Inventario | Resumen de datos |
| :---------------------------------- | :----------------- | :----------------------- | :-------------------- | :------------------------------ | :----------------- | :---------------------- | :--------- | :--------------- |
| Vendaño Balarezo, Williams Eduardo | dev-willy-code     | C                        | L                     | C                               | C                  | C                       | C          | C                |
| Castro Alejos, Julio                | JulioXC4           | C                        | C                     | C                               | L                  | C                       | L          | C                |
| Guerra Perez, José Jahaziel        | jahazielgg         | C                        | C                     | L                               | C                  | C                       | C          | C                |
| Guzmán Cabrejos, Yaku Mateo        | yak-cod            | C                        | C                     | C                               | C                  | L                       | C          | L                |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28 | L                        | C                     | C                               | C                  | C                       | C          | C                |

</div>

#### 5.2.2.3 Sprint Backlog 2

El objetivo principal de este Sprint es desarrollar la interfaz frontend de los dashboards para **administradores de restaurantes y proveedores**, enfocándose en una estructura clara, navegación eficiente y visualización adecuada de datos críticos.

![Board Sprint 2](assets/images/cap-5/vision-statement-sprint2.png)

Además, se realizaron mejoras en el *landing page*, incluyendo la implementación de un **toggle de idioma** (inglés/español) y la incorporación de **atributos de accesibilidad** como `aria-label` y `lang`, asegurando mayor inclusión y cumplimiento de estándares web.

![Board Sprint Details 2](assets/images/cap-5/sprint-backlog2-2.png)

![Board Sprint Details 2](assets/images/cap-5/sprint-backlog2-1.png)

Trello: [https://shorturl.at/X5KyX](https://shorturl.at/X5KyX)

#### 5.2.2.4 Development Evidence for Sprint Review

En esta sección se presentan los avances realizados durante el Sprint 2, centrado en el desarrollo de los módulos principales de la aplicación web interna de Restock.
El objetivo principal fue implementar funcionalidades claves para la gestión de productos, pedidos, inventario y compras, con el fin de mejorar la eficiencia operativa y la trazabilidad de los recursos dentro de los restaurantes.

Durante este sprint se avanzó en la autenticación de usuarios, el diseño del panel principal y la implementación inicial de tres módulos funcionales clave.

##### Commits Relevantes

| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | bd6c32e | feat(restaurant-analytics): add carrousel. |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | f8d1229 | feat(supplier-analytics): add json server behavior. |  | 16-05-2025 |
| Williams/UI-Topic-frontend | develop | Williams | 36a496a | feat(mock): adding mock.user |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 046f822 | routes: fix routes behavior. |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 37843c2 | chore: fix behavior |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 883367d | fix(restaurant-supplier): fix internal routing. |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 61f2e4b | feat(restaurant-supplier): add restaurant supplier catalog. |  | 16-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | 966f47a | fix(router): rename supplier reviews route to ratings |  | 16-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | af04b7f | feat(router): update user data structure and add role-based routing |  | 16-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 1c01a96 | fix: fix sidebar |  | 16-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | cba3b83 | Update inventory-supply-create-and-edit.component.vue |  | 16-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | 7564e45 | Update inventory-supply-add-and-edit.component.vue |  | 16-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | 6d3c52e | Update inventory.component.vue |  | 16-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 3623ec4 | fix: fix supplies |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 340c7dd | feat(supplier-analytics-route): add supplier analytics route. |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | e225fbd | feat(supplier-analytics): add supplier analytics summary components and page |  | 16-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | a2b2637 | fix(styles): update menu link padding and improve color consistency in styles |  | 16-05-2025 |
| Yaku Guzman/UI-Topic-frontend | develop | Yaku Guzman | 90ff1c4 | feat(restaurant-analytics): add restaurant analytics summary components and page |  | 16-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | e415b5d | fix: fix color |  | 16-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | c7c86df | fix: fix functions |  | 16-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 4fb746f | fix: fix delete function |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 6ad2d54 | fix: fix styles |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | b13e97b | fix: fix styles |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 3c1f216 | fix: fix styles (sidebar, html components) |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 26904fc | chore: folder structure based on bounded context in the project |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 2099c0b | fix: fix add inventory (components) |  | 15-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | e8f17f2 | fix: fix add inventory modal (calendar) |  | 14-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | fd8a1cf | fix: fix inventory management with modal for adding and editing supplies, add search functionality, and connect modal to inventory actions |  | 14-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 0d31b31 | feat: integrate inventory management with modal for adding and editing supplies, add search functionality, and connect modal to inventory actions |  | 13-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 2f7cc13 | feat(inventory): add edit button to supply cards and integrate modal for editing |  | 13-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | 55dbceb | feat(sidebar): restructure app layout with sidebar and router integration |  | 12-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | a2e9a33 | feat(i18n): add language switcher component and update translations for sidebar |  | 12-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | b0d0145 | feat(api): add mock user data with json-server and configure router |  | 12-05-2025 |
| jahazielgg/UI-Topic-frontend | develop | jahazielgg | 5c22699 | feat(user): add user entity, service, and user card component for user data management. |  | 12-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | d787a0c | feat(inventory): implement supplies and inventory management section with modal form and carousel |  | 11-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 458ec4a | feat(inventory): progress on empty state and ingredient creation UI |  | 10-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 3645809 | chore: install dependencies and setup base tooling for Vue project |  | 10-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | 50e43fd | Delete .vscode directory |  | 08-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | 3274b65 | Delete package-lock.json |  | 08-05-2025 |
| JulioXC4/UI-Topic-frontend | develop | JulioXC4 | 7e3e6c0 | chore: create Vue 3 project with Vite |  | 08-05-2025 |
| Julio Castro Alejos/UI-Topic-frontend | develop | Julio Castro Alejos | 5ee5558 | Initial commit |  | 08-05-2025 |

#### 5.2.2.5 Execution Evidence for Sprint Review

A continuación, se presenta el video del frontend de la aplicación web interna. Este demuestra la interacción de los usuarios autenticados con los módulos principales del sistema, incluyendo la navegación por el sidebar, la gestión de productos, el seguimiento de alertas y el control de inventario.

**Video del frontend:**
![Captura del video](assets/images/cap-5/evidence_sprint_2/video_evidence.png)

[https://short-link.me/16eW0](https://short-link.me/16eW0)

#### 5.2.2.6 Services Documentation Evidence for Sprint Review

Durante este Sprint se avanzó en el desarrollo del **frontend interno de Restock**, habilitando múltiples rutas navegables para los usuarios autenticados (administradores de restaurante y proveedores), en una estructura basada en Vue Router, Domain-Driven Design y componentes cargados dinámicamente. Aunque aún no se han documentado endpoints REST con OpenAPI, se despliegan a continuación los recursos navegables disponibles, que forman parte del ecosistema de consumo de servicios web del sistema.

**Descripción del Logro:**

* Finalización del Landing Page e implementación multilenguaje.
* Desarrollo modular del frontend con rutas específicas por rol (restaurante y proveedor).
* Estructura basada en Vue Router, DDD y carga lazy de componentes.
* Integración visual con PrimeVue y buenas prácticas de separación por contextos.

##### Rutas accesibles del sistema (Frontend)

| Recurso / Vista               | Acción implementada                        | Método HTTP | URL relativa                            | Propósito funcional                                   |
| ----------------------------- | ------------------------------------------- | ------------ | --------------------------------------- | ------------------------------------------------------ |
| Landing Page                  | Visualización pública inicial             | GET          | `/` (con redirección de rol)         | Acceso inicial y redirección por tipo de usuario      |
| Supplier Inventory            | Visualización de inventario de proveedor   | GET          | `/dashboard/supplier/inventory`       | Gestión del inventario del proveedor                  |
| Restaurant Inventory          | Visualización de inventario de restaurante | GET          | `/dashboard/restaurant/inventory`     | Control de insumos del restaurante                     |
| Restaurant Summary Overview   | Resumen analítico del restaurante          | GET          | `/dashboard/restaurant/summary`       | Dashboard de datos clave del restaurante               |
| Supplier Summary Overview     | Resumen analítico del proveedor            | GET          | `/dashboard/supplier/summary`         | Dashboard de datos clave del proveedor                 |
| Supplier Catalog (Restaurant) | Catálogo de proveedores                    | GET          | `/dashboard/restaurant/suppliers`     | Visualización y exploración de proveedores           |
| Supplier Detail (Restaurant)  | Detalle de proveedor específico            | GET          | `/dashboard/restaurant/suppliers/:id` | Información detallada del proveedor y su catálogo    |
| Supplier Reviews              | Visualización de calificaciones            | GET          | `/dashboard/supplier/ratings`         | Revisión de calificaciones recibidas por el proveedor |

##### Despliegue de recursos

| Recurso          | Acción implementada   | Método HTTP | URL / Endpoint                                                             | Repositorio                                                                         |
| ---------------- | ---------------------- | ------------ | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Landing Page     | Visualización inicial | GET          | [Landing URL](https://aplicaciones-web-curso-upc.github.io/UI-Topic-landing/) | [UI-Topic-landing](https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-landing.git) |
| Frontend Interno | Navegación por rutas  | GET          | [App URL](https://ui-topic-frontend.vercel.app)                               | [UI-Topic-frontend](https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-frontend)   |

##### Evidencia de interacción

* Video de navegación por módulos del sistema:
  [https://short-link.me/16eW0](https://short-link.me/16eW0)
* Captura de la interfaz en funcionamiento:
  ![Captura del video](assets/images/cap-5/evidence_sprint_2/video_evidence.png)

##### Commits relacionados

| Commit ID   | Descripción                                                                                   | Autor       |
| ----------- | ---------------------------------------------------------------------------------------------- | ----------- |
| `0d31b31` | `feat(inventory): integrate inventory management with modal for adding and editing supplies` | JulioXC4    |
| `61f2e4b` | `feat(restaurant-supplier): add restaurant supplier catalog.`                                | Yaku Guzman |
| `55dbceb` | `feat(sidebar): restructure app layout with sidebar and router integration`                  | jahazielgg  |

#### 5.2.2.7 Software Deployment Evidence for Sprint Review

Durante este Sprint, se realizaron las actividades de despliegue del frontend de la aplicación web desarrollada con Vue 3 y PrimeVue utilizando la plataforma **Vercel**. A continuación, se detallan los pasos ejecutados:

1. Se accedió a [https://vercel.com](https://vercel.com) e inició sesión con una cuenta de GitHub.
   Luego, se seleccionó la opción **"Add New Project"** para importar el repositorio `UI-Topic-frontend`.

![Vercel Deployment Step 1](assets/images/cap-5/evidence_sprint_2/evidence_1.png)

2. Se seleccionó el repositorio `UI-Topic-frontend` y se configuró el proyecto.
   Vercel detectó automáticamente que se trataba de un proyecto Vue 3, por lo que sugirió las configuraciones por defecto para el build.

![Vercel Deployment Step 2](assets/images/cap-5/evidence_sprint_2/evidence_2.png)

3. Se verificaron las configuraciones:

- **Framework**: Vue.js
- **Build Command**: `npm run build`
- **Output Directory**: `dist`

Se procedió a desplegar haciendo clic en **"Deploy"**.

![Vercel Deployment Step 3](assets/images/cap-5/evidence_sprint_2/evidence_3.png)

4. El proceso de build y despliegue fue iniciado por Vercel, mostrando en tiempo real los logs del pipeline.

![Vercel Deployment Step 4](assets/images/cap-5/evidence_sprint_2/evidence_4.png)

5. Una vez finalizado el despliegue, se mostró la URL pública de acceso a la aplicación.
   Se probó exitosamente el funcionamiento de la aplicación en dicha URL.

![Vercel Deployment Step 5](assets/images/cap-5/evidence_sprint_2/evidence_5.png)

[https://ui-topic-frontend.vercel.app/](https://ui-topic-frontend.vercel.app/)

#### 5.2.2.8 Team Collaboration Insights during Sprint.

Se crearon ramas específicas para cada sección o funcionalidad (feature/[nombre-de-seccion]), permitiendo un trabajo paralelo organizado.
Cada miembro del equipo asumió la responsabilidad de desarrollar una o más secciones del Frontend.
Se realizaron commits frecuentes, registrando avances de manera continua y detallada.
Las funcionalidades desarrolladas se integraron mediante Pull Requests hacia la rama develop.
Se mantuvo una comunicación constante mediante la plataforma Discord para coordinar avances y resolver dudas en tiempo real.
Se aplicaron buenas prácticas de programación, control de versiones y colaboración en equipo.

##### **Analíticos de colaboración**

![Team Collaboration Insight](assets/images/cap-5/team_collaboration_insight.png)

##### **Analíticos de commits de GitHub**

![Team Collaboration Insight](assets/images/cap-5/team_collaboration_insight_2.png)

### Recursos del Sprint

| Recurso              | Acción implementada                                | Método HTTP | URL / Endpoint                                                 | Link de repositorio                                             |
| -------------------- | --------------------------------------------------- | ------------ | -------------------------------------------------------------- | --------------------------------------------------------------- |
| Landing Page         | Visualización completa y funcional del landing     | GET          | https://aplicaciones-web-curso-upc.github.io/UI-Topic-landing/ | https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-landing  |
| UI del sistema (WIP) | Avance en el sistema (menú, dashboard, inventario) | GET          | https://ui-topic-frontend.vercel.app/dashboard                 | https://github.com/Aplicaciones-Web-Curso-UPC/UI-Topic-frontend |
|                      |                                                     |              |                                                                |                                                                 |

### 5.2.3. Sprint 3

#### 5.2.3.1. Sprint Planning 3

| Sprint #                             | Sprint 3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint Planning Background** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Date                                 | 2025-06-21                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Time                                 | 08:00 pm (GMT-5)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Location                             | Modalidad remota mediante la plataforma Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Prepared By                          | Guerra Perez, José Jahaziel                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Attendees (to planning meeting)      | Avendaño Balarezo, Williams Eduardo / Castro Alejos, Julio / Guerra Perez, José Jahaziel<br /> / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Sprint 2 Review Summary              | Durante el Sprint 2 se logró una mejora significativa en la experiencia de inicio para nuevos usuarios,<br /> al rediseñar e integrar la landing page con el frontend principal de la aplicación web Restock. Se<br /> avanzó considerablemente en el desarrollo del módulo frontend, incorporando funcionalidades clave <br />como la gestión de inventario, notificaciones, analíticas y suscripciones para los perfiles de administradores <br />y proveedores.<br />El equipo demostró una sólida coordinación y colaboración en la implementación de estos <br />componentes, respetando los lineamientos definidos en la planificación. Como oportunidad de <br />mejora, se identificó la necesidad de fortalecer aún más la alineación del equipo con los objetivos <br />priorizados del sprint, para asegurar una entrega aún más consistente en próximos ciclos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Sprint 2 Retrospective Summary       | Durante el Sprint 2, el equipo mantuvo una comunicación fluida y una coordinación efectiva,<br />lo cual permitió avanzar de forma sólida en varios módulos clave del frontend. La integración <br />continua, las revisiones cruzadas de código y la claridad en las responsabilidades asignadas <br />fueron aspectos destacados que facilitaron un buen ritmo de trabajo.<br />Como oportunidad de mejora, se identificó la necesidad de reforzar el seguimiento y <br />cumplimiento de los objetivos priorizados, así como de mejorar la estimación de tiempos en <br />algunos flujos más complejos. También se mencionó la importancia de alinear aún más los <br />esfuerzos individuales con los objetivos de entrega colectivos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Sprint Goal & User Stories** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Sprint 3 Goal                       | Nuestro enfoque está en presentar de forma efectiva nuestra propuesta de valor a los nuevos visitantes. También, habilitar la gestión de recetas y pedidos, así como mejorar la sección de ventas, para los administradores de restaurantes; incorporar la gestión de órdenes para los proveedores; y, en general, permitir a ambos segmentos realizar el pago de su suscripción. Asimismo, proporcionar, mediante el API de la plataforma, puntos de accesos a los desarrolladores frontend para que implementen funcionalidades relacionadas con gestión de pedidos, ventas, recetas, inventario, perfil y comentarios.<br />Creemos que esto ofrece a los visitantes mayor confianza hacia el equipo de trabajo y les permite conocer mejor la propuesta de valor. Del mismo modo, mejora los flujos de usuario, al permitir la realización de pagos de suscripción; agiliza las operaciones para los administradores de restaurantes, al facilitar la creación y gestión de ventas, la configuración de recetas y la gestión de pedidos; optimiza el tiempo operativo para los proveedores, al permitir el seguimiento de pedidos. Además, permite a los desarrolladores frontend implementar funcionalidades esenciales de forma más eficiente, incluyendo pedidos, ventas, recetas, inventario, perfil y comentarios.<br />Esto se confirmará cuando aumente la cantidad de visitantes que se registren en la plataforma. Del mismo modo, cuando se incremente la cantidad de ordenes, ventas e insumos que registran administradores de restaurantes en la plataforma; aumente el número de insumos registrados y órdenes gestionadas por los proveedores; y se incremente la cantidad de suscripciones por parte de ambos segmentos. Además, cuando los desarrolladores frontend aumenten la cantidad de funcionalidades relacionadas con el pedidos, ventas, recetas, inventario, perfil y comentarios en el frontend. |
| Sprint 3 Velocity                    | 60                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Sum of Story Points                  | 57                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

#### 5.2.3.2. Aspect Leaders and Collaborators.

Durante el Sprint 3,  se ha definido el desarrollo e integración de los módulos principales del frontend de la aplicación web interna  Restock  y del backend, abarcando funcionalidades clave como la gestión de productos, pedidos, inventario y compras. Estas implementaciones buscan optimizar los procesos internos y mejorar la trazabilidad del inventario, brindando mayor eficiencia a los administradores de restaurantes y su personal.

Con el fin de mantener una coordinación efectiva y una comunicación fluida entre los integrantes del equipo, se estructuró la matriz de liderazgo y colaboración (LACX), donde se asignó un líder (L) encargado de cada funcionalidad y colaboradores (C) que brindan apoyo en su implementación.

<div style="font-size: 0.75em; overflow-x: auto;">

| Team Member (Last Name, First Name) | GitHub Username    | Planning | Subscription | Profile | IAM | Analytics | Resource | Monitoring |
| :---------------------------------- | :----------------- | :------- | :----------- | :------ | :-- | :-------- | :------- | :--------- |
| Vendaño Balarezo, Williams Eduardo | dev-willy-code     | C        | L            | L       | L   | C         | C        | C          |
| Castro Alejos, Julio                | JulioXC4           | C        | C            | C       | C   | C         | C        | C          |
| Guerra Perez, José Jahaziel        | jahazielgg         | L        | C            | C       | C   | L         | L        | L          |
| Guzmán Cabrejos, Yaku Mateo        | yak-cod            | C        | C            | C       | C   | C         | C        | C          |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28 | C        | C            | C       | C   | C         | C        | C          |

</div>

#### 5.2.3.3 Sprint Backlog 3

El objetivo principal de este Sprint es consolidar una experiencia funcional completa para los distintos perfiles de usuario dentro de la plataforma Restock. Se prioriza la mejora de la landing page para comunicar eficazmente la propuesta de valor a nuevos visitantes, así como la habilitación de módulos clave como la gestión de ventas, recetas y pedidos para los administradores de restaurantes, y la gestión de órdenes para los proveedores.

Asimismo, se trabajará en la integración del flujo de pagos por suscripción y en la provisión de APIs REST documentadas, permitiendo al equipo frontend consumir endpoints de forma eficiente para construir las vistas requeridas. Este enfoque integral busca mejorar la usabilidad, operatividad y cohesión entre el frontend y backend, facilitando la validación funcional de la plataforma y avanzando hacia su adopción por parte de los usuarios finales.

![Sprint backlog 3](assets/images/cap-5/sprint-backlog3-1.png)

[https://short-link.me/122Hv](https://short-link.me/122Hv)

| User Story ID | User Story Title                                                           | Task ID | Task Title                                                                                                                 | Task Description                                                                                                                                                                                                                                 | Estimated Hours |
| ------------- | -------------------------------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------- |
| US-02         | Recuperación de contraseña                                               | T001    | Diseñar la pantalla de solicitud de recuperación de contraseña'.                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Conectar la pantalla con el endpoint /api/v1/auth/forgot-password.                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Diseñar la pantalla de restablecimiento de contraseña (formulario de nueva contraseña).                                 |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Implementar manejo de tokens inválidos o expirados en el frontend                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Conectar formulario de nueva contraseña con endpoint /api/v1/auth/reset-password                                          |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            |         |                                                                                                                            |                                                                                                                                                                                                                                                  |                 |
| US-03         | Soporte de acceso según estado de suscripción                            | T001    |                                                                                                                            | Consultar el estado de suscripción del usuario al iniciar sesión.                                                                                                                                                                              | 1h              |
|               |                                                                            | T002    | Mostrar o restringir funcionalidades según el estado de suscripción                                                      |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Diseñar una vista de advertencia para usuarios con suscripción vencida o inactiva                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Redirigir o bloquear el acceso a rutas protegidas si el estado no es válido                                               |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T005    | Verificar y actualizar el acceso luego de la renovación                                                                   |                                                                                                                                                                                                                                                  | 1h              |
| US-04         | Gestión manual de stock e insumos                                         | T001    | Implementar interfaz de edición de stock e insumo                                                                         | Diseñar y desarrollar un formulario o sección para que el administrador registre el stock actual, nivel máximo y descuentos manuales. Incluir campos necesarios y diseño validado con UX básico.                                            | 1h              |
|               |                                                                            | T002    | Validar entradas de stock en frontend y backend                                                                            | Agregar validaciones tanto para evitar valores negativos o no numéricos en stock, nivel máximo y descuento. Incluir advertencias o bloqueos según corresponda.                                                                                | 1 h             |
|               |                                                                            | T003    | Desarrollar lógica de actualización de stock                                                                             | Implementar lógica para actualizar el stock de un insumo, aplicando registros nuevos, con control de errores y advertencias.                                                                                                                    | 1h              |
|               |                                                                            | T004    | Registrar compras y actualizar stock                                                                                       | Crear el flujo completo para registrar una compra de insumo: formulario, validaciones, actualización de stock, y registro del costo en historial.                                                                                               | 1h              |
|               |                                                                            | T005    | Manejar mensajes de éxito y error en la interfaz                                                                          | Integrar mensajes visuales para notificar al usuario sobre operaciones exitosas (registro, actualización, descuento) y errores (validaciones, datos faltantes o inválidos).                                                                    | 2h              |
| US-05         | Gestión integral de notificaciones de inventario                          | T001    | Mostrar alertas visuales en listado de inventario                                                                          | Implementar lógica y diseño en la vista de inventario                                                                                                                                                                                          | 1/2h            |
|               |                                                                            | T002    | Integrar bandera de vencimiento                                                                                            | A partir de la fecha de vencimiento de cada insumo, calcular si debe marcarse como próximo a vencer. Mostrar tooltip o badge indicando días restantes si corresponde.                                                                          | 2h              |
|               |                                                                            | T003    | Habilitar y mostrar configuración de notificaciones automáticas                                                          | Agregar en una sección donde el administrador pueda habilitar/deshabilitar las notificaciones automáticas.                                                                                                                                     | 2h              |
|               |                                                                            | T004    | Mostrar aviso en la interfaz si hay notificaciones recientes                                                               | Agregar un componente de notificación que muestre alertas recientes de vencimiento o bajo stock si han sido enviadas.                                                                                                                           | 1h              |
| US-06         | Enviar comentarios y calificaciones sobre pedidos                          | T001    | Crear componente de retroalimentación para pedidos entregados                                                             | Diseñar e implementar un componente reutilizable que permita al administrador de restaurante ver un pedido entregado.                                                                                                                           | 1h              |
|               |                                                                            | T002    | Validar calificación y comentario en frontend                                                                             | Agregar validaciones al formulario de retroalimentación                                                                                                                                                                                         | 1h              |
|               |                                                                            | T003    | Enviar retroalimentación y mostrar confirmación                                                                          | Registrar la retroalimentación asegurándose de enviar el ID del pedido, calificación y comentario.                                                                                                                                            | 1h              |
| US-07         | Gestionar productos en el inventario                                       | T001    | Implementar vista de listado y estados de productos del proveedor                                                          | Crear una vista que muestre todos los productos registrados del proveedor                                                                                                                                                                        | 2h              |
|               |                                                                            | T002    | Crear formulario unificado para registrar y editar productos                                                               | Implementar un formulario reutilizable para crear o editar productos                                                                                                                                                                             | 1h              |
|               |                                                                            | T003    | Integrar acciones CRUD en el catálogo del proveedor                                                                       | Desde la vista del listado: Permitir crear un nuevo producto (abre formulario), Permitir editar un producto existente, Permitir eliminar un producto con confirmación, Permitir activar/desactivar un producto con botones de cambio de estado. | h               |
| US-07         | Gestionar productos en el inventario                                       | T001    | Implementar vista de listado y estados de productos del proveedor                                                          | Crear una vista que muestre todos los productos registrados del proveedor                                                                                                                                                                        | 2h              |
|               |                                                                            | T002    | Crear formulario unificado para registrar y editar productos                                                               | Implementar un formulario reutilizable para crear o editar productos                                                                                                                                                                             | 1h              |
|               |                                                                            | T003    | Integrar acciones CRUD en el catálogo del proveedor                                                                       | Desde la vista del listado: Permitir crear un nuevo producto (abre formulario), Permitir editar un producto existente, Permitir eliminar un producto con confirmación, Permitir activar/desactivar un producto con botones de cambio de estado. | h               |
| US-15         | Actualización manual de estado del inventario                             | T001    | Diseñar pantalla de edición manual de inventario con campos editables por insumo.                                        |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T002    | Implementar la lógica de validación de cantidades ingresadas.                                                            |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Mostrar confirmación visual de inventario actualizado correctamente.                                                      |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T004    | Agregar mensajes de error si los valores ingresados son inválidos.                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Integrar la pantalla a la vista principal de administración de insumos.                                                   |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T006    | Documentar el proceso de actualización manual desde el frontend.                                                          |                                                                                                                                                                                                                                                  | 1h              |
| US-16         | Gestión de ventas                                                         | T001    | Implementar la lógica de validación de insumos disponibles antes de confirmar una venta.                                 |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Integrar el consumo de recetas asociadas para mostrar impacto en insumos.                                                  |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Documentar el flujo de gestión de ventas desde el frontend.                                                               |                                                                                                                                                                                                                                                  | 1h              |
| US-17         | Seguimiento de una orden                                                   | T001    | Diseñar vista para mostrar y seleccionar el estado actual de cada orden.                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar selector gráfico para cambiar el estado (en espera, preparando, en camino, entregado).                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Actualizar colores de la fila de la orden de acuerdo al estado actual.                                                     |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Documentar el flujo visual de seguimiento de una orden.                                                                    |                                                                                                                                                                                                                                                  | 1/2h            |
| US-19         | Visualizar y gestionar ordenes recibidas                                   | T001    | Crear pantalla con listado de órdenes solicitadas (tabla).                                                                |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar modal para actualizar la situación de una orden (aceptado o denegado) y establecer fecha estimada de entrega. |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Permitir ordenamiento por fecha.                                                                                           |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Permitir ordenamiento por fecha.                                                                                           |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T005    | Incluir botón de acceso rápido al detalle de cada orden.                                                                 |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T006    | Actualizar automáticamente lista si hay cambios recientes.                                                                |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T007    | Documentar funcionalidad de visualización y gestión de órdenes.                                                         |                                                                                                                                                                                                                                                  | 1h              |
| US-20         | Visualizar información específica de una orden                           | T001    | Diseñar vista detallada que muestre todos los campos de una orden (ítems, cantidades, cliente, etc.).                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar navegación desde listado general a detalle de orden.                                                          |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Mostrar estado actual y fecha estimada de entrega.                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Agregar sección para observaciones o notas de la orden.                                                                   |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T005    | Documentar visualización específica de orden por ID.                                                                     |                                                                                                                                                                                                                                                  | 1h              |
| US-21         | Visualizar historial de órdenes por restaurante                           | T001    | Crear sección que agrupe órdenes completadas por restaurante.                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Permitir búsqueda de restaurante por nombre.                                                                              |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Mostrar las órdenes en orden cronológico según se prefiera.                                                             |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Incluir detalles básicos como fecha, monto y estado.                                                                      |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Implementar paginación para historial largo.                                                                              |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T006    | Documentar flujo del historial por restaurante.                                                                            |                                                                                                                                                                                                                                                  | 1h              |
| US-22         | Descargar reportes de historial de órdenes cumplidas                      | T001    | Diseñar botón de exportación en pantalla de historial.                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Solicitar confirmación antes de descargar reporte.                                                                        |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T003    | Dar feedback si la descarga fue exitosa o hubo errores.                                                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Documentar proceso de descarga de reportes desde interfaz.                                                                 |                                                                                                                                                                                                                                                  | 1h              |
| US-23         | Cambio de contraseña                                                      | T001    | Mostrar opción de “Cambiar contraseña” en la configuración de la cuenta                                               |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Validar que la nueva contraseña cumpla con los requisitos de seguridad                                                    |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Verificar coincidencia entre nueva contraseña y su confirmación                                                          |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Enviar solicitud de cambio de contraseña al servidor                                                                      |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Mostrar mensaje de éxito tras el cambio correcto o Mostrar mensaje de error si la contraseña actual es incorrecta        |                                                                                                                                                                                                                                                  | 1h              |
| US-24         | Eliminar cuenta                                                            | T001    | Mostrar opción “Eliminar cuenta” en la configuración del perfil                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Solicitar paso de verificación para confirmar la eliminación                                                             |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Enviar la solicitud de eliminación de cuenta al servidor                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Confirmar visualmente al usuario que la cuenta ha sido borrada.                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Redirigir al usuario a la página de inicio o despedida tras eliminar la cuenta                                            |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-01         | Registro y autenticación de usuarios mediante API RESTful                 | T001    | Diseñar el modelo de usuario y estructura de base de datos                                                                |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T002    | Implementar endpoint /api/v1/auth/register para registro de usuarios                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Implementar endpoint /api/v1/auth/login para autenticación                                                                |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Configurar control de errores y middleware de autenticación (JWT)                                                         |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-02         | Recuperar contraseña mediante API RESTful usando Resend                   | T001    | Diseñar e implementar el endpoint /api/v1/auth/forgot-password                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Integrar servicio de correo Resend para envío del enlace de recuperación                                                 |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Implementar lógica de manejo de errores y respuestas HTTP estándar                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Crear y almacenar tokens seguros de recuperación de contraseña                                                           |                                                                                                                                                                                                                                                  | 1h              |
| TS-03         | Gestión del estado de suscripción mediante API RESTful                   | T001    | Diseñar el modelo de suscripción de la base de datos                                                                     |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar endpoint GET /api/v1/subscription/status/:id                                                                   |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Implementar endpoint POST /api/v1/subscription/renew                                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Agregar middleware o función auxiliar para evaluar el estado de la suscripción                                           |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-04         | Sistema de notificaciones de inventario mediante API RESTful               | T001    | Implementar endpoint /api/v1/notifications/expiring-supplies                                                               |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar endpoint /api/v1/notifications/exceeding-stock                                                                 |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Diseñar y aplicar lógica de dominio para filtros de notificaciones                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Escribir pruebas unitarias para lógica de notificaciones                                                                  |                                                                                                                                                                                                                                                  | 2h              |
| TS-05         | Gestión de proveedores mediante API RESTful                               | T001    |                                                                                                                            |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-06         | Gestionar insumos  mediante API RESTful                                    | T001    | Implementar endpoint GET /api/v1/supplies/:id (Listar insumos del proveedor)                                               |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar endpoint POST /api/v1/supplies (Crear nuevo insumo)                                                            |                                                                                                                                                                                                                                                  | h               |
|               |                                                                            | T003    | Implementar endpoint PUT /api/v1/supplies/{id} (Actualizar insumo)                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Implementar endpoint DELETE /api/v1/productos/{id} (Eliminar insumo)                                                       |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T005    | Implementar endpoint PATCH /api/v1/productos/{id}/estado (Cambiar estado del insumo)                                       |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T006    | Validación y manejo de errores para creación y actualización                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T007    | Implementar pruebas unitarias para todos los endpoints                                                                     |                                                                                                                                                                                                                                                  | 2h              |
| TS-07         | Registrar comentarios y calificaciones sobre pedidos mediante API RESTful  | T001    | Implementar endpoint POST /api/v1/feedback (Registrar retroalimentación)                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Validar calificación y comentario en POST /api/v1/feedback                                                                |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Validar estado del pedido antes de aceptar feedback                                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Asociar retroalimentación al proveedor correspondiente                                                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Implementar pruebas unitarias del endpoint                                                                                 |                                                                                                                                                                                                                                                  | 1h              |
| TS-08         | Registro histórico de eventos críticos de insumos                        | T001    | Crear colección supply_event_logs con campos: supplyId, type, detectedAt, details, severity.                              |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar lógica para detectar condiciones críticas en insumos y registrar evento automáticamente.                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Crear servicio RESTful GET /api/v1/supplies/events con filtros por tipo, insumo y rango de fechas.                         |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Documentar tipos de eventos permitidos: "EXPIRATION_SOON", "LOW_STOCK", "OVERSTOCKED".                                     |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T005    | Agregar pruebas unitarias y de integración para asegurar el correcto registro de eventos críticos.                       |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-09         | Crear recetas mediante API RESTful                                         | T001    | Definir endpoint POST /api/v1/recipes en el controlador                                                                    |                                                                                                                                                                                                                                                  | 2h              |
| TS-12         | Eliminar una receta mediante API RESTful                                   | T001    |                                                                                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Validar campos requeridos en payload (nombre, ingredientes)                                                                |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Crear lógica de persistencia con relación a insumos                                                                      |                                                                                                                                                                                                                                                  | 2 h             |
|               |                                                                            | T005    | Escribir test unitario y de integración para el endpoint                                                                  |                                                                                                                                                                                                                                                  | 1h              |
| TS-13         | Obtener perfil mediante API RESTful                                        | T001    | Implementar endpoint GET /api/v1/profile/:id protegido por JWT                                                             |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T002    | Validar que el token sea correcto antes de procesar la solicitud                                                           |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Consultar y devolver información del perfil (id, nombre, email, URL de imagen, estado)                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Gestionar error 401 en caso de token inválido o expirado                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Escribir test unitario y de integración para el endpoint                                                                  |                                                                                                                                                                                                                                                  | 1h              |
| TS-14         | Actualizar perfil mediante API RESTful                                     | T001    | Implementar endpoint PUT /api/v1/profile/:id con protección por JWT                                                       |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T002    | Validar formato de campos                                                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Actualizar los datos del perfil en la base de datos                                                                        |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Retornar los datos actualizados con código 200                                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Retornar errores 400 con detalles si hay datos inválidos                                                                  |                                                                                                                                                                                                                                                  | 1h              |
| TS-15         | Subir imagen de perfil mediante API RESTful usando Cloudinary              | T001    | Implementar endpoint POST /api/v1/profile/images/id.                                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Validar formato de archivo antes de subir (JPG, PNG, WEBP)                                                                 |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Asociar la URL retornada por Cloudinary al usuario correspondiente                                                         |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Manejar errores por formato no soportado (415)                                                                             |                                                                                                                                                                                                                                                  | 1h              |
| TS-16         | Obtener lista para ingredientes más usados mediante API RESTful           | T001    | Implementar endpoint GET /api/v1/ingredients/most-used                                                                     |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Permitir parámetro ?period= con valores como 7d o 30d                                                                     |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Consultar datos agregados de ingredientes en base al periodo                                                               |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T004    | Retornar JSON con lista de ingredientes, id, nombre y cantidad_utilizada                                                   |                                                                                                                                                                                                                                                  | 2h              |
| TS-17         | Obtener lista de alertas recientes  mediante API RESTful                   | T001    | Implementar endpoint GET /api/v1/alerts                                                                                    |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T002    | Clasificar alertas por tipo: vencimiento, bajo stock, etc                                                                  |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Retornar lista de alertas como JSON                                                                                        |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Retornar lista vacía si no hay alertas activas                                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Implementar filtros para pruebas                                                                                           |                                                                                                                                                                                                                                                  | 1h              |
| TS-18         | Obtener lista de mejores clientes mediante API RESTful                     | T001    | Implementar endpoint GET /api/v1/supplier/top-clients                                                                      |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T002    | Consultar base de datos y ordenar clientes por total de compras                                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Retornar JSON con campos: nombre_restaurante, total_compras                                                                |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Agregar validación de fechas y manejo de errores                                                                          |                                                                                                                                                                                                                                                  | 1h              |
| TS-19         | Actualizar estado de orden mediante API RESTful                            | T001    | Crear endpoint para cambiar estado de una orden por ID.                                                                    |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T002    | Aplicar lógica de seguridad (autenticación y permisos).                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Manejar errores de estado inválido o inexistente.                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Escribir pruebas para transiciones de estado comunes.                                                                      |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T005    | Documentar API de actualización de estado de órdenes.                                                                    |                                                                                                                                                                                                                                                  | 2h              |
| TS-20         | Consultar estado de entrega mediante API RESTful                           | T001    | Crear endpoint para obtener estado actual de una orden.                                                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar control de acceso para proveedor o restaurante.                                                                |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Optimizar respuesta solo con campos necesarios (estado, fecha).                                                            |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Manejar errores si orden no existe.                                                                                        |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T005    | Escribir pruebas unitarias del endpoint.                                                                                   |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T006    | Documentar consulta del estado de entrega por ID.                                                                          |                                                                                                                                                                                                                                                  | 1h              |
| TS-21         | Obtener calificaciones de servicios de proveedores mediante API RESTful    | T001    | Crear endpoint para obtener calificaciones por proveedor ID.                                                               |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Incluir datos como puntuación, comentario, fecha.                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Agregar orden cronológico o filtros si se requiere.                                                                       |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Validar existencia del proveedor y autorización del solicitante.                                                          |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Diseñar pruebas para distintos escenarios (sin calificaciones, múltiples).                                               |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T006    | Documentar la API de calificaciones del proveedor.                                                                         |                                                                                                                                                                                                                                                  | 2h              |
| TS-22         | Gestionar órdenes recibidas mediante API RESTful                          | T001    | Crear endpoint para listar órdenes recibidas por proveedor.                                                               |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Agregar filtros por estado, fecha o restaurante.                                                                           |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Manejar errores y datos faltantes en las solicitudes.                                                                      |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Probar la gestión completa de órdenes.                                                                                   |                                                                                                                                                                                                                                                  | h               |
|               |                                                                            | T005    | Documentar endpoints RESTful para gestión de órdenes recibidas.                                                          |                                                                                                                                                                                                                                                  | 1h              |
| TS-23         | Consultar detalles de una orden mediante API RESTful                       | T001    | Crear endpoint para obtener datos completos de una orden por ID.                                                           |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T002    | Validar existencia de la orden y su pertenencia al proveedor.                                                              |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Incluir ítems, cantidades, fecha de creación, cliente, etc.                                                              |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Escribir pruebas para orden encontrada y no encontrada.                                                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Documentar la estructura de respuesta y ejemplos de consulta.                                                              |                                                                                                                                                                                                                                                  | 1h              |
| TS-24         | Obtener historial de ordenes mediante API RESTful                          | T001    | Crear endpoint que devuelva órdenes de un proveedor agrupadas por restaurante.                                            |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Ordenar por fecha de forma descendente.                                                                                    |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Permitir incluir filtros como fechas o estado.                                                                             |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Validar autenticación y permisos del proveedor.                                                                           |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Documentar endpoint de historial cronológico de órdenes.                                                                 |                                                                                                                                                                                                                                                  | 2h              |
| TS-25         | Exportar reporte de historial de órdenes completados mediante API RESTful | T001    | Crear endpoint para generar archivo Excel del historial de órdenes completadas.                                           |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Permitir parámetros de filtrado (fechas, restaurantes).                                                                   |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Formatear columnas y contenido de forma clara y legible.                                                                   |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T004    | Asegurar que el archivo se descargue correctamente.                                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Probar el export en distintos navegadores/sistemas.                                                                        |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T006    | Documentar generación y descarga del reporte Excel.                                                                       |                                                                                                                                                                                                                                                  | 1/2h            |
| TS-26         | Gestionar ventas e inventario mediante API RESTful                         | T001    | Crear endpoints para registrar ventas.                                                                                     |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Implementar lógica de validación y verificación de stock antes de registrar una venta en el inventario.                 |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T003    | Crear endpoint para actualizar manualmente el inventario.                                                                  |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Aplicar manejo de errores para transacciones inválidas o datos incompletos.                                               |                                                                                                                                                                                                                                                  | 1/2h            |
|               |                                                                            | T005    | Diseñar pruebas unitarias y de integración para ambos endpoints.                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T006    | Documentar los endpoints RESTful de ventas.                                                                                |                                                                                                                                                                                                                                                  | 1h              |
| TS-27         | Cambio de contraseña mediante API RESTful                                 | T001    | Crear endpoint seguro /api/v1/auth/change-password                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Diseñar estructura del cuerpo de la solicitud                                                                             |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Implementar validación de entrada                                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Verificar contraseña actual del usuario                                                                                   |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T005    | Actualizar la contraseña en base de datos                                                                                 |                                                                                                                                                                                                                                                  | 1h              |
| TS-28         | Eliminar cuenta mediante API RESTful                                       | T001    | Crear endpoint seguro /api/v1/auth/delete-account                                                                          |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T002    | Diseñar estructura del cuerpo de la solicitud                                                                             |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T003    | Validar autenticación del usuario                                                                                         |                                                                                                                                                                                                                                                  | 1h              |
|               |                                                                            | T004    | Eliminar o desactivar la cuenta del usuario                                                                                |                                                                                                                                                                                                                                                  | 2h              |
|               |                                                                            | T005    | Revocar tokens activos y sesiones                                                                                          |                                                                                                                                                                                                                                                  | 1/2h            |

#### 5.2.3.4 Development Evidence for Sprint Review

En esta sección presentamos la evidencia de desarrollo correspondiente al Sprint, en forma de commits registrados en los distintos módulos del backend de la plataforma Restock.

Cada entrada refleja avances funcionales importantes realizados por el equipo, incluyendo la implementación de agregados, comandos, endpoints, configuración del entorno, y mejoras en la estructura del código.

| Repository                         | Branch  | Commit Id | Commit Message                                                                                                                | Commit Message Body | Commited on (Date) |
| ---------------------------------- | ------- | --------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------- | ------------------ |
| Julio Castro/restock-platform      | develop | 28992e7   | feat(domain): create CustomerSupply aggregate and constructor from command                                                    |                     | 22-06-2025         |
| Julio Castro/restock-platform      | develop | 8d2c0a6   | feat(bc-resource): add queries for retrieving batches and supplies                                                            |                     | 22-06-2025         |
| Julio Castro/restock-platform      | develop | ca21492   | feat(bc-resource): implement commands for batch and supply creation and update                                                |                     | 22-06-2025         |
| Gabriela Shapiama/restock-platform | develop | b313d35   | refactor(Program): simplify DbContext configuration and comment out HTTPS redirection                                         |                     | 22-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 04bdc72   | feat(server): configure Kestrel to listen on specified port from environment variable                                         |                     | 22-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 9012237   | feat(configuration): add appsettings for local and production environments                                                    |                     | 22-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 9fd966d   | feat: enhance JSON serialization settings and improve database context configuration                                          |                     | 21-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 322ac8e   | feat(docker): add Dockerfile for building and running CatchUpPlatform.API                                                     |                     | 21-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 000878d   | feat(configuration): update appsettings for production environment and remove token settings                                  |                     | 21-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | 467eb35   | feat(recipe): add AddRecipeSupplyCommand for adding supplies to recipes                                                       |                     | 21-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | a8fbb78   | feat(config): rename appsettings to appsettings.Production.json and update connection string for production environment       |                     | 21-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | 3b07ed2   | feat(recipe): update AddSupplyToRecipe to accept multiple supplies and change supplyId type to int in update/delete endpoints |                     | 20-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | 0a4207b   | feat(recipe): change SupplyId type from Guid to int in recipe supply commands and resources                                   |                     | 20-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | 6c528c4   | feat(recipe): make recipe description optional and update related properties for nullable support                             |                     | 19-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | a49dd6a   | feat(recipe): add endpoints for listing, updating, and deleting recipe supplies; support optional supply inclusion in queries |                     | 18-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | e097162   | feat(recipe): add UpdateRecipeSupplyResource and support optional supply inclusion in assembler                               |                     | 18-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | e3cbd61   | feat(recipe): add command records for updating and deleting recipe supplies                                                   |                     | 18-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | cb9dd37   | feat(recipe): add service methods for updating, deleting, and querying recipe supplies                                        |                     | 18-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | f7e4840   | feat(recipe): extend services and repository to support recipe supply update, delete, and querying                            |                     | 18-06-2025         |
| Jahaziel Guerra/restock-platform   | develop | 1679ec6   | feat(recipe): add endpoint and service logic to add supply to recipe                                                          |                     | 18-06-2025         |
| Yaku Guzman/restock-platform       | develop | 5fd1781   | refactor(resource): remove Supplies input from CreateRecipeResource                                                           |                     | 18-06-2025         |
| Yaku Guzman/restock-platform       | develop | df20fbe   | refactor(assembler): remove Supplies mapping from CreateRecipeCommandFromResourceAssembler                                    |                     | 18-06-2025         |
| Julio Castro/restock-platform      | develop | bdcb05a   | refactor(command): remove Supplies input from CreateRecipeCommand and UpdateRecipeCommand                                     |                     | 18-06-2025         |
| Julio Castro/restock-platform      | develop | a102df6   | feat(resource): add AddRecipeSupplyResource record for recipe supply input                                                    |                     | 18-06-2025         |
| Julio Castro/restock-platform      | develop | ac5c718   | feat: update AppDbContext to enforce generic DbContext options and clean up RecipeSupply configuration                        |                     | 17-06-2025         |
| Julio Castro/restock-platform      | develop | 4a3b67d   | feat: refactor Recipe and RecipeSupply entity configurations for improved relationships and clarity                           |                     | 17-06-2025         |
| Julio Castro/restock-platform      | develop | 9460372   | feat: update Recipe and RecipeSupply entities for improved structure and validation                                           |                     | 17-06-2025         |
| Julio Castro/restock-platform      | develop | f1a57dc   | feat(restock): add bounded context folders                                                                                    |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | 99d6426   | feat(resource): add supply entity.                                                                                            |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | c7eeb8a   | feat(resource): add order to supplier batch entity.                                                                           |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | 416b45b   | feat(resource): add order to supplier entity.                                                                                 |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | dcc3a37   | feat(resource): add order to supplier states value object.                                                                    |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | 63f1055   | feat(resource): add order to supplier situations value object.                                                                |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | edbb93b   | feat(resource): add batch entity.                                                                                             |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | dda6d96   | chore: delete  files.                                                                                                         |                     | 14-06-2025         |
| Julio Castro/restock-platform      | develop | a744a30   | feat: improve database initialization and update API documentation for recipes                                                |                     | 13-06-2025         |
| Yaku Guzman/restock-platform       | develop | 656fcc5   | feat: add token settings and default connection string to appsettings.json                                                    |                     | 13-06-2025         |
| Yaku Guzman/restock-platform       | develop | d6ace92   | feat: refactor Recipe and RecipeSupply entity configurations for improved clarity and consistency                             |                     | 13-06-2025         |
| Yaku Guzman/restock-platform       | develop | e7c681f   | feat: update connection string and upgrade package versions in project files                                                  |                     | 13-06-2025         |
| Yaku Guzman/restock-platform       | develop | 5abad19   | feat: add Recipe and RecipeSupply entities with EF Core configuration                                                         |                     | 13-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 212fcef   | feat: change SupplyIdentifier to a record for improved immutability                                                           |                     | 13-06-2025         |
| Gabriela Shapiama/restock-platform | develop | cba2e4a   | feat: add RecipesController for managing recipe operations                                                                    |                     | 13-06-2025         |
| Gabriela Shapiama/restock-platform | develop | db32ad2   | feat: add RecipeRepository for managing recipe data persistence                                                               |                     | 13-06-2025         |
| Gabriela Shapiama/restock-platform | develop | af64949   | feat: implement RecipeCommandService and RecipeQueryService for recipe management                                             |                     | 13-06-2025         |
| Gabriela Shapiama/restock-platform | develop | 0790773   | feat: add resource and assembler classes for creating and transforming recipe data                                            |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | 567ab3b   | feat: refactor query classes to use concise syntax                                                                            |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | 3f13be2   | feat: add IRecipeCommandService and IRecipeQueryService interfaces for recipe management                                      |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | f2e9aba   | feat: rename RecipeAggregate to Recipe and enhance supply management methods                                                  |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | dce53a2   | feat: add IRecipeRepository interface for managing recipe data operations                                                     |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | c954b04   | feat(planning): add commands for creating, updating, and deleting recipes with supply management                              |                     | 13-06-2025         |
| William Avendaño/restock-platform | develop | 0ec9a0e   | feat: update README and rename Ingredient to Supply for clarity                                                               |                     | 10-06-2025         |
| William Avendaño/restock-platform | develop | 4a559f5   | feat: add RecipeSupply entity for managing supply identifiers and quantities                                                  |                     | 10-06-2025         |
| William Avendaño/restock-platform | develop | f92c44f   | feat: enhance RecipeAggregate with properties and supply management methods                                                   |                     | 10-06-2025         |
| William Avendaño/restock-platform | develop | 537ec3d   | feat: add IRecipeService interface for handling recipe commands                                                               |                     | 10-06-2025         |
| William Avendaño/restock-platform | develop | e666b24   | feat: add command classes for updating recipes and supplies                                                                   |                     | 10-06-2025         |
| Jahaziel/restock-platform          | develop | fd5189e   | feat: add query classes for retrieving recipes and supplies by user and ID                                                    |                     | 10-06-2025         |
| Jahaziel/restock-platform          | develop | 2e46c52   | feat: add EUnitMeasurement value object for representing unit measurements                                                    |                     | 10-06-2025         |
| Jahaziel/restock-platform          | develop | e099f32   | feat: add ECategories value object for managing recipe categories                                                             |                     | 10-06-2025         |
| Jahaziel/restock-platform          | develop | 3d4d897   | feat: rename RecipeName to RecipeIdentifier and add new value objects for RecipeImageURL, RecipePrice, and RecipeQuantity     |                     | 10-06-2025         |
| Julio-Castro/restock-platform      | develop | 1f61a76   | feat: add command classes for managing supplies and recipes in the domain model                                               |                     | 10-06-2025         |
| Julio-Castro/restock-platform      | develop | 3f23e35   | feat: add folders for Commands and Queries in the domain model                                                                |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | 91ae3a7   | feat: add Recipe class to represent recipe entities with properties and ingredients                                           |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | 00f6d90   | feat: add RecipeName value object to represent recipe names                                                                   |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | 4a43ace   | feat: add methods to manage ingredients in Recipe class                                                                       |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | cc1745c   | feat: add RecipeAggregate class to manage recipe entities                                                                     |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | 4037890   | feat: add Ingredient, IngredientName, and IngredientQuantity entities                                                         |                     | 07-06-2025         |
| Julio-Castro/restock-platform      | develop | 6e7fbad   | chore: initial commit                                                                                                         |                     | 03-06-2025         |
| Jahaziel/restock-platform          | develop | f629fef   | chore: initial commit                                                                                                         |                     | 03-06-2025         |

#### 5.2.3.5. Execution Evidence for Sprint Review

A continuación, se muestra un video con los avances realizados durante el Sprint 3, en el cual se trabajó en la landing page, así como en el desarrollo del frontend y backend.

**Video del sprint 3:**
![Captura del video](assets/images/cap-5/evidence_sprint_3.png)
[https://shorturl.at/V5zDA](https://shorturl.at/V5zDA)

#### 5.2.3.6. Services Documentation Evidence for Sprint Review.

#### 5.2.3.7. Software Deployment Evidence for Sprint Review

Durante este sprint, se realizaron actividades de despliegue y pruebas de los servicios desarrollados, asegurando que las funcionalidades del sistema estén operativas y accesibles para los usuarios finales. A continuación, se detallan los pasos realizados:

1. Dockerfile: Se creó un Dockerfile para el backend del sistema, permitiendo la creación de una imagen que encapsula todas las dependencias y configuraciones necesarias para ejecutar el servicio.

![Evidence Step 0](assets/images/cap-5/evidence-sprint3/evidence-step0.png)

2. Iniciar un servicio en Render: Se creó un nuevo servicio en Render para el backend.

![Evidence Step 1](assets/images/cap-5/evidence-sprint3/evidence-step1.png)

3. Configurar el servicio: Se configuró el servicio en Render, especificando el nombre del servicio, la región y el tipo de instancia.

![Evidence Step 2](assets/images/cap-5/evidence-sprint3/evidence-step2.jpg)

4. Variables de entorno: Se añadieron las variables de entorno necesarias para la configuración del servicio, como las credenciales de la base de datos y las claves de API.

![Evidence Step 3](assets/images/cap-5/evidence-sprint3/evidence-step3.png)

5. Despliegue del servicio: Se inició el despliegue del servicio en Render, lo que permitió que el backend estuviera disponible en la URL proporcionada.

![Evidence Step 4](assets/images/cap-5/evidence-sprint3/evidence-step4.jpg)

6. Verificación del despliegue: Se verificó que el servicio estuviera funcionando correctamente accediendo a la URL proporcionada por Render.

![Evidence Step 5](assets/images/cap-5/evidence-sprint3/evidence-step5.jpg)

#### 5.2.3.8. Team Collaboration Insights during Sprint

Seguimos usando ramas específicas para cada sección o funcionalidad (feature/[nombre-de-seccion]), permitiendo un trabajo paralelo organizado.

Cada miembro del equipo asumió la responsabilidad de desarrollar una o más boundeds del Backend.
Se realizaron commits frecuentes, registrando avances de manera continua y detallada.
Las funcionalidades desarrolladas se integraron mediante Pull Requests hacia la rama develop.
Se mantuvo una comunicación constante mediante la plataforma Discord para coordinar avances y resolver dudas en tiempo real.
Se aplicaron buenas prácticas de programación, control de versiones y colaboración en equipo.

##### **Analíticos de colaboración**

![Team Collaboration Insight](assets/images/cap-5/team_ci_3_1.png)

##### **Analíticos de commits de GitHub**

![Team Collaboration Insight](assets/images/cap-5/team_ci_3_2.png)

### 5.2.4. Sprint 4

#### 5.2.4.1. Sprint Planning 4

| Sprint #                             | Sprint 4                                                                                                                                                           |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Sprint Planning Background** |                                                                                                                                                                    |
| Date                                 |                                                                                                                                                                    |
| Time                                 | 08:00 pm (GMT-5)                                                                                                                                                   |
| Location                             | Modalidad remota mediante la plataforma Discord                                                                                                                    |
| Prepared By                          |                                                                                                                                                                    |
| Attendees (to planning meeting)      | Avendaño Balarezo, Williams Eduardo / Castro Alejos, Julio / Guerra Perez, José Jahaziel<br /> / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole |
| Sprint 3 Review Summary              | Durante el Sprint 3.,,,,,,,,,,,,,                                                                                                                                  |
| Sprint 3 Retrospective Summary       | Durante el Sprint 3,......................                                                                                                                         |
| **Sprint Goal & User Stories** |                                                                                                                                                                    |
| Sprint 4 Goal                        | Nuestro enfoque                                                                                                                                                    |
| Sprint 4 Velocity                    |                                                                                                                                                                    |
| Sum of Story Points                  |                                                                                                                                                                    |

#### 5.2.4.2. Aspect Leaders and Collaborators.

Durante el Sprint 4, se ha definido el desarrollo de los últimos módulos principales del frontend de la aplicación web interna Restock y del backend, abarcando funcionalidades clave como la gestión de productos, pedidos, inventario y compras. Estas implementaciones buscan optimizar los procesos internos y brindar mayor eficiencia a los administradores de restaurantes y proveedores de restaurantes.

Con el fin de mantener una coordinación efectiva y una comunicación fluida entre los integrantes del equipo, se estructuró la matriz de liderazgo y colaboración (LACX), donde se asignó un líder (L) encargado de cada funcionalidad y colaboradores (C) que brindan apoyo en su implementación.

<div style="font-size: 0.75em; overflow-x: auto;">

| Team Member (Last Name, First Name) | GitHub Username    | Planning | Subscription | Profile | IAM | Analytics | Resource | Monitoring |
| :---------------------------------- | :----------------- | :------- | :----------- | :------ | :-- | :-------- | :------- | :--------- |
| Castro Alejos, Julio                | JulioXC4           | C        | L            | C       | C   | C         | L        | C          |
| Guerra Perez, José Jahaziel        | jahazielgg         | L        | C            | C       | C   | L         | C        | C          |
| Guzmán Cabrejos, Yaku Mateo        | yak-cod            | C        | C            | C       | L   | C         | C        | C          |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28 | C        | C            | L       | C   | C         | C        | L          |

</div>

#### 5.2.4.3. Sprint Backlog 4

#### 5.2.4.4. Development Evidence for Sprint Review

#### 5.2.4.5. Execution Evidence for Sprint Review

#### 5.2.4.6. Services Documentation Evidence for Sprint Review

#### 5.2.4.7. Software Deployment Evidence for Sprint Review

#### 5.2.4.8. Team Collaboration Insights during Sprint

Se crearon ramas específicas para cada sección o funcionalidad (feature/[nombre-de-seccion]), permitiendo un trabajo paralelo organizado.

Cada miembro del equipo asumió la responsabilidad de desarrollar una o más secciones del Landing page, Frontend y Backend.
Se realizaron commits frecuentes, registrando avances de manera continua y detallada.
Las funcionalidades desarrolladas se integraron mediante Pull Requests hacia la rama develop.
Se mantuvo una comunicación constante mediante la plataforma Discord para coordinar avances y resolver dudas en tiempo real.
Se aplicaron buenas prácticas de programación, control de versiones y colaboración en equipo.

**Landing Page**

***Analíticos de colaboración***

Permite visualizar y analizar la participación del equipo en tareas colaborativas, identificando el nivel de actividad y compromiso de cada miembro para optimizar la coordinación y la productividad.

![Team Collaboration Insight](assets/images/cap-5/collaborationLanding.png)

***Analíticos de commits de GitHub***

Muestra el historial y frecuencia de commits realizados en GitHub, ayudando a evaluar el ritmo de desarrollo, la contribución individual y detectar posibles cuellos de botella en el flujo de trabajo.

![Team Collaboration Insight](assets/images/cap-5/collaborationLanding2.png)

**Frontend**

***Analíticos de colaboración***

Permite monitorear de manera detallada la interacción y el aporte de cada miembro en las actividades conjuntas, facilitando la identificación de patrones de trabajo y fomentando una gestión más eficiente del equipo.

![Team Collaboration Insight](assets/images/cap-5/collaborationFrontend.png)

***Analíticos de commits de GitHub***

Presenta un análisis claro del flujo de commits en GitHub, mostrando la frecuencia y volumen de contribuciones para evaluar el progreso del proyecto y detectar áreas que requieren mayor atención o soporte.

![Team Collaboration Insight](assets/images/cap-5/collaborationFrontend2.png)

**Backend**

***Analíticos de colaboración***

Ofrece una vista detallada sobre la participación de cada integrante en las actividades grupales, permitiendo identificar su nivel de implicación y colaboración para mejorar la organización y el rendimiento general del equipo.

![Team Collaboration Insight](assets/images/cap-5/collaborationBackend.png)

***Analíticos de commits de GitHub***

Refleja el registro y la periodicidad de los commits realizados en el repositorio, facilitando el seguimiento del avance del desarrollo, la distribución de las contribuciones y la detección de posibles bloqueos o retrasos.

![Team Collaboration Insight](assets/images/cap-5/collaborationBackend2.png)

### Recursos del Sprint

| Recurso      | Acción implementada                             | Método HTTP | URL / Endpoint                                           | Link de repositorio         |
| ------------ | ------------------------------------------------ | ------------ | -------------------------------------------------------- | --------------------------- |
| Landing Page | Visualización completa y funcional del landing  | GET          | https://restock-4368.github.io/landing-page/             | https://short-link.me/16WRW |
| Frontend     | Visualización completa y funcional del frontend | GET          | https://restock-4368.github.io/UI-Topic-frontend/sign-in | https://short-link.me/16WS3 |
| Backend      | Implementación completa del backend             | GET          | https://short-link.me/12JfP                              | https://short-link.me/16WSe |

## 5.3. Validation Interviews

### 5.3.1. Diseño de Entrevistas

Para garantizar que la aplicación cumpla con las necesidades reales de los usuarios finales, se diseñó un proceso de entrevistas de validación centrado en dos segmentos objetivos clave: **administradores de restaurantes** y **proveedores de insumos**. Cada sesión de validación incluirá interacción con el **Landing Page** y la **aplicación web** (desktop y mobile), siguiendo flujos de usuario específicos que cubren funcionalidades críticas del sistema.

## Objetivo General

Validar la usabilidad, comprensión y utilidad de las funcionalidades del sistema a través de sesiones controladas de interacción, aplicando principios de evaluación heurística y recogiendo observaciones cualitativas.

## Segmento 1: Administradores de Restaurantes

### Elementos a validar

- Claridad del valor ofrecido en el landing page.
- Flujo de suscripción y pago.
- Registro y gestión de insumos.
- Gestión de lotes e inventario.
- Gestión de ventas y recetas.
- Visualización y selección de proveedores.
- Realización y seguimiento de pedidos.
- Panel de alertas y resúmenes.

### Flujos de Usuario a evaluar

- **Desktop & Mobile User Flow 1:** Suscripción y pago con Stripe.
- **Desktop & Mobile User Flow 3:** Registro y gestión de insumos.
- **Desktop & Mobile User Flow 4:** Resumen e indicadores.
- **Desktop & Mobile User Flow 5:** Visualización de proveedores y productos.
- **Desktop & Mobile User Flow 6:** Seguimiento de pedidos.
- **Desktop & Mobile User Flow 7:** Comentarios a proveedores.
- **Desktop & Mobile User Flow 8:** Registro y visualización de ventas.
- **Desktop & Mobile User Flow 9:** Creación y gestión de recetas.

### Actividades durante la sesión

1. Navegar el Landing Page y explicar lo que entienden del producto.
2. Simular una suscripción desde un plan.
3. Usar el módulo de inventario: registrar, editar y filtrar insumos.
4. Acceder al panel de resumen y describir lo que entienden.
5. Navegar por proveedores, seleccionar uno y simular una orden.
6. Realizar comentarios sobre proveedores.
7. Registrar una venta.
8. Crear una receta.

## Segmento 2: Proveedores de Restaurantes

### Elementos a validar

- Claridad del valor en el Landing Page.
- Gestión de catálogo de productos.
- Eliminación de insumos no disponibles.
- Revisión de pedidos realizados por restaurantes.
- Interacción con comentarios recibidos.

### Flujos de Usuario a evaluar

- **Desktop & Mobile User Flow 1:** Suscripción y pago.
- **Desktop & Mobile User Flow 10:** Registro y gestión de productos en el catálogo.
- **Desktop & Mobile User Flow 11:** Eliminación de insumos.
- **Desktop & Mobile User Flow 12:** Gestión de órdenes recibidas.
- **Desktop & Mobile User Flow 13:** Panel principal del proveedor.

### Actividades durante la sesión

1. Explorar el Landing Page y describir su comprensión del producto.
2. Simular el proceso de registro y suscripción.
3. Ingresar al sistema y registrar productos en su catálogo.
4. Eliminar productos del catálogo.
5. Revisar pedidos recibidos de restaurantes.
6. Comentar sobre la utilidad de la interfaz de pedidos y feedback.

## Herramientas y Recursos para Validación

- **Formato de Evaluación Heurística:** Se aplicarán los 10 principios heurísticos de Nielsen en cada sesión.
- **Instrumento de observación:** Lista de verificación + sección de notas abiertas.
- **Grabación de pantalla y voz:** previa autorización, para análisis posterior.

### 5.3.2. Registro de Entrevistas

Segmento 1: Dueños o administradores de Restaurantes

**ENTREVISTA 1:**

**Nombre:** Alfredo Bernuy
**Edad:** 52 años
**Distrito:** Chorrillos
**Timing:** (00:00- 05:18 min)

![Foto de Entrevista](assets/images/entrevistaFinal1.png)

Ver entrevista: https://lc.cx/YT7O8G

**Resumen:**
Alfredo Bernuy, administrador de restaurantes con 4 años de experiencia, tiene 52 años, es casado y vive en el distrito de Chorrillos, Lima. Es una persona comprometida y orientada a la mejora continua.

Alfredo Bernuy destaca que la plataforma le resulta muy intuitiva desde el primer acceso: los menús están organizados de forma clara, los botones de acción son fácilmente reconocibles y el flujo para crear o modificar pedidos se siente natural y ágil. Valora especialmente la sección de gestión de stock, que le permite visualizar en tiempo real los niveles de inventario, recibir alertas automáticas al alcanzar el mínimo definido y filtrar por categorías o fechas para detectar tendencias.

Por otro lado, subraya que el diseño es moderno y atractivo: la paleta de colores es sobria pero actual, la tipografía resulta legible y los iconos comunican su función de un vistazo. Considera que la herramienta le brinda un control total sobre pedidos y stock, le ahorra tiempo y le transmite la confianza necesaria para optimizar sus operaciones diarias.

**ENTREVISTA 2:**

**Nombre:** Mery Pilar
**Edad:** 49 años
**Distrito:** Chorrillos
**Timing:** (05:19 - 10:50 min)

![Foto de Entrevista](assets/images/entrevistaFinal2.png)

Ver entrevista: https://lc.cx/YT7O8G

**Resumen:**

Mery Pilar, administradora de restaurantes con 6 años de experiencia, tiene 49 años, es casada y vive en el distrito de Chorrillos, Lima. Es una persona responsable y orientada a la mejora continua e innovación.

Mery Pilar resalta que la herramienta es sumamente sencilla de usar desde el primer contacto: los apartados están dispuestos de manera ordenada, los elementos interactivos resultan intuitivos y el proceso para generar o actualizar pedidos fluye de forma muy eficiente. Aprecia de forma especial el módulo de control de inventario, que le permite monitorear al instante las existencias, recibir notificaciones automáticas cuando un artículo llega al stock mínimo y aplicar filtros por categoría o periodo para identificar patrones de consumo.

Además, enfatiza que la apariencia es fresca y profesional: los tonos empleados son elegantes sin dejar de ser actuales, la tipografía se lee con total nitidez y los iconos transmiten claramente su función. En su opinión, esta solución le proporciona el dominio completo sobre pedidos e inventario, optimiza su tiempo y le infunde la seguridad necesaria para mejorar sus operaciones diarias.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Segmento 2: Proveedores para Restaurantes

**ENTREVISTA 1:**

**Nombre:** Flor Medina
**Edad:** 28 años
**Distrito:** San Miguel
**Timing:** (10:51 - 21:05 min)

![Foto de Entrevista](assets/images/entrevistaFinal3.png)

Ver entrevista: https://lc.cx/YT7O8G

**Resumen:**

Gerente de logistica y 7 años de experiencia

Flor Medina tiene 28 años, vive en el distrito de San Miguel y es gerente de logistica de pedidos. Es una persona perseverante, responsable y amable.

Comenta que la plataforma le facilita enormemente la gestión de sus pedidos entrantes: puede visualizar al instante las solicitudes de los restaurantes, confirmar o rechazar con un solo clic y programar fechas de envío en un calendario interactivo. Destaca el módulo de invetario, donde actualiza precios y descripciones de productos en tiempo real, y agradece las notificaciones automáticas que recibe cuando un cliente solicita pedidos.

Por su parte, valora que el panel de análisis le proporciona métricas claras que le ayuda a ajustar su producción y planificar rutas de reparto más eficientes. En conjunto, considera que esta herramienta le otorga un control total de sus procesos de venta y logística, reduce errores administrativos y le brinda la confianza de ofrecer un servicio más ágil y profesional.

### 5.3.3. Evaluaciones según heurísticas

**Carrera:** Ingeniería de Software

**Curso:** Aplicaciones Web
**Sección:** 4368
**Profesores:** Angel Velasquez
**Auditor:** Gabriela Nicole Shapiama Rivera y Yaku Mateo Guzman Cabrejos
**Cliente(s):** Mery Pilar, Alfredo Bernuy y Flor Medina

**Site o App a evaluar:** Restock

**ESCALA DE SEVERIDAD:**

Los errores serán puntuados tomando en cuenta la siguiente escala de severidad

<table>
    <tr>
        <td>Nivel</td>
        <td>Descripción</td>
    </tr>
    <tr>
        <td>1</td>
        <td>Problema superficial: puede ser fácilmente superador por el usuario ó ocurre con muy poco frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo.</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente reléase</td>
    </tr>
    <tr>
        <td>3</td>
        <td>Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta.</td>
    </tr>
    <tr>
        <td>4</td>
        <td>Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento.</td>
    </tr>
</table>

**Tareas evaluadas:**

1. Visualización de planes de suscripción
2. Gestión de inventario de insumos
3. Recepción de notificaciones automáticas
4. Realización de pedidos
5. Creación de recetas
6. Registro de ventas

---

**TABLA RESUMEN**

| #  | Problema                                                          | Escala de severidad | Heurística / Principio violado                                                 |
| -- | ----------------------------------------------------------------- | ------------------- | ------------------------------------------------------------------------------- |
| 1  | Uso de colores sin etiquetas para estados de pedido               | 2                   | Usabilidad: Visibilidad del estado del sistema                                  |
| 2  | Falta de opciones rápidas para reutilizar recetas                | 1                   | Usabilidad: Reconocer mejor que recordar                                        |
| 3  | No existen accesos directos ni funciones para expertos            | 3                   | Usabilidad: Flexibilidad y eficiencia de uso                                    |
| 4  | Botones y acciones no están claramente etiquetados               | 2                   | Usabilidad: Correspondencia entre sistema y mundo real                          |
| 5  | No se contempla accesibilidad visual o de navegación             | 2                   | Inclusive Design: Accesibilidad y compatibilidad                                |
| 6  | Falta de opciones para editar o cancelar un pedido                | 2                   | Usabilidad: Libertad y control del usuario                                      |
| 7  | Flujo de tareas puede ser poco guiado                             | 1                   | Information Architecture: Is it usable?                                         |
| 8  | Modal de creación de insumos podría ser más informativo        | 1                   | Usabilidad: Ayuda y documentación                                              |
| 9  | Notificaciones no especifican acción sugerida                    | 2                   | Usabilidad: Ayuda al usuario a reconocer, diagnosticar y recuperarse de errores |
| 10 | Registro de ventas puede generar confusión por pasos implícitos | 2                   | Arquitectura de información: Claridad del flujo                                |
| 11 | Panel de análisis no permite filtrar por tipo de cliente         | 2                   | Information Architecture: Is it findable?                                       |
| 12 | Calendario de envíos carece de vista resumen o semanal           | 2                   | Usabilidad: Flexibilidad y eficiencia de uso                                    |

---

**DESCRIPCIÓN DE PROBLEMAS**

**PROBLEMA #1: Uso de colores sin etiquetas para estados de pedido**
**Severidad:** 2
**Heurística violada:** Usabilidad - Visibilidad del estado del sistema
**Problema:** Actualmente, el sistema usa colores para indicar el estado de los pedidos, pero no existe una leyenda textual que acompañe estos colores. Esto puede causar confusión a usuarios que no recuerdan o entienden el significado de cada color.
**Evidencia:** La usuaria indicó: "Le sale de diferente color...". No mencionó saber qué significa cada color.
**Recomendación:** Incorporar etiquetas de texto junto a los colores para que el estado sea inequívocamente identificado ("Aprobado", "Pendiente", etc.).

---

**PROBLEMA #2: Falta de opciones rápidas para reutilizar recetas**
**Severidad:** 1
**Heurística violada:** Usabilidad - Reconocer mejor que recordar
**Problema:** El sistema permite crear recetas, pero no ofrece un mecanismo claro para reutilizarlas o seleccionarlas de forma directa. Esto puede hacer que el usuario deba rehacer pasos innecesarios.
**Evidencia:** La usuaria comentó: "Y puedo crear acá nuevos productos también", lo cual implica que debe crear nuevamente la receta en vez de seleccionar una ya existente.
**Recomendación:** Añadir un buscador o selector de recetas guardadas para ser reutilizadas.

---

**PROBLEMA #3: No existen accesos directos ni funciones para expertos**
**Severidad:** 3
**Heurística violada:** Usabilidad - Flexibilidad y eficiencia de uso
**Problema:** El sistema está centrado en tareas básicas, pero no contempla accesos rápidos, atajos o funcionalidades para usuarios frecuentes que desean operar con mayor agilidad.
**Evidencia:** "...tener más tiempo... incluso para poder abrir otra tienda", sugiere que la eficiencia es una necesidad importante para la usuaria.
**Recomendación:** Incluir favoritos, accesos directos desde el dashboard, filtros inteligentes o teclas rápidas.

---

**PROBLEMA #4: Botones y acciones no están claramente etiquetados**
**Severidad:** 2
**Heurística violada:** Usabilidad - Correspondencia entre sistema y mundo real
**Problema:** Algunos botones como "Place Order" no son intuitivos para un usuario hispanohablante, y su comprensión depende del color o la posición.
**Evidencia:** "Place Order (el morado)" indica que se recuerda el color más que la acción.
**Recomendación:** Usar etiquetas localizadas ("Realizar pedido") y añadir íconos descriptivos.

---

**PROBLEMA #5: No se contempla accesibilidad visual o de navegación**
**Severidad:** 2
**Heurística violada:** Inclusive Design - Accesibilidad y compatibilidad
**Problema:** El sistema no ofrece opción de alto contraste, navegación por teclado o soporte para lectores de pantalla.
**Evidencia:** No mencionado directamente, pero se infiere por ausencia de referencia.
**Recomendación:** Añadir opciones de accesibilidad visual y teclas de navegación.

---

**PROBLEMA #6: Falta de opciones para editar o cancelar un pedido**
**Severidad:** 2
**Heurística violada:** Usabilidad - Libertad y control del usuario
**Problema:** El sistema no deja claro si se pueden modificar o anular pedidos una vez registrados, lo cual limita el control del usuario sobre el flujo.
**Evidencia:** No se menciona esta posibilidad en la entrevista, y la acción parece definitiva.
**Recomendación:** Añadir botones de "Editar" y "Cancelar" en pedidos recientes.

---

**PROBLEMA #7: Flujo de tareas puede ser poco guiado**
**Severidad:** 1
**Heurística violada:** Arquitectura de información - Is it usable?
**Problema:** El proceso de registrar ventas o pedidos implica múltiples pasos que pueden resultar poco intuitivos sin guías.
**Evidencia:** "...registrar... seleccionar... luego se descuenta el stock" sugiere un flujo de acciones implícito.
**Recomendación:** Incorporar guías visuales paso a paso (como barra de progreso o onboarding contextual).

---

**PROBLEMA #8: Modal de creación de insumos podría ser más informativo**
**Severidad:** 1
**Heurística violada:** Usabilidad - Ayuda y documentación
**Problema:** El modal para añadir insumos es funcional, pero no proporciona ejemplos ni guías sobre qué información debe colocarse.
**Evidencia:** "...tiene ahí la opción de poner cualquiera de sus ítems" indica libertad sin orientación.
**Recomendación:** Incluir sugerencias o placeholders dentro del modal (por ejemplo: "Ej: Lechuga romana").

---

**PROBLEMA #9: Notificaciones no especifican acción sugerida**
**Severidad:** 2
**Heurística violada:** Usabilidad - Ayuda al usuario a reconocer, diagnosticar y recuperarse de errores
**Problema:** Las notificaciones informan del stock mínimo o de pedidos, pero no indican directamente qué hacer a continuación.
**Evidencia:** "...con esto ya tendríamos las notificaciones que nos alertarían" indica utilidad, pero no orientación.
**Recomendación:** Añadir botones de acción directa en las notificaciones ("Realizar pedido", "Editar insumo").

---

**PROBLEMA #10: Registro de ventas puede generar confusión por pasos implícitos**
**Severidad:** 2
**Heurística violada:** Arquitectura de información - Claridad del flujo
**Problema:** El proceso de registrar una venta y luego registrarla nuevamente para descontar del inventario puede resultar confuso para usuarios nuevos.
**Evidencia:** "...ventas registradas que no se han descontado del inventario..." sugiere un doble paso no evidente.
**Recomendación:** Fusionar ambos pasos o hacer explícito el estado intermedio con instrucciones claras ("Venta pendiente de confirmación").

---

**PROBLEMA #11: Panel de análisis no permite filtrar por tipo de cliente**
**Severidad:** 2
**Heurística violada:** Arquitectura de información - Is it findable?
**Problema:** El panel de métricas proporciona datos útiles, pero no permite segmentarlos por tipo de cliente, zona geográfica u otros criterios relevantes para la logística.
**Evidencia:** Flor menciona que "el panel de análisis le proporciona métricas claras", pero sugiere que la información está centralizada sin filtros.
**Recomendación:** Incluir filtros en el panel (por fecha, zona, tipo de restaurante, etc.) para mayor utilidad.

---

**PROBLEMA #12: Calendario de envíos carece de vista resumen o semanal**
**Severidad:** 2
**Heurística violada:** Usabilidad - Flexibilidad y eficiencia de uso
**Problema:** Aunque se puede programar fechas de envío, no se ofrece una vista que permita ver de forma semanal o mensual todas las programaciones a la vez.
**Evidencia:** Flor menciona que programa fechas de envío en un calendario interactivo, pero no indica capacidad de ver planificación agregada.
**Recomendación:** Añadir vistas tipo "semana" o "mes" al calendario para facilitar la gestión logística de varios pedidos.

## 5.4. Video About-the-Product

A continuación, se presenta el video "About the Product" del sistema Restock, una solución tecnológica desarrollada para digitalizar y automatizar la gestión de inventarios y pedidos en restaurantes. Este video está dirigido principalmente a los visitantes del Landing Page, quienes desean conocer el modelo de negocio y las principales funcionalidades de la plataforma, así como a los usuarios potenciales de las aplicaciones, interesados en realizar tareas relacionadas con los procesos soportados por la solución.

El video comunica de forma clara y dinámica el propósito del producto, mostrando cómo Restock ayuda a reducir el desperdicio, mejorar la eficiencia operativa y fortalecer la relación entre administradores de restaurantes y proveedores. Se utiliza un tono consistente con la propuesta visual y comunicacional del producto, combinando narración, demostraciones de uso y escenarios reales.

Como parte de la validación del producto, se incluye también el testimonio de un administrador de restaurante entrevistado en la etapa de descubrimiento.

A continuación, se incluye un screenshot del video, junto con los enlaces de la versión publicada en Microsoft Stream y YouTube, y el detalle del timing.

[https://shorturl.at/4827U](https://shorturl.at/4827U)
