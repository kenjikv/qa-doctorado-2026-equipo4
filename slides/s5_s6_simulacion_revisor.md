# Evaluación de Propuesta - Equipo 4
**Propuesta evaluada:** C — Empresa: NorthStar Quality Lab
**Veredicto:** Aceptar con condiciones

> Regla: Todo punto debe estar **respaldado por la propuesta**.
> Si algo no está en la propuesta, debe ir en "Vacíos" o "Preguntas", no como afirmación.

---

## Slide 1 — Qué ofrece la propuesta (solo hechos del texto)
- **Objetivo declarado (copiar 1 frase o resumir):** Programa integral basado en evidencia reproducible y gobernanza del quality gate, con el objetivo de **sostener calidad continua sin frenar el flujo**, mediante checks críticos (must-pass) y un mecanismo formal de excepciones.  
  **Referencia:** Sección 1

- **Alcance / exclusiones (2+ puntos):**
  - Incluye: escenarios (6–10) con evidencia, matriz y estrategia Top 3, diseño sistemático (≥12 casos), oráculos mínimos/estrictos, gate CI con artifacts, política de excepciones y registro de cambios. **Ref:** Sección 3
  - Excluye: performance a gran escala y pruebas de seguridad especializadas. **Ref:** Sección 3

- **Entregables principales (3+ puntos):**
  - Gate CI con checks críticos bloqueantes y publicación de artifacts. **Ref:** Sección 4 (Fase 4), 8
  - Política de excepciones y registro de cambios operativo. **Ref:** Sección 3, 5, 8
  - Escenarios con evidencia reproducible versionada y diseño sistemático EQ/BV + pairwise. **Ref:** Sección 3, 4 (Fases 1–3), 8

---

## Slide 2 - Fortalezas (basadas en texto)
> 3-5 fortalezas. Cada una debe citar una sección.

- **F1:** Metodología Clara con pasos identificables
  **Evidencia en propuesta:** Sección 4 (Fase 2 y 4): "Clasificación de checks: críticos (must-pass) vs informativos"; "Checks no funcionales inicialmente informativos hasta estabilizar baseline".  
  **Por qué es valioso (1 frase):** Alineado con principio de alta señal/bajo ruido del curso: el gate no bloquea por métricas inestables.

- **F2:** Costo determinado
  **Evidencia en propuesta:** Sección 7
  **Por qué es valioso:** Por que se sabe el precio a primera instancia

- **F3:** Política de excepciones con ticket asociado y revisión semanal.  
  **Evidencia en propuesta:** Sección 5: "La excepción debe asociarse a un ticket de corrección y revisarse en la siguiente reunión semanal".
  **Por qué es valioso:** Evita que el gate bloquee injustificadamente sin dejar excepciones sin trazabilidad.

- **F4:**: Separación entre checks críticos (must-pass) e informativos.
  **Evidencia en propuesta:** Sección 4 Fase 2 y 4
  **Por qué es valioso:** Mejora señal/ruido del gate y evita bloqueo prematuro por inestabilidad inicial.
- (Opcional) F4/F5: ___ (mismo formato)

---

## Slide 3 - Debilidades / riesgos (basadas en texto)
> 3-6 debilidades. Marcar severidad: **Crítica / Mayor / Menor**.
> Cada debilidad debe citar una sección de la propuesta.

- **D1 (Severidad: Mayor):** No se define cuándo ni cómo un check "informativo" pasa a ser bloqueante; "estabilizar baseline" es ambiguo.  
  **Texto/Sección relacionada:** Sección 4 (Fase 4): "Checks no funcionales inicialmente informativos hasta estabilizar baseline"; Fase 5: "Ajuste de umbrales no funcionales para lograr estabilidad de flujo".  
  **Riesgo/impacto:** El gate puede quedar permanentemente con checks solo informativos, reduciendo la señal real del control.

- **D2 (Severidad: Mayor):** La política de excepciones permite aprobar cuando "existe justificación operativa" sin definir qué constituye una justificación aceptable.  
  **Texto/Sección relacionada:** Sección 4 (Fase 5): "Activación de política de excepciones cuando un check no funcional bloquea entregas y existe justificación operativa"; Sección 5: "se permite aprobar mediante una excepción registrada".  
  **Riesgo/impacto:** Riesgo de Goodhart/gaming: excepciones frecuentes pueden vaciar de contenido el gate.

- **D3 (Severidad: Mayor):** "Temporalmente" no tiene criterio objetivo; un check con fallos esporádicos puede quedar desactivado indefinidamente.  
  **Texto/Sección relacionada:** Sección 5: "Si un check genera fallos esporádicos, se recomienda reducir temporalmente su severidad a informativo mientras se corrige".  
  **Riesgo/impacto:** Checks inestables (bajo ruido) pueden quedar permanentemente rebajados sin plazo ni criterio de reactivación.

- **D4 (Severidad: Menor):** No se especifica formato ni contenido mínimo del "registro de cambios" del gate.  
  **Texto/Sección relacionada:** Sección 6: "registro en repositorio y bitácora de cambios del gate"; Sección 8: "registro de cambios disponible y operativo".  
  **Riesgo/impacto:** Dificulta auditoría y trazabilidad de modificaciones del gate.


---

## Slide 4 - Cobertura explícita vs vacíos
### A) Lo que la propuesta sí define (3-5 puntos)
- Escenarios con medida y evidencia esperada **Ref:** Sección 4
- Matriz de riesgos, impacto por probabilidad **Ref:** Sección 4
- Gate safe con checks criticos bloqueantes  **Ref:** Sección 4
- Revisión semanal y auditorias **Ref:** Sección 6
- Entregas incrementales con hitos **Ref:** Sección 6

### B) Vacíos/ambigüedades que impiden evaluar bien (3-5 puntos)
- **Vacío 1:** Criterio concreto para "estabilizar baseline" y activar checks no funcionales como bloqueantes.  
  **Qué falta exactamente:** Definición operativa de estabilidad (ej.: X ejecuciones sin fallo, ventana temporal).  
  **Por qué importa:** Sin ello no se puede verificar que el gate evolucione de informativo a bloqueante.

- **Vacío 2:** Qué es "justificación operativa" aceptable para una excepción.  
  **Qué falta exactamente:** Tipos o ejemplos de justificación, quién aprueba, nivel de formalidad.  
  **Por qué importa:** Determina el rigor real de la política de excepciones.

- **Vacío 3:** Plazo máximo para que un check "temporalmente" informativo vuelva a ser bloqueante.  
  **Qué falta exactamente:** Días, sprints o hitos para la revisión.  
  **Por qué importa:** Evita que checks se desactiven indefinidamente por inestabilidad.

- **Vacío 4:** Estructura o esquema de la bitácora de cambios del gate.  
  **Qué falta exactamente:** Campos obligatorios, dónde se almacena, formato.  
  **Por qué importa:** Necesario para gobernanza y auditoría.

- **Vacío 5:** Desglose monetario del precio por fase o entregable.  
  **Qué falta exactamente:** La propuesta indica costo total (USD 10,800) y lo que incluye (gobernanza, bitácora, estabilización), pero no asigna montos a cada fase o entregable.  
  **Por qué importa:** Complica la evaluación de valor, la comparación con alternativas y la negociación por fases.

### C) Preguntas de aclaración al proveedor (2-4 preguntas)
- **P1:** ¿Qué criterio operativo define que un check no funcional ha "estabilizado" y puede pasar de informativo a bloqueante?
- **P2:** ¿Qué tipos de "justificación operativa" son aceptables para aprobar una excepción, y quién tiene autoridad para validarla?
- **P3:** ¿Cuál es el plazo máximo recomendado para mantener un check en modo "temporalmente informativo" antes de decidir su reactivación o eliminación?
- **P4:** ¿Qué formato y campos mínimos tendrá la bitácora de cambios del gate, y en qué repositorio o herramienta se mantendrá?
- **P5:** ¿Es posible disponer de un desglose del costo por fase o por entregable principal para evaluar valor y eventual negociación por hitos?

---

## Slide 5 — Goodhart / Gaming (solo si se deriva del texto)
> Debe basarse en señales explícitas del documento (ej.: "mantener gate verde", "ajustar umbrales", "excepciones", "reruns", etc.)

- **Señal en la propuesta (citar):** "Si un check no funcional bloquea el gate, se permite aprobar mediante una excepción registrada"; "Si un check genera fallos esporádicos, se recomienda reducir temporalmente su severidad a informativo".  
  **Referencia:** Sección 5

- **Riesgo de gaming (1 frase):** Incentivo a usar excepciones o rebajar severidad en lugar de corregir la causa raíz del fallo.

- **Consecuencia probable (1 frase):** El gate pierde significado si las excepciones son habituales o los checks inestables se mantienen informativos sin plazos.

- **Mitigación/condición (1 frase):** Limitar excepciones por periodo (ej.: máximo N por mes), definir criterio objetivo de "temporalmente", y que la auditoría mensual revise la tasa de excepciones con acción correctiva si supera un umbral.

---

## Slide 6 - Condiciones para aceptar (solo si el veredicto lo requiere)
> 2-4 condiciones **verificables**. Deben apuntar a corregir debilidades o llenar vacíos.

- **C1:** Incluir en el contrato o anexo técnico una definición operativa de "estabilización de baseline" (ej.: 5 ejecuciones consecutivas sin fallo en 7 días) como requisito para pasar un check de informativo a bloqueante.  
  **Cómo se verifica:** Documento entregado con criterio explícito; revisión en reunión de aceptación.  
  **Motivo (D# o Vacío #):** D1, Vacío 1

- **C2:** Documentar tipos de justificación aceptables y autoridad de aprobación de excepciones; establecer un límite máximo de excepciones por periodo (ej.: 2 por mes por check).  
  **Cómo se verifica:** Política de excepciones actualizada con anexo; auditoría mensual comprueba cumplimiento del límite.  
  **Motivo (D# o Vacío #):** D2, Vacío 2, Slide 5 (Goodhart)

- **C3:** Definir plazo máximo (ej.: 2 sprints o 4 semanas) para que un check en modo "temporalmente informativo" sea revaluado y reactivado o descartado.  
  **Cómo se verifica:** Política escrita; registro de checks en modo temporal con fecha de revisión.  
  **Motivo (D# o Vacío #):** D3, Vacío 3

- **C4:** Entregar esquema o plantilla de bitácora de cambios (campos, ubicación, formato) antes de la Fase 4.  
  **Cómo se verifica:** Documento con estructura; registro operativo en semana 6.  
  **Motivo (D# o Vacío #):** D4, Vacío 4

---

## Slide 7 - Veredicto (decisión final)
- **Decisión:** Aceptar con condiciones

- **Justificación:**
  1) La propuesta es sólida en metodología (escenarios, riesgo, oráculos, diseño sistemático, quality gate) y gobernanza, pero los vacíos en estabilización de baseline, justificación de excepciones y plazos "temporales" impiden evaluar el rigor real del gate (D1, D2, D3, Vacíos 1–3).
  2) El riesgo de Goodhart/gaming por excepciones y rebajas de severidad es real y no está mitigado con criterios verificables (Slide 5).
  3) Las condiciones C1–C4 son verificables y corrigen los vacíos principales; su cumplimiento antes de la Fase 4 (o en el contrato) hace la propuesta aceptable.

