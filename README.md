# Análisis del comportamiento de clientes y logística en un eCommerce brasileño (SQL + Visualización)

## Descripción general

Este proyecto aplica el ciclo de vida del análisis de datos para explorar el comportamiento de los clientes y la eficiencia logística en una tienda online brasileña multirubro. A partir de un dataset real de la plataforma Olist, se busca entender cómo compran los clientes, cómo varían los tiempos de entrega, y qué factores afectan la satisfacción, rentabilidad y recurrencia.

El análisis se desarrolló utilizando SQL para la exploración y extracción de datos en BigQuery, y se complementó con visualizaciones interactivas en Looker Studio.

## Objetivo del análisis

Responder a la pregunta de negocio:

**¿Qué factores influyen en la conversión, satisfacción y eficiencia logística en un eCommerce multivendedor?**

## Ciclo de vida del análisis de datos aplicado

### 1. Preguntar

Se definieron las siguientes preguntas clave:

#### Funnel de pedidos
- ¿Cuántos pedidos se completan por mes? ¿Cuál es la tasa de entregas exitosas?
- ¿Cuál es el tiempo promedio entre la compra y la entrega?
- ¿Cuáles son los principales motivos de cancelación?

#### Análisis de satisfacción
- ¿Qué calificaciones y comentarios dejan los usuarios?
- ¿Qué productos o vendedores reciben más reclamos?
- ¿Cómo varía la satisfacción según el tipo de producto, región o tiempo de entrega?

#### Comportamiento del cliente
- ¿Cuántos pedidos hace en promedio un cliente?
- ¿Cuál es la recurrencia y ticket promedio?
- ¿Qué cohortes de clientes son más rentables?

#### Análisis de productos y categorías
- ¿Cuáles son los productos y categorías más vendidos?
- ¿Qué productos generan más ingresos?
- ¿Cuáles tienen alta devolución o baja calificación?

#### Logística y regiones
- ¿Desde qué regiones compran más los clientes?
- ¿Qué vendedores despachan más rápido?
- ¿Dónde hay más demoras o reclamos?

### 2. Preparar

Se utilizó el dataset público de Kaggle:

**Brazilian eCommerce Public Dataset by Olist**  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

El dataset contiene más de 100,000 pedidos con detalles de productos, pagos, entregas, calificaciones, clientes y vendedores.

Se cargaron y modelaron las siguientes tablas en BigQuery:

- orders
- order_items
- customers
- products
- sellers
- order_reviews
- order_payments
- product_category_name_translation

### 3. Procesar

- Se eliminaron registros incompletos y duplicados.
- Se estandarizaron nombres de columnas, fechas y tipos de datos.
- Se crearon vistas en BigQuery para facilitar el análisis por usuario, producto, pedido y vendedor.
- Se construyó un modelo relacional (estrella) para el análisis.

### 4. Analizar

Se organizaron los análisis en cinco bloques principales:

#### 1. Funnel de pedidos
- Cantidad de pedidos por estado (delivered, canceled, etc.)
- Tiempos promedio de entrega y despacho
- Proporción de entregas a tiempo vs. retrasadas

#### 2. Análisis de satisfacción
- Distribución de calificaciones (1–5 estrellas)
- Análisis de comentarios de clientes
- Ranking de productos/vendedores con mejores y peores calificaciones

#### 3. Comportamiento del cliente
- Cantidad de pedidos por cliente
- Análisis de clientes nuevos vs. recurrentes
- Cohortes mensuales por primera compra

#### 4. Productos y categorías
- Productos más vendidos por volumen e ingresos
- Categorías con mayor
