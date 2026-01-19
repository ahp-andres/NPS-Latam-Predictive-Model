# NPS-Latam-Predictive-Model
Modelo de Machine Learning para predecir NPS y simulador de estrategias de fidelización para LATAM Airlines.

# ✈️ Optimización de NPS para LATAM Airlines

> *"Un enfoque basado en datos para transformar la experiencia del cliente: De la intuición a la predicción."*

Este proyecto presenta una solución de **Business Analytics** que integra técnicas de Ciencia de Datos y Machine Learning para resolver un problema crítico en la industria aeronáutica: la variabilidad en la satisfacción del cliente (NPS) y su impacto en la rentabilidad.

## 🎯 Objetivos de la Investigación
El propósito central fue desarrollar un sistema de soporte a la decisión (DSS) capaz de:
1.  **Predecir** con alta precisión la probabilidad de que un pasajero se convierta en detractor.
2.  **Cuantificar** el impacto de variables operativas (Wifi, Comida, Confort) en la lealtad del cliente.
3.  **Simular** escenarios de inversión para optimizar el ROI en mejoras de servicio.

---

## 🔍 Análisis Exploratorio: Hipótesis vs. Realidad
Antes del modelado, se realizó un análisis estadístico para validar qué factores influyen realmente en la percepción del usuario, desafiando las creencias tradicionales del negocio.

### Hallazgo: La Supremacía de la Experiencia
> ![Heatmap de Correlación](heatmap_proyecto.jpeg)
>
> * **Evidencia Estadística:** El mapa de calor (Heatmap) reveló una correlación significativa entre la **Experiencia a Bordo** y la satisfacción global, superando a variables como "Retraso" o "Precio".
> * **Implicancia Estratégica:** Los datos sugieren que la inversión en *User Experience* (UX) —específicamente confort y conectividad— tiene un retorno marginal superior en la retención que la reducción de costos en tarifas.

---

## 🛠️ Metodología y Arquitectura
Se implementó un pipeline de procesamiento de datos riguroso para asegurar la robustez y escalabilidad del modelo.

### 1. Ingeniería de Características (Feature Engineering)
* **Archivo:** `Modelo_Predictivo_NPS.ipynb`
* **Reducción de Dimensionalidad:** Se aplicó la técnica **RFE (Recursive Feature Elimination)** para depurar el dataset, aislando las 26 variables predictoras más relevantes y eliminando el ruido estadístico.
* **Selección del Modelo:** Tras evaluar múltiples algoritmos, se seleccionó **XGBoost Classifier** optimizado mediante `GridSearchCV`, debido a su capacidad superior para manejar relaciones no lineales en los datos.

### 2. Evaluación del Desempeño
> ![Matriz de Resultados](resultados_finales.jpeg)
>
> * **Minimización del Riesgo:** El modelo fue calibrado priorizando la métrica de **Recall (Sensibilidad)** para la clase "Detractor".
> * **Interpretación:** Desde una perspectiva de negocio, esto minimiza los "Falsos Negativos", asegurando que el sistema alerte sobre casi la totalidad de los clientes en riesgo de fuga para una intervención temprana.

### 3. Despliegue: Simulador Interactivo
Como fase final, se desarrolló una prueba de concepto (PoC) para facilitar la adopción de la herramienta por parte de los stakeholders no técnicos.

> **Interfaz de Usuario (Gradio):**
>
> ![Simulador de Escenarios](demo_app_gradio.jpeg)
>
> * **Funcionalidad:** Esta interfaz permite a la gerencia manipular variables críticas en tiempo real y visualizar la fluctuación proyectada del NPS, cerrando la brecha entre el modelo matemático y la estrategia comercial.

---

## 🚀 Impacto de Negocio y Hoja de Ruta (Roadmap)

La analítica predictiva no tiene valor si no cambia la operación. Basado en los insights del modelo, se proponen las siguientes acciones estratégicas:

### 1. Redefinición del CAPEX (Inversión)
* **El Insight:** El modelo indica que el "Confort del Asiento" y la "Conectividad (Wifi)" son los predictores dominantes de lealtad, por encima de la puntualidad (dentro de márgenes normales).
* **La Recomendación:** Reasignar presupuesto de marketing tradicional hacia la modernización de cabinas y acuerdos de SLA (Service Level Agreement) para Wifi de alta velocidad.
    * *Meta:* Convertir la conectividad en un diferenciador competitivo, no en un *commodity*.

### 2. Gestión Proactiva del Churn (Fuga)
* **El Insight:** Podemos identificar detractores con alta precisión antes de que aterrice el avión.
* **La Recomendación:** Integrar el modelo XGBoost al CRM de la aerolínea para activar protocolos de "Recuperación de Servicio" en tiempo real (ej. ofrecer un upgrade o compensación inmediata a pasajeros identificados como "Alto Riesgo" por el algoritmo).

### 3. Hiper-Personalización por Segmento
* **El Insight:** El modelo detecta comportamientos dispares entre viajeros de negocios y turistas.
* **La Recomendación:** Abandonar las estrategias de "talla única".
    * *Para Business:* Enfocar la comunicación en eficiencia y conectividad.
    * *Para Economy:* Enfocar la comunicación en entretenimiento a bordo y relación calidad-precio.

> **💡 Veredicto Final:**
> *"Este proyecto demuestra que LATAM Airlines puede pasar de un modelo reactivo (analizar encuestas pasadas) a uno proactivo (predecir y corregir la experiencia futura), optimizando cada dólar invertido en la satisfacción del cliente."*

---
*Proyecto desarrollado como parte del Summer Camp PUCP - Inteligencia Artificial | 2026*
