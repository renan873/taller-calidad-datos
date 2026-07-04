# Taller 3: Calidad y Limpieza de Datos

**Autores:** Renan Rivadeneria, Sol Tuarez, Diego Nicinga, Gabriel Estupiñan.  

## 1. Contexto del Proyecto
Este repositorio contiene el desarrollo del Taller 3 de la asignatura, enfocado en técnicas modernas de detección y limpieza de datos. El objetivo del proyecto fue diagnosticar y tratar problemas de calidad de datos utilizando un entorno de pruebas con el dataset de ventas de la empresa ficticia "Tech Coffee Shop" (`dirty_cafe_sales.csv`). Esto simula un entorno real previo a la manipulación en bases de datos de producción.

## 2. Tecnologías y Librerías Utilizadas
El análisis y limpieza se llevó a cabo en un entorno interactivo (**Google Colab** / **Jupyter Notebook**) bajo **Python 3**. 
Las librerías implementadas incluyen:
- `pandas` y `numpy` para la manipulación y análisis tabular.
- `missingno` y `ydata-profiling` para exploración y visualización inicial de datos faltantes y atípicos.
- `scikit-learn` para aplicar imputaciones, escalado y normalización.
- `pandera` para la definición de esquemas de validación y control estricto de la calidad final de los datos.

## 3. Principales Hallazgos y Decisiones de Limpieza
A lo largo de la ejecución del notebook, se abarcaron las siguientes fases clave:

* **Exploración y diagnóstico:** Mediante `df.info()`, `df.describe()` y visualizaciones de `missingno` se detectaron valores nulos, registros con entradas inconsistentes (ej. "ERROR", "UNKNOWN" en métodos de pago o ubicaciones) y tipos de variables que requerían casteos.
* **Tratamiento de datos faltantes:** Basado en el peso que representaban los datos nulos y corruptos, se aplicaron estrategias de imputación (usando `SimpleImputer`) para salvar datos de ventas viables o se eliminaron filas que carecían de información fundamental de negocio.
* **Escalado y normalización:** Se probaron técnicas de preprocesamiento (como `MinMaxScaler` o `StandardScaler` de Scikit-Learn) sobre las variables cuantitativas (como el precio o total gastado) para compararlas métricamente y evitar sesgos en potenciales modelos analíticos.
* **Validación de calidad:** Como paso definitivo, se construyó un esquema con `pandera` (`DataFrameSchema`) para verificar que el dataset procesado cumpliera estrictamente con las reglas de negocio establecidas, obteniendo un reporte de éxito en la validación.

## 4. Estructura del Repositorio
- `Taller3_calidad__datos.ipynb`: El cuaderno de desarrollo, comentado paso a paso con el código y las conclusiones sustentadas de cada técnica aplicada.
- `README.md`: Este documento que detalla el contexto y resultados.
- Historial de `commits`: Reflejo estructurado del progreso del desarrollo.

## 5. Instrucciones de Ejecución
1. Clona o descarga este repositorio de GitHub.
2. Instala las dependencias listadas si utilizas un entorno local:
