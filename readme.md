# Análisis de Segmentación de Clientes E-commerce (RFM + Clustering)

## 📌 Descripción del Proyecto

Este proyecto realiza un análisis de datos transnacionales de una empresa minorista en línea con sede en el Reino Unido. El objetivo principal es explorar el comportamiento de compra de los clientes y aplicar técnicas de **Machine Learning** para segmentarlos mediante un modelo de agrupamiento (**Clustering**).

> **Nota:** Este archivo representa la primera fase del proyecto ("archivo sucio" de exploración y modelado inicial). El desarrollo futuro incluirá una interfaz interactiva.

## 📊 Dataset

El conjunto de datos contiene transacciones ocurridas entre el **01/12/2010 y el 09/12/2011**. La empresa se especializa en regalos únicos y cuenta con una base de clientes que incluye tanto consumidores individuales como mayoristas.

* **Origen:** [Kaggle - E-commerce Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data/data).
* **Variables Clave:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, y `Country`.

## 🛠️ Metodología y Pipeline

### 1. Exploración y Limpieza de Datos (EDA)

Se realizó un diagnóstico inicial de la calidad de los datos, identificando:

* **Valores Nulos:** Presencia significativa de nulos en la columna `CustomerID` y algunos en `Description`.
* **Anomalías en Cantidades:** Identificación de registros con `Quantity` negativa (posibles devoluciones) y `UnitPrice` en cero o negativo (ajustes de deuda o errores).
* **Similitud de Textos:** Uso de la distancia de Levenshtein para identificar descripciones de productos redundantes o con errores tipográficos.

### 2. Ingeniería de Características: Modelo RFM

Para segmentar a los clientes, se transformaron las transacciones en métricas **RFM**:

* **Recency (Recencia):** Días transcurridos desde la última compra.
* **Frequency (Frecuencia):** Cantidad total de transacciones por cliente.
* **Monetary (Monetario):** Valor total de las compras realizadas.

### 3. Segmentación con K-Means

Se aplicó el algoritmo **K-Means** sobre los datos estandarizados para agrupar a los clientes en clústeres con características similares.

Los resultados preliminares muestran perfiles diferenciados, por ejemplo:

* **Clientes Inactivos:** Alta recencia y baja frecuencia.
* **Clientes VIP/Leales:** Baja recencia y altos niveles de gasto y frecuencia.

## 🚀 Tecnologías Utilizadas

* **Python 3.x**
* **Pandas & NumPy:** Manipulación de datos.
* **Matplotlib & Seaborn:** Visualización estática.
* **Scikit-learn:** Preprocesamiento (`StandardScaler`) y modelado (`KMeans`).
* **Levenshtein:** Análisis de similitud de cadenas de texto.

## 🏗️ Próximos Pasos

* Implementación de visualizaciones interactivas con **Plotly**.
* Desarrollo de un Dashboard de análisis de clientes utilizando **Streamlit**.
* Refinamiento de la limpieza de datos para manejar devoluciones y valores atípicos (outliers).

---

*Este proyecto está en desarrollo activo.*