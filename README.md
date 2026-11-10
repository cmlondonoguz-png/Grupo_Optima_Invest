# Proyecto de analítica financiera | IX Concurso ITM 2026 | Optima Invest

**Curso:** Lenguajes de Programación · Ingeniería Financiera  
**Concurso:** 12 de noviembre de 2026  
**Simulacro:** 10 de noviembre de 2026  
**Tecnología:** Python + Streamlit

## 1. Identificación del proyecto

- **Nombre de la aplicación:** Optima Invest
- **Equipo e integrantes:** Marcela Guerrero / Kevin Jaramillo / Carlos Londoño 
- **Enlace a la aplicación:** [Pendiente / URL]
- **Repositorio del proyecto:** [[URL]](https://github.com/cmlondonoguz-png/Grupo_Optima_Invest/tree/main)
- **Última actualización:** 2026-11-10

## 2. ¿Qué queremos investigar? · S25

**Investiga:** ¿qué significa analizar el comportamiento histórico de un activo financiero? ¿Qué preguntas pueden responderse con datos de mercado y cuáles no?

- **Situación o fenómeno de interés:** Los inversionistas suelen construir portafolios con diferentes activos financieros, pero no siempre conocen si la distribución de su capital es eficiente o si existen combinaciones alternativas que podrían ofrecer una mejor relación entre rentabilidad y riesgo.

Optima Invest busca abordar esta situación mediante el análisis de diferentes activos y la optimización de sus ponderaciones dentro de un portafolio de inversión.
- **Pregunta principal:** ¿Tu portafolio actual es tan rentable como podría serlo, considerando su nivel de riesgo y las posibilidades de diversificación?
- **Objetivo del análisis:** Desarrollar una aplicación de analítica financiera que permita evaluar el rendimiento histórico de un portafolio de inversión, comparar su distribución inicial con diferentes alternativas de optimización y determinar qué combinación de activos presenta una mejor relación entre rentabilidad y riesgo.
- **Importancia financiera:** Permite a los inversionistas retail tomar decisiones basadas en datos cuantitativos en lugar de intuición, demostrando la importancia de la diversificación y la optimización de pesos para mejorar el perfil riesgo-retorno de sus inversiones.
- **Preguntas complementarias:** ¿Cómo afecta la inclusión de un activo de alta volatilidad (criptomoneda) a la estabilidad general de un portafolio tradicional?

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
- **Frecuencia:** Diaria
- **Variables disponibles:** Fecha, Precio de cierre ajustado (Close).
- **Limitaciones de los datos:** Fechas faltantes por festivos de mercado, datos simulados en caso de caída del servidor de Yahoo, y no consideración de costos de transacción ni impuestos.

**Primera prueba:** https://colab.research.google.com/drive/1H8QIkoFmbILgDaXEcKBX8CHj7Ahy7mca#scrollTo=9e126d30

## 4. Metodología de análisis · S25–S26

**Investiga:** ¿qué indicadores permiten responder la pregunta principal? ¿cómo se calculan? ¿qué interpretación y limitaciones tienen?

| Indicador / técnica | ¿Qué mide? | ¿Por qué lo necesitamos? | Implementación |
|---|---|---|---|
| Rendimiento Acumulado | El crecimiento total del capital invertido `(1 + r).cumprod()`. | Muestra la rentabilidad real generada en el período seleccionado. | `app.py` (Línea 146) |
| Volatilidad Anualizada | La dispersión de los retornos `std() * sqrt(252)`. | Cuantifica el riesgo de mercado asumido por el portafolio. | `app.py` (Línea 148) |
| Ratio de Sharpe | Rendimiento total sobre la volatilidad anualizada. | Evalúa la eficiencia del portafolio (riesgo vs. retorno). | `app.py` (Línea 150) |
| Matriz de Correlación | Relación lineal entre activos (Pearson de -1 a 1). | Determina el grado de diversificación real de la cartera. | `app.py` (Línea 174) |
| Optimización SLSQP (Solver) | Asignación óptima de pesos (W) maximizando Sharpe. | Responde a la pregunta de si existe una combinación más eficiente. | `app.py` (Línea 232) |
| Simulación de Monte Carlo | Proyección estocástica de escenarios futuros y VaR 95%. | Estima la probabilidad de pérdida y los peores/mejores escenarios. | `app.py` (Línea 367) |


### Visualizaciones previstas

| Gráfico | Pregunta que ayuda a responder | Variables | Interpretación esperada |
|---|---|---|---|
| Gráfico de Líneas (Base 100) | ¿Cómo se comparan los activos desde un mismo punto de partida? | Precio normalizado, Fecha | Evolución comparativa del crecimiento individual de cada activo. |
| Mapa de Calor (Heatmap) | ¿Qué tan correlacionados están los activos? | Matriz de Correlación | Identificar pares de activos que se mueven en la misma dirección o en direcciones opuestas. |
| Gráfico Circular (Pie Chart) | ¿Cuál es la composición ideal del portafolio? | Pesos óptimos (W), Activos | Visualización rápida de la asignación de capital sugerida por el Solver. |
| Histograma de Simulación | ¿Cuáles son los escenarios probables de rentabilidad? | Frecuencia, Rentabilidad Final | Distribución de los resultados de Monte Carlo, identificando el VaR 95% y el promedio. |

**Primer resultado verificable:** [Enlace a un cálculo o gráfico realizado con datos reales y una interpretación breve]

## 5. Diseño de la aplicación · S25

**Investiga:** ¿cómo se construyen controles, gráficos y métricas con la herramienta elegida? ¿qué sucede cuando el usuario modifica una selección?

- **Usuarios previstos:** Estudiantes de ingeniería financiera, inversionistas retail y entusiastas de las finanzas.
- **Entradas y filtros:** Buscador de tickers, selección múltiple de activos, período histórico (3mo a 2y), capital inicial, fuente de datos y pesos manuales por activo.
- **Secciones de la interfaz:** Se divide en 5 pestañas: 📈 Portafolio, 📊 Estadística, ⚖️ Comparación, 🎲 Montecarlo, e ℹ️ Proyecto.
- **Resultados visibles:** Métricas principales en la parte superior (Rendimiento, Volatilidad, Capital final), diagnóstico general de diversificación, tablas descriptivas, pesos óptimos matemáticos y gráficas interactivas.
- **Interacción principal:** Cuando el usuario ajusta los pesos en la barra lateral, la aplicación normaliza a 100% y recalcula instantáneamente la evolución del portafolio actual frente al portafolio optimizado por el Solver.

**Flujo previsto:**  
Selección de activos y configuración de capital/pesos → Descarga de datos con `yfinance` → Cálculo de matriz de covarianza y rendimientos → Optimización matemática (Scipy) → Comparativa visual → Análisis de riesgo vía Monte Carlo.

**Decisión técnica:** Se utilizó Python por su robustez en cálculos científicos (`numpy`, `scipy`, `pandas`) y Streamlit por su capacidad para desplegar interfaces interactivas de datos rápidamente sin necesidad de desarrollo web tradicional. Plotly se integró por la interactividad visual requerida.

## 6. Construcción y pruebas · S26 (5 de noviembre)

Actualiza esta sección durante el laboratorio de desarrollo.

- **Componentes implementados:** Extracción de datos en tiempo real, normalización de pesos, cálculos descriptivos, optimización de Sharpe mediante SLSQP, simulación de Monte Carlo vectorizada con NumPy, renderizado de visualizaciones dinámicas.
- **Cómo ejecutar la aplicación:**
  pip install -r requirements.txt
  streamlit run app.py
- **Dependencias:** `streamlit`, `pandas`, `numpy`, `yfinance`, `plotly`, `scipy`.
- **Pruebas realizadas:** Se probó la interrupción del API de Yahoo Finance, implementando con éxito un generador de precios simulados como mecanismo de respaldo (fallback) para evitar que la aplicación falle en pleno concurso. Se validó la normalización matemática cuando el usuario excede el 100% en la asignación de pesos manuales.
- **Errores conocidos y cómo se resolvieron:** Las micro-fracciones negativas residuales del optimizador SLSQP (ej. `-1e-16`) se resolvieron aplicando una máscara lambda que convierte a `0.0` cualquier valor menor a `1e-4`.

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
- **Problema financiero y activos:** Dificultad de estructurar un portafolio sin intuición. Presentación de VOO, NU, BTC.
- **Datos y metodología:** Extracción vía yfinance y cálculos de retornos logarítmicos/aritméticos.
- **Demostración de interactividad:** Cambio de pesos en la barra lateral para observar el impacto en el Ratio de Sharpe.
- **Hallazgos e interpretación:** Contraste del portafolio empírico vs optimizado por el Solver de Scipy.
- **Conclusión y limitaciones:** Impacto real de la diversificación matemática y límites de las proyecciones (Monte Carlo).

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
| 2026-10-31 | Marcela, Kevin, Carlos | Definición de lógica y activos | Esbozo del layout en `app.py` | Integrar librerías financieras |
| 2026-11-05 | Marcela, Kevin, Carlos | Implementación del Solver | Script SLSQP funcional en el tab "Estadística" | Desarrollar Monte Carlo |
| 2026-11-10 | Marcela, Kevin, Carlos | Pruebas de simulación y contingencia | Simulador de precios fall-back listo | Preparar simulacro |

## Recursos de consulta

- [Libro de programación y analítica financiera del curso](https://github.com/vyolete/proyecto_analitica_financiera)
- [Documentación de yfinance](https://ranaroussi.github.io/yfinance/)
- [Documentación de pandas](https://pandas.pydata.org/docs/)
- [Documentación de Streamlit](https://docs.streamlit.io/)
- [Documentación de Shiny para R](https://shiny.posit.co/r/)

**Uso del documento:** En S25 desarrolla especialmente las secciones 2 a 5 y registra tu primera prueba; en S26, S27 y S28 actualiza el mismo README. No dupliques información en entregas separadas.
