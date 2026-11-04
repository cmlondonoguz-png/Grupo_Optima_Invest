# Proyecto de analítica financiera | IX Concurso ITM 2026 | Optima Invest

**Curso:** Lenguajes de Programación · Ingeniería Financiera  
**Concurso:** 12 de noviembre de 2026  
**Simulacro:** 10 de noviembre de 2026  
**Tecnología:** [Python + Streamlit / R + Shiny / otra interfaz en Python o R]

## 1. Identificación del proyecto

- **Nombre de la aplicación:** Optima Invest
- **Equipo e integrantes:** Marcela Guerrero / Kevin Jaramillo / Carlos Londoño 
- **Enlace a la aplicación:** [Pendiente / URL]
- **Repositorio del proyecto:** [URL]
- **Última actualización:** [AAAA-MM-DD]

## 2. ¿Qué queremos investigar? · S25

**Investiga:** ¿qué significa analizar el comportamiento histórico de un activo financiero? ¿Qué preguntas pueden responderse con datos de mercado y cuáles no?

- **Situación o fenómeno de interés:** Los inversionistas suelen construir portafolios con diferentes activos financieros, pero no siempre conocen si la distribución de su capital es eficiente o si existen combinaciones alternativas que podrían ofrecer una mejor relación entre rentabilidad y riesgo.

Optima Invest busca abordar esta situación mediante el análisis de diferentes activos y la optimización de sus ponderaciones dentro de un portafolio de inversión.
- **Pregunta principal:** ¿Tu portafolio actual es tan rentable como podría serlo, considerando su nivel de riesgo y las posibilidades de diversificación?
- **Objetivo del análisis:**Desarrollar una aplicación de analítica financiera que permita evaluar el rendimiento histórico de un portafolio de inversión, comparar su distribución inicial con diferentes alternativas de optimización y determinar qué combinación de activos presenta una mejor relación entre rentabilidad y riesgo.
- **Importancia financiera:** Importa porque buscamos maximizar la rentabilidad y diversificación del portafolio del inversionista
- **Preguntas complementarias:** [Opcionales]

> **Comprueba:** ¿tu pregunta identifica activos, variables y un período de estudio? ¿Es posible responderla con datos disponibles?

## 3. Activos, datos y alcance · S25

**Investiga:** ¿qué activos se ajustan a tu pregunta? ¿qué datos históricos existen? ¿qué frecuencia, período y fuente utilizarás?

| Activo | Símbolo o ticker | Tipo | Razón para incluirlo |
|---|---|---|---|
| [Activo 1] | [VOO] | [ETF] | [Es un ETF estable historicamente] |
| [Activo 2] | [NU] | [ACCION   ] | [Es una buena accion con bastante proyección a futuro en el sector financiero] |
| [Activo 3] | [BTC] | [Criptomoneda  ] | [Es la criptomoneda mas importante y reconocida a nivel mundial] |

- **Fuente de datos:** Proveedor: finance.yahoo.com link: https://finance.yahoo.com/quote/VOO/
- **Período:** 31 octubre 2025 a 31 octubre 2026
- **Frecuencia:** [Diaria, semanal, mensual...]
- **Variables disponibles:** [Fecha, precio de cierre, volumen...]
- **Limitaciones de los datos:** [Fechas faltantes, zona horaria, ajustes, diferencias de mercado...]

**Primera prueba:** [Enlace al notebook o archivo que descarga o consulta datos; indica qué funcionó y qué no]

## 4. Metodología de análisis · S25–S26

**Investiga:** ¿qué indicadores permiten responder la pregunta principal? ¿cómo se calculan? ¿qué interpretación y limitaciones tienen?

| Indicador / técnica | ¿Qué mide? | ¿Por qué lo necesitamos? | Implementación |
|---|---|---|---|
| [Indicador 1] | [Concepto y fórmula, si aplica] | [Relación con la pregunta] | [Archivo o celda] |
| [Indicador 2] | [Concepto y fórmula, si aplica] | [Justificación] | [Pendiente / enlace] |

No es necesario utilizar todos los indicadores estudiados en clase. Selecciona y justifica únicamente los pertinentes.

### Visualizaciones previstas

| Gráfico | Pregunta que ayuda a responder | Variables | Interpretación esperada |
|---|---|---|---|
| [Gráfico 1] | [Pregunta] | [Variables] | [Qué se podrá observar] |
| [Gráfico 2] | [Pregunta] | [Variables] | [Qué se podrá comparar] |

**Primer resultado verificable:** [Enlace a un cálculo o gráfico realizado con datos reales y una interpretación breve]

## 5. Diseño de la aplicación · S25

**Investiga:** ¿cómo se construyen controles, gráficos y métricas con la herramienta elegida? ¿qué sucede cuando el usuario modifica una selección?

- **Usuarios previstos:** [Quién podría consultar la aplicación]
- **Entradas y filtros:** [Activos, fechas, parámetros...]
- **Secciones de la interfaz:** [Pantalla principal, comparación, riesgo, etc.]
- **Resultados visibles:** [Gráficos, tablas, indicadores y explicaciones]
- **Interacción principal:** [Describe qué cambia cuando el usuario modifica un control]

**Flujo previsto:**  
Selección de activos y parámetros → Obtención de datos → Preparación y cálculos → Visualización → Interpretación.

**Boceto o esquema:** [Inserta una imagen o enlace al diseño, por ejemplo `docs/boceto.png`]

**Decisión técnica:** [¿Por qué usarás Python o R y qué biblioteca de aplicación elegiste?]

## 6. Construcción y pruebas · S26 (5 de noviembre)

Actualiza esta sección durante el laboratorio de desarrollo.

- **Componentes implementados:** [Qué funciona realmente]
- **Cómo ejecutar la aplicación:** [Comandos, dependencias y pasos]
- **Dependencias:** [Archivo `requirements.txt`, `renv.lock` u otro]
- **Pruebas realizadas:** [Caso probado, resultado esperado y resultado obtenido]
- **Errores conocidos y cómo se resolvieron:** [Explicación]
- **Pendientes antes del simulacro:** [Tareas concretas]

> No afirmes que una función está implementada si aún no ha sido probada.

## 7. Hallazgos e interpretación · S26–S28

Para cada hallazgo importante, registra:

1. **Evidencia:** [Gráfico, tabla o indicador con enlace]
2. **Qué muestra:** [Describe el comportamiento observado]
3. **Interpretación financiera:** [Explica su significado en relación con la pregunta]
4. **Limitaciones:** [Qué no puedes concluir de los datos]

**Conclusión provisional o final:** [Respuesta sustentada a la pregunta principal]

> Los resultados históricos no garantizan rendimientos futuros.

## 8. Simulacro · S27 (10 de noviembre)

**Guion de sustentación (3–5 minutos):**
- Problema financiero y activos.
- Datos y metodología.
- Demostración de interactividad.
- Hallazgos e interpretación.
- Conclusión y limitaciones.

**Retroalimentación recibida:** [Observaciones del docente o compañeros]

| Ajuste necesario | Responsable | Estado |
|---|---|---|
| [Ajuste] | [Integrante] | [Pendiente / en proceso / resuelto] |

## 9. Presentación final · S28 (12 de noviembre)

- **Enlace funcional de la aplicación:** [URL]
- **Versión final / commit:** [Enlace]
- **Evidencia de presentación:** [Enlace autorizado]
- **Conclusiones finales:** [Síntesis]
- **Limitaciones y posibles mejoras:** [Descripción]

## 10. Bitácora de trabajo y aportes

| Fecha | Integrante(s) | Investigación o decisión | Avance técnico / evidencia | Próximo paso |
|---|---|---|---|---|
| 2026-11-03 | [Nombre] | [Qué investigamos] | [Enlace a código o documento] | [Acción] |
| 2026-11-05 | [Nombre] | [Decisiones] | [Evidencia] | [Acción] |
| 2026-11-10 | [Nombre] | [Retroalimentación] | [Cambio] | [Acción] |

## Recursos de consulta

- [Libro de programación y analítica financiera del curso](https://github.com/vyolete/proyecto_analitica_financiera)
- [Documentación de yfinance](https://ranaroussi.github.io/yfinance/)
- [Documentación de pandas](https://pandas.pydata.org/docs/)
- [Documentación de Streamlit](https://docs.streamlit.io/)
- [Documentación de Shiny para R](https://shiny.posit.co/r/)

**Uso del documento:** En S25 desarrolla especialmente las secciones 2 a 5 y registra tu primera prueba; en S26, S27 y S28 actualiza el mismo README. No dupliques información en entregas separadas.
