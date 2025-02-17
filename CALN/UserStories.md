# Documento de Requisitos del Producto (PRD)

## 1. **Resumen Ejecutivo**
Este documento define los requisitos del producto para un Sistema de Gestión de Candidatos (ATS). El objetivo del sistema es optimizar el proceso de reclutamiento y selección de talento a través de una plataforma moderna basada en microservicios y microfrontends, proporcionando una experiencia eficiente tanto para reclutadores como para candidatos.

## 2. **Objetivos del Producto**
- Automatizar y optimizar el ciclo de vida del reclutamiento.
- Mejorar la experiencia del candidato y del reclutador.
- Centralizar y estructurar la información de los postulantes.
- Proporcionar análisis y reportes para mejorar la toma de decisiones.
- Integración con herramientas externas (CRM, ERP, LinkedIn, etc.).

## 3. **Público Objetivo**
- **Reclutadores:** Publican ofertas y gestionan candidatos.
- **Candidatos:** Aplican a las vacantes y realizan seguimiento de su postulación.
- **Administradores:** Gestionan el sistema, permisos y reportes.

## 4. **Requisitos Funcionales**
### 4.1. **Publicación y Gestión de Ofertas de Trabajo**
- Creación, edición y cierre de ofertas de empleo.
- Publicación en múltiples plataformas de empleo.
- Integración con redes sociales para difusión de vacantes.

### 4.2. **Captura y Gestión de Candidatos**
- Recopilación de CVs desde distintas fuentes (formularios, email, LinkedIn).
- Creación de perfiles estructurados de candidatos.
- Búsqueda y filtrado avanzado de postulantes.

### 4.3. **Seguimiento y Evaluación de Candidatos**
- Pipeline de selección con estados personalizados.
- Programación de entrevistas y envío de notificaciones.
- Registro de evaluaciones y feedback estructurado.

### 4.4. **Reportes y Analítica de Reclutamiento**
- Métricas de tiempo de contratación y conversión de candidatos.
- Identificación de fuentes de talento más efectivas.
- Reportes exportables en formatos estándar.

### 4.5. **Gestión de Usuarios y Seguridad**
- Autenticación y autorización (OAuth, JWT).
- Control de roles y permisos.
- Cumplimiento con normativas de protección de datos (GDPR, Habeas Data).

## 5. **Requisitos No Funcionales**
- **Escalabilidad:** Arquitectura basada en microservicios y contenedores Kubernetes.
- **Alto rendimiento:** Uso de caché con Redis y comunicación asíncrona con Kafka.
- **Disponibilidad:** Despliegue en infraestructura cloud con alta disponibilidad.
- **Seguridad:** Cifrado de datos, gestión de accesos y auditoría de eventos.

## 6. **Arquitectura Técnica**
- **Frontend:** Angular - TypeScript (Microfrontends).
- **Backend:** Java - Spring Boot (Microservicios).
- **Base de Datos:** Oracle.
- **Mensajería:** Kafka para comunicación asíncrona.
- **API Gateway:** Spring Cloud Gateway.
- **Despliegue:** Contenedores Docker en Kubernetes.

## 7. **Casos de Uso Principales**
1. **Publicación de una oferta de empleo.**
2. **Aplicación de un candidato a una oferta.**
3. **Revisión y filtrado de candidatos por parte del reclutador.**
4. **Programación de entrevistas y evaluaciones.**
5. **Notificación al candidato sobre el estado de su postulación.**

## 8. **Integraciones Externas**
- Plataformas de empleo (LinkedIn, Indeed, Glassdoor).
- CRM y ERP corporativos.
- Herramientas de comunicación (Slack, Teams, Email).

## 9. **Métricas de Éxito**
- **Tiempo promedio de contratación.**
- **Tasa de conversión de postulaciones a contrataciones.**
- **Nivel de satisfacción del candidato y del reclutador.**
- **Eficiencia en el uso de fuentes de talento.**

## 10. **Historias de Usuario**

| ID  | Historia de Usuario | Descripción | Criterios de Aceptación | Notas Adicionales | Tareas |
|---|---|---|---|---|---|
| HU1 | Como reclutador, quiero publicar una oferta de empleo para atraer candidatos adecuados. | Permite a los reclutadores crear y publicar ofertas en múltiples plataformas. | Dado que soy un reclutador autenticado, cuando completo el formulario de publicación, entonces la oferta debe estar visible en el portal de empleos. | Considerar validaciones para evitar datos incompletos. | Diseñar formulario, validar campos, conectar con API de publicación, pruebas. |
| HU2 | Como candidato, quiero aplicar a una oferta de empleo para postularme a una vacante. | Permite a los candidatos subir su CV y completar un formulario de aplicación. | Dado que soy un candidato autenticado, cuando aplico a una oferta, entonces mi perfil debe registrarse en la base de datos del sistema. | Incluir opción de carga de CV y autofill de datos. | Diseñar formulario, conectar con base de datos, pruebas de validación. |
| HU3 | Como reclutador, quiero filtrar y buscar candidatos para encontrar el perfil ideal. | Permite aplicar filtros avanzados en la base de datos de candidatos. | Dado que soy un reclutador autenticado, cuando utilizo los filtros de búsqueda, entonces debo ver una lista de candidatos que cumplen con los criterios. | Incluir búsqueda por palabras clave, experiencia y habilidades. | Diseñar interfaz, implementar lógica de búsqueda, conectar con base de datos. |
| HU4 | Como reclutador, quiero programar entrevistas para coordinar con los candidatos seleccionados. | Permite a los reclutadores seleccionar un candidato y agendar una entrevista. | Dado que seleccioné un candidato, cuando elijo una fecha y hora, entonces la entrevista debe registrarse en el sistema y enviarse una notificación. | Integrar con calendarios de terceros. | Diseñar módulo de entrevistas, integración con notificaciones, pruebas. |
| HU5 | Como candidato, quiero recibir notificaciones sobre mi estado para saber si sigo en el proceso. | Permite enviar notificaciones automáticas según el estado del candidato. | Dado que mi estado ha cambiado, cuando se actualiza en el sistema, entonces debo recibir una notificación con la información. | Usar múltiples canales (email, SMS, app). | Implementar sistema de notificaciones, pruebas de envío y recepción. |

## 11. **Backlog Priorizado**

| ID  | HU | Impacto y Valor de Negocio | Urgencia | Complejidad | Riesgos y Dependencias |
|---|---|---|---|---|---|
| HU1 | Publicación de ofertas de empleo | Alto - Impacta la captación de talento directamente | Alta - Requisito base para operación | Media - Requiere integraciones con plataformas externas | Dependencia con API de publicación |
| HU2 | Aplicación de candidatos | Alto - Facilita la adquisición de talento | Alta - Necesario para el funcionamiento del sistema | Media - Incluye validaciones de datos y almacenamiento | Depende de la gestión de usuarios |
| HU3 | Filtrado y búsqueda de candidatos | Medio - Optimiza el trabajo de los reclutadores | Media - Prioritario después de la publicación y postulación | Alta - Compleja lógica de búsqueda y ranking | Depende de la captura de datos de candidatos |
| HU4 | Programación de entrevistas | Medio - Acelera el proceso de selección | Media - Optimiza la gestión de tiempo de los reclutadores | Alta - Requiere integración con calendarios externos | Depende de la funcionalidad de postulación |
| HU5 | Notificaciones a candidatos | Medio - Mejora la experiencia del usuario | Media - Mejora la comunicación del proceso | Baja - Principalmente lógica de envío de mensajes | Depende de los cambios en el estado de postulación |

## 12. **Tickets de Trabajo por Feature**

| ID | Título | Descripción | Criterios de Aceptación | Prioridad | Estimación de Esfuerzo | Asignación | Etiquetas | Comentarios y Notas | Enlaces o Referencias | Historial de Cambios |
|---|---|---|---|---|---|---|---|---|---|---|
| T1 | Creación y publicación de ofertas | Implementar funcionalidad para que los reclutadores puedan crear y publicar ofertas en el portal | Dado que soy un reclutador autenticado, cuando completo el formulario y envío la oferta, entonces esta debe publicarse correctamente | Alta | 8 puntos | Equipo de Backend | #Ofertas #Publicación | Validar datos obligatorios, integrar con plataformas externas | Documentación API, Repositorio GitHub | 01/03/2025 - Creación inicial |
| T2 | Aplicación de candidatos | Permitir que los candidatos se postulen a las ofertas disponibles en el sistema | Dado que soy un candidato autenticado, cuando aplico a una oferta, entonces mi perfil debe almacenarse en la base de datos | Alta | 8 puntos | Equipo de Frontend | #Aplicaciones #Candidatos | Considerar compatibilidad con distintos formatos de CV | Mockups UI, Base de datos | 02/03/2025 - Ajustes en validaciones |
| T3 | Filtros y búsqueda de candidatos | Implementar búsqueda avanzada y filtrado de candidatos por criterios como experiencia y habilidades | Dado que soy un reclutador autenticado, cuando aplico un filtro, entonces debo ver una lista de candidatos relevantes | Media | 13 puntos | Equipo de Backend | #Búsqueda #Filtros | Evaluar rendimiento con grandes volúmenes de datos | Algoritmos de ranking, Base de datos | 03/03/2025 - Mejora en indexación |
| T4 | Programación de entrevistas | Implementar módulo para que los reclutadores agenden entrevistas con candidatos | Dado que seleccioné un candidato, cuando elijo una fecha y hora, entonces la entrevista debe registrarse y enviarse una notificación | Media | 8 puntos | Equipo de Integraciones | #Entrevistas #Notificaciones | Integrar con calendarios externos (Google, Outlook) | API Calendarios, UX Wireframes | 04/03/2025 - Agregado soporte para Zoom |
| T5 | Notificaciones a candidatos | Implementar sistema de notificaciones automáticas sobre el estado del proceso de selección | Dado que mi estado ha cambiado, cuando se actualiza en el sistema, entonces debo recibir una notificación | Media | 5 puntos | Equipo de Backend | #Notificaciones #Candidatos | Definir estrategias de notificación (email, SMS, push) | Arquitectura de eventos, Kafka | 05/03/2025 - Ajustes en templates de email |

## 13. **Consideraciones Finales**
Este PRD establece la base para el desarrollo del ATS, asegurando que las funcionalidades sean alineadas con las necesidades de los usuarios y las tendencias del mercado. La implementación seguirá metodologías ágiles para adaptarse a cambios y mejoras continuas.

---

**¿Se necesita algún ajuste o se requiere mayor detalle en algún punto?**

