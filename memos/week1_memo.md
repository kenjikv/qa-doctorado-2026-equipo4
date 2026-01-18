# Memo de Progreso — Semana 1

**Fecha:** 18/01/2026  
**Equipo:** Equipo 4
**Semana:** 1 de 8

## Objetivos de la semana

Durante la primera semana se establecieron las bases técnicas y organizativas del proyecto doctoral de aseguramiento de la calidad. El foco principal se orientó a la selección fundamentada del sistema bajo prueba, la preparación del entorno de ejecución y la definición de mecanismos mínimos que aseguren reproducibilidad, control y trazabilidad del trabajo inicial.

De manera complementaria, se priorizó la generación de documentación clara y accesible que permita a todos los integrantes comprender rápidamente la estructura del repositorio, el propósito de cada componente y la forma correcta de interactuar con el SUT.

## Logros

- **SUT seleccionado y documentado:** Se seleccionó el sistema **Restful Booker** como SUT y se documentó formalmente la decisión en `SUT_SELECTION.md`, incluyendo descripción, motivos de selección, alcance, riesgos y limitaciones.
- **Scripts de entorno implementados:** Se crearon los scripts `run_sut.sh`, `healthcheck_sut.sh` y `stop_sut.sh` en el directorio `setup/`, permitiendo levantar, verificar la salud y detener el SUT de forma controlada mediante Docker.
- **Automatización con Makefile:** Se incorporó un _Makefile_ para unificar las operaciones de arranque, verificación, detención y reinicio del SUT, reduciendo la complejidad operativa y el riesgo de errores manuales.
- **README estructurado:** Se elaboró un `README.md` alineado con criterios académicos, detallando la estructura del repositorio, requisitos del entorno y formas de ejecución mediante scripts y Makefile.
- **Acuerdos del equipo registrados:** Se formalizaron los acuerdos de colaboración, estándares de calidad y mecanismos de coordinación en el archivo `AGREEMENTS.md`.

## Evidencia principal

- **Selección y justificación del SUT:** `SUT_SELECTION.md`
- **Gestión del ciclo de vida del SUT:**
  - `setup/run_sut.sh`
  - `setup/healthcheck_sut.sh`
  - `setup/stop_sut.sh`
- **Orquestación de comandos:** `Makefile`
- **Documentación de uso y estructura:** `README.md`
- **Normas y acuerdos del equipo:** `AGREEMENTS.md`

## Retos y notas

- **Dependencia del entorno Docker:** El correcto funcionamiento del proyecto depende de la disponibilidad de Docker y Docker Compose, lo cual se documentó explícitamente en el README para evitar ambigüedades.
- **Gestión de permisos de ejecución:** Se identificó la necesidad de asignar permisos de ejecución a los scripts, resolviéndose mediante un objetivo específico en el Makefile.
- **Chequeo de salud del SUT:** La validación de salud se basa en la disponibilidad de endpoints funcionales clave de Restful Booker, lo que proporciona un indicador práctico aunque limitado del estado del sistema.

## Lecciones aprendidas

La estandarización temprana de comandos mediante un _Makefile_ facilita la adopción del entorno por parte del equipo y reduce inconsistencias en la ejecución. Asimismo, disponer de scripts explícitos para el control del SUT permite separar claramente las tareas de infraestructura de las actividades de prueba. Finalmente, mantener la documentación inicial concisa y bien estructurada acelera la incorporación de nuevos integrantes y mejora la comprensión global del proyecto.

## Próximos pasos — Semana 2 (propuestos)

- Diseñar casos de prueba funcionales y definir reglas de oráculo iniciales en el directorio `design/`.
- Elaborar una estrategia preliminar de pruebas y riesgos en `risk/test_strategy.md`, alineada con las características de Restful Booker.
- Implementar pruebas básicas de tipo _smoke_ sobre los endpoints principales del SUT.
- Definir métricas iniciales de ejecución y comenzar la recolección sistemática de evidencias en `evidence/week2/`.

**Preparado por:** Equipo 4
**Próxima revisión:** Semana 2
