Evaluación 03 - Diseño y Solución de Problemas con Agentes de IA
# AI Room Services – Automatización de Atención al Cliente Hotelero con N8N

# 📌 Planteamiento del Problema

El proceso de atención al cliente en negocios hoteleros, especialmente en pequeños y medianos establecimientos, suele depender de la disponibilidad de personal y de respuestas manuales. Esta situación genera retrasos, respuestas inconsistentes y pérdida de oportunidades de reserva.

Hoy en día, los clientes esperan inmediatez, personalización y disponibilidad 24/7, particularmente en canales como WhatsApp, que se ha convertido en el medio de comunicación preferido en el sector. Sin embargo, la falta de automatización en la gestión de mensajes entrantes, la clasificación de solicitudes y la validación de pagos constituye un cuello de botella operativo que limita la competitividad y la satisfacción de los huéspedes.

Adicionalmente, las encuestas tradicionales de satisfacción resultan insuficientes para capturar en tiempo real las necesidades del cliente. Esto impide que los hoteles actúen con agilidad y se anticipen a expectativas cambiantes, lo cual afecta tanto la fidelización como la generación de ingresos.

En este contexto, la implementación de agentes inteligentes automatizados aparece como una solución innovadora. A través de integraciones con WhatsApp y APIs externas, dichos agentes pueden:

- Interpretar mensajes de texto y voz.
- Identificar necesidades específicas del huésped.
- Sugerir opciones personalizadas.
- Gestionar reservas (agendar, reprogramar, cancelar y consultar citas).
- Validar comprobantes de pago.

Este enfoque optimiza la experiencia del usuario al ofrecer atención continua, rápida y sin fricciones, al tiempo que permite a los hoteles reducir cargas operativas y mejorar su eficiencia.

# ⚙️ Justificación de la Tecnología

Para resolver esta problemática, se selecciona N8N como la herramienta principal. La elección se justifica en los siguientes aspectos:

* Naturaleza del problema: La atención al cliente hotelero requiere gestionar múltiples servicios (mensajería, bases de datos, pasarelas de pago, modelos de IA). N8N ofrece un entorno visual que facilita la orquestación de flujos complejos sin necesidad de programación extensa.

* Velocidad de desarrollo: A diferencia de una solución puramente en código, con N8N es posible prototipar rápidamente y realizar ajustes sin grandes esfuerzos de mantenimiento. Esto es clave para negocios pequeños/medianos que no cuentan con grandes equipos técnicos.

* Escalabilidad y flexibilidad: El flujo diseñado se puede ampliar fácilmente para integrar nuevos servicios (ej. marketing automatizado, CRM, sistemas de facturación). Además, la exportación/importación mediante archivos JSON permite replicar la solución en distintos establecimientos.

* Interactividad y personalización: Gracias a nodos como OpenAI y PostgreSQL Memory, el sistema recuerda interacciones previas y genera respuestas personalizadas. Esto mejora la experiencia del cliente y aumenta la tasa de conversión en reservas.

* Control de flujo avanzado: La solución implementa condicionales (IF) y gestión de datos (loops, edición de campos), lo cual garantiza decisiones dinámicas y adaptativas dentro del proceso.

En resumen, N8N es la herramienta óptima porque permite a los hoteles automatizar su atención al cliente sin necesidad de grandes inversiones en infraestructura tecnológica, logrando un equilibrio entre rapidez de desarrollo, escalabilidad y experiencia de usuario.

# 🚀 Guía de Uso

1. Requisitos Previos

Instalar N8N en un servidor local o en la nube. Contar con credenciales de acceso a las APIs a integrar:

- WhatsApp Business API o similar.
- OpenAI API (para procesamiento de lenguaje natural).
- PostgreSQL (para memoria de chat y gestión de reservas).
- API de validación de pagos (opcional).

2. Importación del Workflow

- Descargar el archivo workflow.json
 desde este repositorio: 
[AI_Room_Services_V1 1.json](https://github.com/user-attachments/files/22448476/AI_Room_Services_V1.1.json)

- Ingresar a la interfaz de N8N.
- Seleccionar Import Workflow y cargar el archivo.
Guardar y activar el flujo.

3. Flujo General del Sistema

El flujo implementado incluye los siguientes pasos principales:

<img width="1318" height="691" alt="image" src="https://github.com/user-attachments/assets/c4a80e3d-c36f-4879-8555-d152532a4066" />

- Recepción de mensaje (texto o voz) desde WhatsApp.
- Inicialización de datos y validación condicional.
- Conversión de audio a texto (si aplica).
- Procesamiento con OpenAI para interpretar la solicitud del cliente.
- Gestión de memoria en PostgreSQL para personalizar interacciones.
- Agente de reservas con las siguientes funciones: Agendar cita/reserva, reprogramar cita, cancelar cita y consultar citas existentes.
- Respuesta automática al cliente con confirmación de acción.

4. Ejemplo de Interacción

El cliente envía: “Hola, quisiera reservar una habitación doble para este fin de semana”.
El sistema procesa el mensaje con OpenAI, consulta disponibilidad en la base de datos y agenda la reserva.
El cliente recibe una confirmación inmediata con los detalles de su reserva.

