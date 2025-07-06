# Análisis del comportamiento de usuarios en una tienda online (SQL + Visualización)

## Descripción general

Este proyecto aplica el ciclo de vida del análisis de datos para explorar el comportamiento de los usuarios en una tienda online multirubro. A partir de un dataset real de eventos de navegación y compras, se busca entender cómo interactúan los usuarios con la tienda, en qué puntos del proceso de compra se pierden, y qué productos, usuarios o regiones generan mayor conversión o rentabilidad.

El análisis se desarrolló utilizando **SQL** para la exploración y extracción de datos, y se complementó con visualizaciones interactivas en **Looker Studio**.

---

## Objetivo del análisis

**Responder a la siguiente pregunta de negocio:**

> ¿Cómo se comportan los usuarios en una tienda online y qué factores afectan la conversión de visitas en compras?

---

## Ciclo de vida del análisis de datos aplicado

### 1. **Preguntar**
Se definieron las siguientes preguntas clave:

#### Funnel de conversión
- ¿Cuántos usuarios visualizaron productos, agregaron al carrito y realizaron compras?
- ¿Cuál es la tasa de conversión en cada paso del funnel?
- ¿En qué paso del proceso se pierde la mayor cantidad de usuarios?

#### Análisis temporal
- ¿En qué días y horas se concentra la mayor actividad de compra?
- ¿Cómo ha evolucionado la cantidad de compras mes a mes?
- ¿Se observan diferencias entre días hábiles y fines de semana?

#### Productos y categorías
- ¿Cuáles son los productos y categorías más vistos vs. más comprados?
- ¿Qué productos tienen muchas visualizaciones pero pocas compras?
- ¿Cuáles son los productos más rentables?

#### Comportamiento por usuario
- ¿Cuál es el promedio de eventos por usuario?
- ¿Cuántos usuarios compran más de una vez? ¿Cuántos son nuevos?
- ¿Qué cohortes de usuarios (según fecha de registro) convierten mejor?

#### Segmentación por región o dispositivo
- ¿Desde qué regiones o países se genera mayor volumen de compras?
- ¿Qué dispositivos (móvil vs. escritorio) convierten más?

---

### 2. **Preparar**
- Se utilizó un dataset público de Kaggle:  
  **[eCommerce behavior data from multi-category store](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store)**
- El dataset contiene más de **280 millones de registros**, incluyendo eventos como visualizaciones, adiciones al carrito y compras.
- Se cargaron las tablas en **BigQuery** para su análisis.

---

### 3. **Procesar**
- Se identificaron las tablas relevantes: `events`, `orders`, `products`, `customers`, `categories`.
- Se limpiaron los datos eliminando registros incompletos y estandarizando fechas y campos clave.
- Se crearon vistas y consultas SQL para facilitar el análisis por pasos del funnel, cohortes, productos y usuarios.

---

### 4. **Analizar**
Se realizaron múltiples consultas SQL para responder las preguntas clave. Se agrupan los análisis en cinco grandes bloques:

#### 1. Funnel de conversión
- Análisis de eventos view → cart → purchase
- Cálculo de tasas de conversión en cada paso
- Identificación de cuellos de botella

#### 2. Análisis temporal
- Distribución de compras por hora y día
- Evolución de la actividad mensual
- Análisis de estacionalidad y comportamiento por días de la semana

#### 3. Productos y categorías
- Ranking de productos y categorías más vistos vs. más vendidos
- Detección de productos con alto interés pero baja conversión
- Cálculo de margen de ganancia por producto

#### 4. Comportamiento por usuario
- Cálculo del promedio de eventos por usuario
- Segmentación entre usuarios nuevos y recurrentes
- Análisis de cohortes mensuales por fecha de primer evento

#### 5. Segmentación geográfica y por dispositivo
- Análisis del volumen de eventos por país o ciudad
- Comparación de tasas de conversión entre usuarios móviles y de escritorio

---

### 5. **Compartir**
- Se creó un **dashboard interactivo en Looker Studio** que resume los hallazgos clave.
- Incluye filtros por tipo de evento, fecha, categoría, producto y dispositivo.
- El proyecto también incluye visualizaciones de funnel, cohortes, ventas por región y ranking de productos.

🔗 Enlace al dashboard: [Próximamente]

---

### 6. **Actuar**
Se derivan las siguientes recomendaciones:

- Optimizar los pasos intermedios del funnel donde se pierde el mayor porcentaje de usuarios.
- Aplicar promociones dirigidas a productos con alta visualización y baja conversión.
- Rediseñar fichas de producto con bajo rendimiento pese a su popularidad.
- Enfocar esfuerzos comerciales en regiones y horarios de alta conversión.
- Diseñar estrategias diferenciadas según tipo de dispositivo (móvil vs escritorio).
- Usar cohortes para personalizar campañas de retención según antigüedad del usuario.

---
