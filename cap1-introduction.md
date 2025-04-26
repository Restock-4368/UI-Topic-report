# Capítulo I: Introducción

## 1.1 Startup Profile

### 1.1.1 Descripción de la Startup

### 1.1.2 Perfiles de integrantes del equipo

| **Williams Eduardo Avendaño Balarezo (u202315325)** |
|-----------------------------------------|
| Soy estudiante de Ingeniería de Software, con un fuerte enfoque en el desarrollo de soluciones eficientes a través de la programación y los algoritmos. Tengo experiencia en desarrollo web, tanto en frontend como en backend, y conocimientos en AWS (como S3 Storage y AWS Lex). Me apasiona aprender nuevas tecnologías y mejorar continuamente mis habilidades.
Puedo aportar al equipo una capacidad sólida para desarrollar aplicaciones escalables y optimizadas, integrando servicios de AWS para mejorar la eficiencia. Mi mentalidad orientada a resultados y mi enfoque en la resolución de problemas me permiten mantener altos estándares de calidad en el desarrollo. |

&nbsp;  
![Foto de Williams](assets/images/williams.png)

| **Yaku Mateo Guzmán Cabrejos (u20231b173)** |
|-----------------------------------------|
|Soy estudiante de Ingeniería de Software, motivado por el desarrollo de aplicaciones y por entender cómo funcionan las tecnologías detrás de ellas. Me gusta crear soluciones útiles, eficientes y seguras. Tengo experiencia en frontend y backend, y conocimientos sólidos en estructuras de datos, patrones de diseño y arquitectura de software, lo que me permite construir sistemas bien organizados y escalables.
A futuro, me gustaría especializarme en informática forense y ciberseguridad. Me interesa aprender nuevas herramientas y metodologías que mejoren el desarrollo y la calidad del software.
Me considero analítico, con buenas prácticas en trabajo en equipo y organización usando Git. Siempre busco aportar ideas prácticas y resolver problemas de forma eficiente. |

&nbsp;  
![Foto de Yaku](assets/images/yaku.png)

| **Julio Castro Alejos (u202021885)** |
|--------------------------|
| Soy estudiante de Ingeniería de Software con un gran interés en el desarrollo web y el enfoque DevOps. Me apasiona entender cómo funcionan los sistemas a nivel técnico y cómo integrarlos de forma eficiente para ofrecer soluciones escalables.  
Me motiva trabajar en equipo, aprender nuevas herramientas y metodologías que potencien tanto el desarrollo como la entrega continua de software de calidad.  
Cuento con habilidades en diseño de arquitecturas web, control de versiones con Git, integración y despliegue continuo (CI/CD), además de conocimientos sólidos en tecnologías frontend y backend.  
A futuro, busco especializarme en la automatización de procesos y el diseño de sistemas robustos, contribuyendo al crecimiento tecnológico en diversos sectores.  
Puedo aportar al equipo capacidades de liderazgo técnico, organización de flujos de trabajo (Git Flow), configuración de entornos de desarrollo y una mentalidad orientada a soluciones prácticas y eficientes. |

&nbsp;  
![Foto de Julio](assets/images/julio.png)

## 1.2 Solution Profile
### 1.2.1 Antecedente y Problemática

#### Who (¿Quiénes se ven afectados?)
Pequeños y medianos restaurantes en América Latina, especialmente aquellos con recursos limitados, procesos informales y bajo acceso a tecnología digital. Tanto los encargados de cocina (back of house) como el personal de atención al cliente (front of house) se ven afectados por una gestión ineficiente de inventarios y pedidos.

#### What (¿Qué ocurre?)
La gestión de inventarios y pedidos en estos restaurantes aún depende de métodos manuales como hojas de cálculo, cuadernos físicos o mensajes informales (vía WhatsApp o verbalmente). Esto conlleva errores humanos, retrasos en el abastecimiento y una falta de trazabilidad en el uso y consumo de insumos. Además, no existe una conexión eficiente entre el área operativa (cocina) y administrativa (compras y abastecimiento), lo que afecta la coordinación y la eficiencia del servicio.

#### Where (¿Dónde sucede?)
La problemática ha sido identificada en diversos países de América Latina como Perú, México, Honduras y Ecuador, donde múltiples estudios han evidenciado que la digitalización en los procesos operativos de restaurantes aún es baja, afectando directamente la eficiencia y la rentabilidad de los negocios.

#### When (¿Desde cuándo y con qué frecuencia?)
Esta situación es constante y persistente. Aunque el avance tecnológico ha mejorado otras industrias, el sector gastronómico —especialmente en el segmento PyME— aún no ha adoptado soluciones automatizadas que conecten en tiempo real los procesos de inventario, pedidos internos (cocina) y reposiciones externas (proveedores).

#### Why (¿Por qué es un problema?)
Porque la falta de automatización:
- Aumenta el **desperdicio de insumos** debido a errores de reposición o falta de planificación.
- Genera **pérdidas económicas** por sobrecompra, desabastecimiento o pedidos erróneos.
- Dificulta la **coordinación entre áreas**: el front of house puede requerir productos que no están disponibles, generando demoras o baja satisfacción del cliente.
- Limita la **reacción ante cambios en la demanda**, como promociones o alta rotación de clientes.
- Reduce la **capacidad de planificación estratégica** al no contar con datos consolidados en tiempo real.
- Impide la **toma de decisiones informadas**, afectando el control financiero y operativo.

#### How (¿Cómo se manifiesta?)
- Pedidos hechos de forma verbal o informal que se olvidan, repiten o ejecutan tarde.
- Procesos fragmentados entre cocina y compras, sin visibilidad compartida del inventario.
- Falta de alertas automatizadas que adviertan sobre bajo stock o insumos con alta rotación.
- Dificultad para generar reportes, analizar patrones de consumo y mejorar la operación día a día.
- Dependencia total del juicio del administrador, sin respaldo de un sistema que facilite el control.

#### How Much (¿Cuál es el impacto cuantitativo?)
- Solo el 28% de restaurantes en Perú monitorean adecuadamente sus residuos con métodos manuales (Cordova-Buiza et al., 2022).
- Un sistema automatizado puede reducir significativamente los costos operativos y de adquisición, como lo demuestran Zamora Saltos & Rodríguez Borges (2024).
- Modelos digitales aplicados en PyMEs alimentarias permiten optimizar tiempos, disminuir errores y mejorar la trazabilidad, reduciendo hasta un 15% de los costos operativos (Cabrera-Gala et al., 2021).
=======
Por tanto, se evidencia una clara necesidad de una solución tecnológica accesible, fácil de usar y que permita automatizar la administración de inventario, con reportes útiles, alertas y una interfaz intuitiva adaptada a las necesidades reales de los propietarios de restaurantes.


### 1.2.1 Antecedente y Problemática

### 1.2.2 Lean UX Proccess

#### 1.2.2.1. Lean UX Problem Statements

El estado actual de la operación en restaurantes ha dependido principalmente de la gestión manual de inventarios y pedidos por parte de administradores y proveedores. Utilizan hojas de cálculo, cuadernos físicos y mensajería informal. Estos procesos generan errores, desperdicio de insumos y falta de control operativo.

Lo que los productos actuales no resuelven es la necesidad de una solución accesible y sencilla que integre a proveedores y permita automatizar la operación sin requerir conocimientos muy técnicos.

Nuestro producto abordará esta brecha mediante una plataforma que digitaliza la gestión de inventario, automatiza pedidos a proveedores y centraliza la comunicación entre las dos partes.

Nuestro enfoque inicial estará dirigido a administradores de restaurantes y proveedores. Sabremos que hemos tenido éxito cuando veamos una reducción del desperdicio, una mejora en los tiempos de abastecimiento, y un uso recurrente de la plataforma para registrar inventario y coordinar pedidos por parte de los usuarios

#### 1.2.2.2 Lean UX Assumptions

### User Assumptions

**¿Quién es el usuario?**

- Segmento 1: Administradores y gerentes de restaurantes medianos ubicados en zonas urbanas, con operaciones activas y contacto frecuente con proveedores. Buscan optimizar su control operativo, evitar pérdidas de insumos y mejorar su capacidad de decisión sin depender de herramientas complejas.

- Segmento 2: Proveedores tradicionales de productos para restaurantes (bebidas, abarrotes), que aún trabajan con métodos manuales como Excel y WhatsApp. Priorizan la eficiencia en entregas, el registro de pedidos y el seguimiento de pagos.

**¿Dónde encaja nuestro producto en su trabajo o vida?**

- Segmento 1: Nuestra plataforma se integra en su rutina diaria como una herramienta central para el control de inventario, la automatización de pedidos y la toma de decisiones basada en datos.

- Segmento 2: La solución actúa como una plataforma comercial liviana que centraliza la recepción de pedidos y permite registrar pagos de forma simple y rápida.

**¿Qué problemas tiene nuestro producto para resolver?**

- Segmento 1:
  - Desorganización en el control de insumos.
  - Errores por registros manuales.
  - Falta de datos para tomar decisiones operativas.
  - Baja trazabilidad con proveedores.
- Segmento 2:
  - Desorden en la gestión de pedidos y entregas.
  - Dificultad para registrar pagos o controlar cuentas pendientes.
  - Pérdida de tiempo al usar múltiples canales.
  - Falta de herramientas simples para organizar su operación.

**¿Cuándo y cómo es nuestro producto usado?**

- Cuándo:
  - Diario: para registrar o consultar inventario, recibir alertas y generar pedidos.
  - Al inicio y fin de jornada: para ver pedidos entrantes, coordinar entregas y cerrar operaciones.
  - Al momento de recibir productos o registrar pagos.
- Cómo:
  - Desde su celular o PC, en una interfaz simple y responsiva, con módulos personalizados para cada segmento.

**¿Qué características son importantes?**

- Panel de control de inventario en tiempo real.
- Alertas automáticas por escasez de productos.
- Generación y envío de pedidos a proveedores desde la plataforma.
- Registro de pagos y gestión de deudas de forma rápida.
- Rutas de entrega optimizadas para proveedores.
- Comunicación centralizada entre proveedor y restaurante.

¿Cómo debe verse nuestro producto y cómo comportarse?

- Apariencia: Interfaz limpia, moderna e intuitiva. De una fácil manera de navegar, enfocandose en la experiencia del usuario
- Comportamiento: Fluido y adaptable. Navegación simple, con módulos organizados por tareas frecuentes. Las alertas deben ser visibles y el flujo debe permitir completar tareas en pocos pasos.

**Objetivos comerciales:**
- Crecimiento de usuarios: Nos enfocaremos en construir una base sólida de usuarios activos que utilicen regularmente la plataforma en sus operaciones diarias. Se proyecta alcanzar 500 usuarios activos en los primeros 6 meses, consolidando una comunidad inicial de administradores de restaurantes y proveedores
Retención: retención del 60%
- Retención: La retención de usuarios será clave para asegurar que la plataforma genere valor sostenido. Se espera lograr una tasa de retención del 60% al finalizar el primer mes de uso, lo que indicaría que la plataforma cumple con las expectativas de y mejora operativa de los segmentos objetivo.
- Expansión geográfica: Durante el primer año se buscará expandir la presencia de la plataforma en un 15% hacia nuevos mercados. Se buscarán nuevas ciudades y regiones con una buena actividad gastronómica, lo que nos permitirá escalar y mejorar nuestra solución

---

### Business Assumptions

- **Creemos que los restaurantes y proveedores necesitan** una plataforma accesible que automatice su operación diaria sin complejidad técnica.
- **Estas necesidades pueden resolverse** con una solución liviana y centralizada, que integre la gestión de inventario, pedidos, proveedores y pagos en un solo sistema.
- **Nuestros primeros clientes serán** restaurantes y proveedores que buscan mejorar sus operaciones sin grandes inversiones ni capacitaciones extensas.
- **El valor #1 que nuestros clientes buscan es** mayor control operativo y reducción de errores.
- **También obtendrán beneficios adicionales** como trazabilidad, ahorro de tiempo, y mejor relación entre restaurantes y proveedores.
- **Adquiriremos la mayoría de clientes a través de** recomendaciones boca a boca, redes sociales y contacto directo con negocios gastronómicos.
- **Generaremos ingresos mediante** suscripciones accesibles por segmento
- **Nuestra competencia principal serán** Oracle Simphony, RestroWorks y SoftRestaurant
- **Los superaremos ofreciendo** una solución más específica, simple, con posibilidad a una personalización mayor y que no requiera un alto conocimiento técnico
- **El mayor riesgo de producto es** que los usuarios no adopten la plataforma por falta de tiempo o familiaridad digital.
- **Resolveremos esto con** un soporte personalizado y una interfaz centrada en tareas frecuentes.

---

### User Benefits

- Control de inventario más preciso y actualizado.
- Reducción de pérdidas por sobrestock o faltantes.
- Procesos más rápidos y automatizados.
- Toma de decisiones basadas en datos reales.
- Menor dependencia de llamadas, mensajes y papel.
- Comunicación clara y directa entre restaurante y proveedor.

---

### Business Outcomes

- Aumentar el uso diario de la plataforma en un 30% por parte de ambos segmentos de usuarios en los próximos 2 meses.
- Incrementar en un 40% la frecuencia de pedidos gestionados desde la app y reducir errores de pedido en un 25%.
- Reducir en un 35% el desperdicio de insumos reportado por los restaurantes registrados.
- Lograr una retención de usuarios del 60% al finalizar el primer mes de uso.

---

### Features

- La plataforma incluirá un sistema automatizado de gestión de inventario que actualiza los niveles de stock en tiempo real, emite alertas inteligentes ante escasez o exceso de insumos y mantiene un historial completo de movimientos, lo que permitirá reducir el desorden y el desperdicio.
- Contará con una interfaz intuitiva, diseñada para facilitar la adopción por parte de administradores y proveedores, con un sencillo proceso de configuración inicial y un organizador con las tareas frecuentes de forma clara y accesible.
- Incorporará herramientas de análisis y reportes automáticos, con indicadores clave como rotación de productos, márgenes por plato y comparativas semanales o mensuales. Esto ayudará a tomar decisiones estratégicas en el negocio.
- Finalmente, permitirá la conexión directa con proveedores mediante un catálogo compartido, un sistema de pedidos con seguimiento de pedidos, un canal de comunicación, agilizando el abastecimiento y reduciendo los retrasos.

#### 1.2.2.3 Lean UX Hypothesis Statements

#### 1.2.2.4 Lean UX Canvas

## 1.3 Segmentos objetivos

**Segmento Objetivo 1: Dueños o Administradores de Restaurantes**

Los dueños o administradores de restaurantes en Lima, con edades entre 20 y 60 años que buscan optimizar la gestión de sus establecimientos para mejorar la experiencia del cliente y aumentar la rentabilidad. Enfrentan desafíos en la administración de inventarios, pedidos y coordinación del personal, por lo que requieren soluciones tecnológicas eficientes. Según el Instituto Nacional de Estadística e Informática (INEI), en abril de 2023, la actividad de restaurantes en Perú creció un 9,16% respecto al año anterior, reflejando un sector en recuperación y expansión. 

**Segmento Objetivo 2: Proveedores para Restaurantes**

Los proveedores de alimentos, bebidas y utensilios que abastecen a restaurantes en Lima y otras ciudades que buscan establecer relaciones comerciales con clientes que valoren la calidad y confiabilidad en las entregas. Este segmento incluye desde pequeños productores locales hasta grandes distribuidores. Según el INEI, en diciembre de 2023, la actividad de restaurantes aumentó un 3,66%, impulsando la demanda de insumos y beneficiando a los proveedores del sector.
