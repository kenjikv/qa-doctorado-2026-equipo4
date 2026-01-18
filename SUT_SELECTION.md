# SUT_SELECTION.md — Restful Booker

## SUT elegido

**Nombre:** Restful Booker  
**Tipo:** API REST  
**Dominio funcional:** Gestión de reservas (_booking management_)  
**Lenguaje y plataforma:** Node.js  
**Fuente:** https://github.com/mwinteringham/restful-booker  
**Licencia:** MIT  
**Modo de ejecución:** Local mediante Docker / Docker Compose  
**Interfaz expuesta:** HTTP (JSON)

## Descripción general del SUT

Restful Booker es una aplicación de referencia ampliamente utilizada en contextos académicos y profesionales para la enseñanza y validación de pruebas sobre APIs REST. El sistema implementa un conjunto acotado pero representativo de operaciones CRUD orientadas a la gestión de reservas, permitiendo crear, consultar, actualizar y eliminar registros de tipo _booking_. La API sigue un diseño simple y explícito, lo cual facilita la comprensión del flujo de datos y la definición de casos de prueba reproducibles.

El SUT expone endpoints claramente delimitados, utiliza códigos de estado HTTP convencionales y opera con estructuras JSON estables. Estas características favorecen la observación del comportamiento externo del sistema sin requerir conocimiento profundo de su implementación interna, alineándose con enfoques de prueba de caja negra y gris.

## Motivo de selección

La selección de Restful Booker se fundamenta en un conjunto de criterios técnicos y académicos que lo hacen especialmente adecuado como sistema bajo prueba en una actividad doctoral orientada al aseguramiento de la calidad.

1. **SUT público, estable y reproducible:** El sistema es de acceso abierto, ampliamente utilizado y mantenido de forma consistente, lo cual permite reproducir experimentos y comparar resultados entre distintos equipos o cohortes académicas bajo las mismas condiciones.

2. **Facilidad de despliegue y control del entorno:** La posibilidad de ejecutar el SUT localmente mediante contenedores Docker garantiza independencia del entorno, aislamiento de las pruebas y control completo del ciclo de vida del sistema, aspectos esenciales para la validez de los resultados experimentales.

3. **Adecuación para múltiples técnicas de prueba:** El diseño simple y explícito de la API, junto con el uso de convenciones HTTP estándar y estructuras JSON estables, permite aplicar pruebas funcionales, de regresión, basadas en contratos y de exploración, facilitando la definición de oráculos y la recolección de evidencias objetivas.

## Adecuación para actividades de aseguramiento de la calidad

Restful Booker resulta adecuado para la aplicación de técnicas de aseguramiento de la calidad debido a que presenta escenarios reales de interacción cliente–servidor, manejo de estados, validación de entradas y control de errores. El sistema permite diseñar y ejecutar pruebas funcionales, pruebas de regresión y pruebas basadas en contratos HTTP, así como analizar el cumplimiento de expectativas definidas mediante oráculos simples.

La presencia de endpoints de autenticación y autorización básica habilita, además, la exploración de pruebas relacionadas con seguridad a nivel de API. Asimismo, el comportamiento determinista de la mayoría de sus operaciones facilita la recolección de evidencias y el análisis comparativo de resultados.

## Riesgos y limitaciones

El uso de Restful Booker como sistema bajo prueba presenta una serie de riesgos y limitaciones que deben ser considerados para una correcta interpretación de los resultados obtenidos durante la actividad doctoral.

1. **Alcance funcional limitado:** El dominio de negocio del SUT es intencionalmente simple, por lo que no refleja la complejidad, interdependencias ni restricciones propias de sistemas productivos reales. Esta limitación puede reducir la capacidad de extrapolar los resultados a contextos industriales de mayor escala.

2. **Mecanismos de seguridad básicos:** La autenticación y autorización implementadas son elementales, lo que restringe el análisis de escenarios avanzados de seguridad, tales como control de accesos granulares, auditoría, trazabilidad o cumplimiento de normativas estrictas.

3. **Observabilidad restringida:** El sistema no proporciona métricas internas ni herramientas nativas de monitoreo, limitando la evaluación de aspectos como rendimiento interno, uso de recursos o tolerancia a fallos. En consecuencia, el análisis de calidad se centra principalmente en el comportamiento externo observable mediante la interfaz HTTP.
