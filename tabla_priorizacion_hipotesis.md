# Tabla de priorización de hipótesis

## Resumen

| # | Causa | Fase DT | Métrica | Periodo | Patrón esperado | Condición de refutación | Estado |
|---|-------|---------|---------|---------|-----------------|-------------------------|--------|
| 1 | Exceso de vehículos particulares | Definir | % de vehículos particulares con información completa y verificada | Mensual | ≥ 98% | ≤ 93% | — |
| 2 | Deficiencias del sistema de transporte público | Empatizar | Índice de cobertura verificada del transporte público (ICV) | Anual | ≥ 37% | ≤ 31% | — |
| 3 | Infraestructura vial insuficiente o congestionada | Definir | % de segmentos viales con mantenimiento registrado | Anual | ≥ 71% | ≤ 65% | — |

---

## Hipótesis 1 — Exceso de vehículos particulares

| Campo | Contenido |
|-------|-----------|
| **Causa** | Exceso de vehículos particulares |
| **Fase DT origen** | Definir |
| **Insight de empatía** | El ciudadano valora la flexibilidad y el control de sus desplazamientos, por lo que sigue utilizando vehículo particular aun cuando sabe que contribuye a la congestión, porque teme llegar tarde y perder tiempo. |
| **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información de los vehículos particulares, incluyendo estado, historial legal y características relevantes mediante fuentes independientes y confiables, entonces podremos identificar patrones de uso y características del parque automotor asociados con el exceso de vehículos particulares. |
| **Pregunta analítica** | ¿Qué relación existe entre el nivel de implementación del sistema de verificación y diligenciamiento de información vehicular y la cantidad de vehículos particulares registrados y activos? |
| **Variables (nombres exactos)** | 1. Porcentaje de vehículos particulares con información completa y verificada<br>2. Nivel de implementación del sistema de verificación y diligenciamiento de información vehicular<br>3. Cantidad de vehículos particulares registrados y activos<br>4. id_vehiculo<br>5. tipo_vehiculo<br>6. fecha_registro<br>7. fecha_circulacion<br>8. hora_circulacion<br>9. zona_circulacion |
| **Tipo de variable** | 1. Indicador KPI<br>2. Explicativa (X)<br>3. Outcome (Y)<br>4. Control<br>5. Segmento<br>6. Control<br>7. Control<br>8. Explicativa<br>9. Explicativa |
| **Cálculo / Transformación** | — |
| **Métrica (nombre + fórmula)** | Porcentaje de vehículos particulares con información completa y verificada = (Número de vehículos con información completa y verificada / Total de vehículos evaluados) × 100 |
| **Periodo / Segmento** | Mensual, una vez al mes |
| **Patrón esperado (si es cierta)** | ≥ 98% |
| **Condición de refutación** | ≤ 93% |
| **Valor esperado para el ciudadano** | Sensación de bienestar y calidad de vida al pasar menos tiempo en congestiones. |
| **Riesgo si es falsa** | Mayor congestión y tiempos de viaje para los ciudadanos, así como incremento de los costos de desplazamiento y presión sobre la infraestructura vial. |
| **Acción si confirma** | Creación del Registro Único de Circulación Urbana (RUCU): cancelación automática del permiso de rodamiento y emisión de orden de inmovilización directa para todo vehículo que, tras el cruce de datos independientes, presente inconsistencias en su historial legal, técnico-mecánico o de SOAT. |
| **Acción si refuta** | Identificar las variables con mayor cantidad de datos faltantes y corregirlas. |
| **Experimento analítico mínimo** | Sobre la base del RUNT (≈200 mil vehículos reales) se corre una sola consulta que cuente, para los vehículos particulares, cuántos están marcados como ACTIVO (información en orden) y cuántos como INCONSISTENTE, separando el conteo por tipo de vehículo y por ciudad. Si se corre en el sistema oficial de la entidad, confirmar antes permiso de lectura y usuario activo; si se usa el archivo ya descargado, no hace falta.<br><br>Luego se dibuja un gráfico de barras sencillo que compare esos dos porcentajes. Con ese único gráfico se responde la hipótesis: si casi todo aparece verificado (99.8%) pero la inconsistencia se concentra en un grupo distinto (buses o camiones, no carros y motos particulares), la idea original —que verificar más resolvería el exceso de carros particulares— probablemente no es el camino, y hay que ajustar la pregunta antes de construir un sistema nuevo. |
| **Estado (V/A/R)** | — |

---

## Hipótesis 2 — Deficiencias del sistema de transporte público

| Campo | Contenido |
|-------|-----------|
| **Causa** | Deficiencias del sistema de transporte público |
| **Fase DT origen** | Empatizar |
| **Insight de empatía** | El usuario percibe que el transporte público no siempre le ofrece tiempos de viaje predecibles ni comodidad suficiente, por lo que busca alternativas para reducir la incertidumbre en sus desplazamientos diarios. |
| **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información del transporte público, incluyendo estado, historial operativo, cobertura, rutas, frecuencias y demás características relevantes mediante fuentes independientes y confiables, entonces podremos identificar las condiciones asociadas a las deficiencias del sistema de transporte público y orientar acciones para mejorar su funcionamiento. |
| **Pregunta analítica** | ¿Qué relación existe entre el nivel de verificación y disponibilidad de información del sistema de transporte público y los indicadores de cobertura, frecuencia, tiempos de espera y demanda del servicio? |
| **Variables (nombres exactos)** | 1. Índice de cobertura verificada del transporte público para el usuario<br>2. Nivel de verificación y disponibilidad de información del sistema de transporte público<br>3. Indicadores del servicio (cobertura, frecuencia, tiempos de espera y demanda)<br>4. frecuencia_operacion<br>5. cobertura_ruta<br>6. variacion_frecuencia<br>7. variacion_tiempo_recorrido<br>8. estado_operativo_ruta<br>9. fecha_operacion<br>10. hora_operacion |
| **Tipo de variable** | 1. Indicador KPI<br>2. Explicativa (X)<br>3. Outcome (Y)<br>4. Explicativa<br>5. Explicativa<br>6. Explicativa<br>7. Explicativa<br>8. Segmento<br>9. Control<br>10. Segmento |
| **Cálculo / Transformación** | — |
| **Métrica (nombre + fórmula)** | Índice de cobertura verificada del transporte público para el usuario: ICV = (N.° de zonas con cobertura verificada / N.° total de zonas pobladas) × 100 |
| **Periodo / Segmento** | Anual |
| **Patrón esperado (si es cierta)** | ≥ 37% |
| **Condición de refutación** | ≤ 31% |
| **Valor esperado para el ciudadano** | Mayor confiabilidad del servicio, al contar con información actualizada sobre rutas, horarios y condiciones. |
| **Riesgo si es falsa** | Mayor estrés, frustración e inseguridad del ciudadano frente a sus desplazamientos diarios. |
| **Acción si confirma** | Crear canales de seguimiento directo para verificar si las intervenciones aplicadas reducen las quejas de los usuarios sobre el servicio. |
| **Acción si refuta** | Identificar las rutas con mayor cantidad de inconsistencias. |
| **Experimento analítico mínimo** | Primero se corre una sola consulta sobre el archivo de paraderos del SITP, pidiendo que cuente por localidad cuántos paraderos hay y qué porcentaje tiene su información completa. Si se corre en el sistema oficial, confirmar antes usuario y permiso de lectura; con el archivo descargado no se requiere nada más.<br><br>Segundo, se dibuja un único gráfico de barras con esos resultados por localidad. Si la información ya está casi toda completa y pareja en todas partes (99.5%), pero la cantidad de paraderos varía muchísimo entre localidades (31 veces más en Kennedy que en La Candelaria), el problema real no es falta de datos verificados sino falta de paraderos físicos en ciertas zonas, algo que verificar información no soluciona. |
| **Estado (V/A/R)** | — |

---

## Hipótesis 3 — Infraestructura vial insuficiente o congestionada

| Campo | Contenido |
|-------|-----------|
| **Causa** | Infraestructura vial insuficiente o congestionada |
| **Fase DT origen** | Definir |
| **Insight de empatía** | Las personas sienten frustración e impotencia al pasar largas horas en congestión y han llegado a normalizar los trancones como parte inevitable de su rutina diaria en Bogotá. |
| **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información de la infraestructura vial, incluyendo estado, capacidad, nivel de congestión, mantenimiento y demás características relevantes mediante fuentes independientes y confiables, entonces podremos identificar las condiciones de la infraestructura asociadas con los niveles de congestión vehicular. |
| **Pregunta analítica** | ¿Cómo varía el nivel de congestión vehicular según el nivel de verificación y disponibilidad de información sobre la infraestructura vial en los diferentes corredores de la ciudad? |
| **Variables (nombres exactos)** | 1. Porcentaje de segmentos viales con mantenimiento registrado<br>2. Nivel de verificación y disponibilidad de información sobre la infraestructura vial<br>3. Nivel de congestión vehicular registrado en los corredores viales<br>4. Estado de la vía<br>5. Capacidad vial<br>6. Nivel de congestión<br>7. Estado de mantenimiento<br>8. Tipo de vía<br>9. Localidad<br>10. Fecha de medición<br>11. Hora de medición |
| **Tipo de variable** | 1. Indicador KPI<br>2. Explicativa (X)<br>3. Outcome (Y)<br>4. Explicativa<br>5. Explicativa<br>6. Resultado<br>7. Explicativa<br>8. Segmento<br>9. Segmento<br>10. Control<br>11. Control |
| **Cálculo / Transformación** | — |
| **Métrica (nombre + fórmula)** | Porcentaje de segmentos viales con mantenimiento registrado = (Segmentos con mantenimiento registrado / Total de segmentos evaluados) × 100 |
| **Periodo / Segmento** | Anual |
| **Patrón esperado (si es cierta)** | ≥ 71% |
| **Condición de refutación** | ≤ 65% |
| **Valor esperado para el ciudadano** | Mayor confianza al saber que las condiciones de las vías son verificadas y analizadas con información confiable, permitiendo tomar decisiones que contribuyan a mejorar la movilidad de la ciudad. |
| **Riesgo si es falsa** | Incremento del tiempo promedio de desplazamiento de los habitantes de Bogotá en minutos por viaje, debido a la persistencia de las condiciones de infraestructura vial asociadas con la congestión. |
| **Acción si confirma** | Identificar y priorizar los tramos viales con mayor congestión para intervención inmediata. |
| **Acción si refuta** | Reformular los criterios de verificación. |
| **Experimento analítico mínimo** | Primero se corre una sola consulta sobre el archivo de segmentos viales de la UMV, agrupando por tipo de superficie de la vía y calculando dos cosas: qué porcentaje de esos segmentos tiene mantenimiento registrado y cuál es su puntaje promedio de deterioro. Si se corre en el sistema oficial, confirmar antes usuario y permiso de lectura.<br><br>Segundo, se dibuja un único gráfico de barras con ese resultado por tipo de vía. A diferencia de los casos anteriores, aquí el dato sí muestra un problema real: solo el 38% de las vías tienen mantenimiento registrado (muy por debajo del 66% supuesto), y ese porcentaje varía mucho según el tipo de vía, siendo más alto donde la vía ya está más deteriorada. La información sí está incompleta y desigual, lo cual respalda la idea original. Lo único que debe ajustarse antes de seguir es la línea base del indicador, porque la realidad está más lejos de la meta de lo calculado. |
| **Estado (V/A/R)** | — |

---

# Ficha de indicador

## Ficha 1 — Vehículos particulares

| Paso | Campo | Contenido |
|------|-------|-----------|
| — | **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información de los vehículos particulares, incluyendo estado, historial legal y características relevantes mediante fuentes independientes y confiables, entonces podremos identificar patrones de uso y características del parque automotor asociados con el exceso de vehículos particulares. |
| 1 | **¿Qué hago? (Acción)** | Identificar los patrones de circulación de los vehículos particulares en Bogotá. |
| 1 | **¿Cómo lo hago? (Método)** | Analizar registros de movilidad según horarios, días, zonas y principales corredores viales de la ciudad. |
| 1 | **¿Para qué lo hago? (Propósito)** | Para determinar en qué horarios y zonas se concentra la circulación de vehículos particulares. |
| 2 | **Aspecto específico a medir** | Nivel de completitud y verificación de la información registrada de los vehículos particulares. |
| 2 | **Público objetivo** | Equipo encargado de recopilar, verificar y diligenciar la información del parque automotor particular de Bogotá. |
| 2 | **Dimensión** | Calidad (¿cumple estándares?) |
| 3 | **Nombre del indicador** | Porcentaje de vehículos particulares con información completa y verificada. |
| 3 | **Numerador (Variable Y)** | Número de vehículos particulares cuya información de estado, historial legal y características relevantes está completa y verificada mediante fuentes confiables e independientes. |
| 3 | **Denominador (Población)** | Total de vehículos particulares incluidos en el proceso de recopilación y diligenciamiento de información. |
| 3 | **Fórmula** | (Número de vehículos con información completa y verificada / Total de vehículos evaluados) × 100 |
| 3 | **Prueba de estrés** | Evaluar el indicador bajo condiciones de alta exigencia, aumentando el número de vehículos particulares que deben ser registrados y verificados y utilizando diferentes fuentes de información independientes. Se comprobaría si el sistema mantiene un alto porcentaje de registros completos y verificados cuando existe mayor volumen de información, datos inconsistentes o dificultades para consultar las fuentes. Si el indicador disminuye significativamente ante estas condiciones, sería necesario fortalecer el proceso de verificación y diligenciamiento para garantizar la confiabilidad de la información. |
| 4 | **Unidad / Tipo** | Porcentaje (%) |
| 5 | **Frecuencia de medición** | Mensual: una vez al mes |
| 5 | **Fuente de datos** | Observatorio de Movilidad de Bogotá |
| 6 | **Línea base** | 0.94 (94%) |
| 6 | **Patrón esperado (meta)** | ≥ 98% |
| 6 | **Condición de refutación** | ≤ 93% |

## Ficha 2 — Transporte público

| Paso | Campo | Contenido |
|------|-------|-----------|
| — | **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información del transporte público, incluyendo estado, historial operativo, cobertura, rutas, frecuencias y demás características relevantes mediante fuentes independientes y confiables, entonces podremos identificar las condiciones asociadas a las deficiencias del sistema de transporte público y orientar acciones para mejorar su funcionamiento. |
| 1 | **¿Qué hago? (Acción)** | Identificar las condiciones de operación del transporte público en Bogotá. |
| 1 | **¿Cómo lo hago? (Método)** | Analizar datos de frecuencia de paso, tiempos de espera, cobertura de rutas, disponibilidad del servicio y demanda por zonas y horarios. |
| 1 | **¿Para qué lo hago? (Propósito)** | Para determinar las condiciones de operación que presentan mayores variaciones en el sistema de transporte público. |
| 2 | **Aspecto específico a medir** | Nivel de cobertura del sistema de transporte público verificado en zonas donde reside o se moviliza la población usuaria. |
| 2 | **Público objetivo** | Usuarios actuales y potenciales del transporte público en Bogotá. |
| 2 | **Dimensión** | Eficacia |
| 3 | **Nombre del indicador** | Índice de cobertura verificada del transporte público para el usuario. |
| 3 | **Numerador (Variable Y)** | Número de zonas/localidades con presencia de rutas de transporte público verificadas mediante fuentes independientes. |
| 3 | **Denominador (Población)** | Número total de zonas/localidades habitadas en Bogotá que requieren servicio de transporte público. |
| 3 | **Fórmula** | ICV = (N.° de zonas con cobertura verificada / N.° total de zonas pobladas) × 100 |
| 3 | **Prueba de estrés** | Aplicar el indicador a un subconjunto de rutas con alta demanda de usuarios (por ejemplo, corredores troncales de mayor afluencia) y compararlo con el resultado global del sistema. Si el porcentaje de deficiencias en las rutas de alta demanda es sustancialmente mayor que el promedio general, el indicador agregado está diluyendo problemas críticos que afectan a más usuarios, lo que obliga a desagregar el reporte por nivel de demanda para orientar las acciones de mejora hacia donde generan mayor impacto. |
| 4 | **Unidad / Tipo** | Porcentaje (%) |
| 5 | **Frecuencia de medición** | Anual |
| 5 | **Fuente de datos** | Datos Abiertos Bogotá |
| 6 | **Línea base** | 0.32 (32%) |
| 6 | **Patrón esperado (meta)** | ≥ 37% |
| 6 | **Condición de refutación** | ≤ 31% |

## Ficha 3 — Infraestructura vial

| Paso | Campo | Contenido |
|------|-------|-----------|
| — | **Supuesto central** | Si implementamos un sistema de verificación y diligenciamiento completo de la información de la infraestructura vial, incluyendo estado, capacidad, nivel de congestión, mantenimiento y demás características relevantes mediante fuentes independientes y confiables, entonces podremos identificar las condiciones de la infraestructura asociadas con los niveles de congestión vehicular. |
| 1 | **¿Qué hago? (Acción)** | Implementar un sistema de verificación y análisis de datos sobre la infraestructura vial. |
| 1 | **¿Cómo lo hago? (Método)** | Integrar información de diferentes fuentes independientes, validar su consistencia y comparar las condiciones de las vías con los niveles de congestión registrados. |
| 1 | **¿Para qué lo hago? (Propósito)** | Determinar qué condiciones de la infraestructura tienen mayor relación con los niveles de congestión vehicular y orientar acciones de mejora. |
| 2 | **Aspecto específico a medir** | Nivel de información completa, verificada y analizada sobre las condiciones de la infraestructura vial. |
| 2 | **Público objetivo** | Habitantes de Bogotá. |
| 2 | **Dimensión** | Calidad |
| 3 | **Nombre del indicador** | Porcentaje de segmentos viales con mantenimiento registrado. |
| 3 | **Numerador (Variable Y)** | Número de segmentos viales con información de mantenimiento registrada. |
| 3 | **Denominador (Población)** | Total de segmentos viales evaluados. |
| 3 | **Fórmula** | (Segmentos con mantenimiento registrado / Total de segmentos evaluados) × 100 |
| 3 | **Prueba de estrés** | Evaluar el comportamiento del indicador bajo diferentes escenarios de disponibilidad de información sobre el mantenimiento de los segmentos viales de Bogotá, con información completa, parcial o inexistente. Por ejemplo, comparar un escenario en el que el 90% de los segmentos cuenta con registros de mantenimiento frente a escenarios del 70%, 50% y 30%. El indicador deberá aumentar cuando exista mayor cantidad de segmentos con información registrada y disminuir cuando aumenten los segmentos sin información. Esto permite determinar la sensibilidad del indicador ante cambios en la disponibilidad de los registros y verificar si la información recopilada es suficiente para analizar la relación entre las condiciones de mantenimiento y los niveles de congestión vehicular. |
| 4 | **Unidad / Tipo** | Porcentaje (%) |
| 5 | **Frecuencia de medición** | Anual |
| 5 | **Fuente de datos** | Datos Abiertos Bogotá |
| 6 | **Línea base** | 0.66 (66%) |
| 6 | **Patrón esperado (meta)** | ≥ 71% |
| 6 | **Condición de refutación** | ≤ 65% |

---

# Anexo: guía de diligenciamiento

- **Causa:** ¿Qué crees que está pasando "detrás" del síntoma? Debe sonar a mecanismo, no a queja.
- **Fase DT origen:** ¿De qué momento de Design Thinking salió?
- **Insight de empatía:** Una observación o cita corta que te inspiró la causa.
- **Supuesto central:** ¿Qué crees que une la causa con el resultado? Es la "apuesta".
- **Pregunta analítica:** Forma neutra y medible de la causa.
  1. Está estrictamente prohibido utilizar adjetivos calificativos como "bueno", "malo", "eficiente" o "exitoso" dentro de la formulación de la pregunta.
  2. Evite redactar preguntas cerradas cuya única respuesta lógica sea un "sí" o un "no", imposibilitando el análisis exploratorio de datos.
  3. No incluya la solución deseada como parte implícita de la pregunta analítica, sesgando el trabajo del ingeniero de datos.
  4. No formule preguntas tan amplias o filosóficas que sea imposible responderlas mediante una consulta estructurada a una base de datos real.
  5. Asegúrese de que la pregunta apunte directamente a medir la relación entre la variable explicativa y la variable de resultado.
- **Variables (nombres exactos):** Columnas que usarás tal cual aparecen en la base (no inventes nombres).
- **Tipo:** Etiqueta cada variable.
  1. *Outcome:* lo que quieres explicar (ej. recompra_30d).
  2. *Explicativa:* lo que crees que causa (ej. comentario_malestar).
  3. *Control:* cosas que pueden distorsionar (ej. canal).
  4. *Segmento:* variable para cortar resultados (ej. canal, zona).
- **Cálculo / Transformación:** Operaciones necesarias antes de la métrica final.
- **Métrica:** Nombre corto + cómo se calcula.
- **Periodo / Segmento:** Rango temporal y cortes.
- **Patrón esperado:** La condición numérica que esperas ver si tu causa es real.
- **Condición de refutación:** El rango o comparación que tiraría tu hipótesis. Debe ser diferente (no repetir con "no").
- **Valor esperado para usuario/ciudadano:** Beneficio concreto si confirmas la hipótesis, en lenguaje humano. Debería sonar a mejora perceptible, no a KPI interno.
- **Riesgo si es falsa:** Qué perderías si sigues insistiendo en esta causa equivocada. Ayuda a priorizar falsar rápido.
- **Acción si confirma:** Movimiento específico inmediato (no "optimizar estrategia"). Debe ser ejecutable en la organización.
- **Acción si refuta:** Ruta alternativa (no repetir la de confirmar).
- **Experimento analítico mínimo:** Qué harás para probarla en pequeño (query + visual en una línea).
- **Estado (V/A/R):** Semáforo.
  - **V (Verde):** todos los campos listos, se puede correr hoy.
  - **A (Amarillo):** falta 1 cosa (umbral, nombre exacto o acción).
  - **R (Rojo):** falta variable clave o patrón, no avanzar.
