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


### 5.1.3 Source Code Style Guide & Conventions

### 5.1.4 Software Deployment Configuration


## 5.2 Landing Page, Services & Applications Implementation


### 5.2.1 Sprint 1

#### 5.2.1.1 Sprint Planning 1

#### 5.2.1.2 Aspect Leaders and Collaborators

#### 5.2.1.3 Sprint Backlog 1

#### 5.2.1.4 Development Evidence for Sprint Review

#### 5.2.1.5 Execution Evidence for Sprint Review

#### 5.2.1.6 Services Documentation Evidence for Sprint Review

#### 5.2.1.7 Software Deployment Evidence for Sprint Review

#### 5.2.1.8 Team Collaboration Insights during Sprint
