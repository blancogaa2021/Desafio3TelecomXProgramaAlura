# **Telecom X – Parte 2: Predicción de Cancelación (Churn)**

### **📣 Historia del Desafío**

¡Felicidades\! 🎉 Has sido promovido después de tu excelente desempeño en el análisis exploratorio de la cancelación de clientes en Telecom X. Tu dedicación, claridad al comunicar los datos y visión estratégica marcaron la diferencia.

Ahora, ¡has sido invitado oficialmente a formar parte del equipo de Machine Learning de la empresa\!

### **🎯 Misión**

Tu nueva misión es desarrollar modelos predictivos capaces de prever qué clientes tienen mayor probabilidad de cancelar sus servicios. La empresa quiere anticiparse al problema de la cancelación, y te corresponde a ti construir un pipeline robusto para esta etapa inicial de modelado.

### **🧠 Objetivos del Desafío**

* Preparar los datos para el modelado (tratamiento, codificación, normalización).  
* Realizar análisis de correlación y selección de variables.  
* Entrenar dos o más modelos de clasificación.  
* Evaluar el rendimiento de los modelos con métricas clave.  
* Interpretar los resultados, incluyendo la importancia de las variables.  
* Crear una conclusión estratégica señalando los principales factores que influyen en la cancelación.

### **🧰 Lo que vas a practicar**

✅ Preprocesamiento de datos para Machine Learning  
✅ Construcción y evaluación de modelos predictivos  
✅ Interpretación de resultados y entrega de insights  
✅ Comunicación técnica con enfoque estratégico

## **Análisis Predictivo de Evasión de Clientes**

### **Propósito del Análisis**

El objetivo principal de este proyecto es construir y evaluar modelos de machine learning para **predecir la probabilidad de que un cliente cancele su servicio (churn)**. Utilizando datos históricos, identificamos los patrones de comportamiento y las características que más influyen en la decisión de un cliente de abandonar la empresa. El resultado final es una herramienta que permite a Telecom X anticiparse a la evasión y aplicar estrategias de retención de manera proactiva.

### **Estructura del Proyecto**

El repositorio está organizado de la siguiente manera:

* datos\_tratados.csv: El conjunto de datos limpio y preprocesado, listo para ser utilizado por los modelos.  
* modelo\_predictivo\_churn.ipynb: El Jupyter Notebook que contiene todo el pipeline de machine learning, desde la carga de datos hasta la evaluación final y la interpretación de resultados.  
* assets/: Carpeta que contiene las visualizaciones generadas, como el gráfico de importancia de variables.  
* README.md: Este archivo, que documenta el proyecto.

### **Proceso de Preparación de los Datos**

1. **Clasificación de Variables:** Los datos se componen de variables numéricas (como Meses\_Contrato y Cargo\_Mensual) y categóricas (como Contrato y Metodo\_Pago).  
2. **Codificación (Encoding):** Las variables categóricas se transformaron a un formato numérico utilizando la técnica de **one-hot encoding** (pd.get\_dummies), permitiendo que los algoritmos de machine learning puedan procesarlas.  
3. **Balanceo de Clases:** Se detectó un desbalance significativo en la variable objetivo Evasion (73.5% No / 26.5% Sí). Para evitar que los modelos se sesgaran hacia la clase mayoritaria, se aplicó la técnica de oversampling **SMOTE**, generando un conjunto de datos de entrenamiento perfectamente balanceado (50/50).  
4. **Separación de Datos:** El conjunto de datos balanceado se dividió en un **70% para entrenamiento** y un **30% para prueba**, asegurando que el modelo se evalúe con datos que no ha visto antes.  
5. **Normalización:** Se aplicó la **estandarización** (StandardScaler) a los datos de entrenamiento para el modelo de Regresión Logística, ya que es sensible a la escala de las variables. Esta decisión asegura que ninguna variable domine el modelo solo por tener una magnitud mayor.

### **Instrucciones para Ejecutar el Cuaderno**

Para replicar este análisis, sigue estos pasos:

1. Asegúrate de tener Python 3 instalado.  
2. Instala las bibliotecas necesarias:  
   pip install pandas matplotlib seaborn scikit-learn imbalanced-learn

3. Abre el archivo modelo\_predictivo\_churn.ipynb en un entorno como Jupyter Notebook o JupyterLab.  
4. Ejecuta las celdas en orden. El código cargará datos\_tratados.csv y realizará todo el proceso automáticamente.

## **Resultados y Conclusiones del Modelo Predictivo**

Se entrenaron y evaluaron dos modelos de clasificación: **Regresión Logística** y **Random Forest**.

El modelo **Random Forest** demostró un rendimiento superior, con una **exactitud (accuracy) del 83%** en el conjunto de prueba, superando a la Regresión Logística (77%). Este modelo es más robusto para capturar las relaciones complejas y no lineales presentes en los datos.

### **Análisis de la Importancia de las Variables**

El modelo Random Forest nos permite identificar qué factores son más decisivos a la hora de predecir una cancelación. A continuación se muestra el gráfico con las 10 variables más importantes:

<img width="1192" height="702" alt="image" src="https://github.com/user-attachments/assets/c7cca7b5-3040-4c60-bdb4-637b333a5202" />


### **Conclusión Final**

El análisis predictivo confirma que la evasión de clientes no es aleatoria, sino que está fuertemente influenciada por factores contractuales y de costo. Los principales factores que influyen en la cancelación son:

1. **customer\_tenure (Antigüedad del Cliente):** Es el predictor más fuerte. Los clientes nuevos tienen un riesgo de cancelación mucho mayor.  
2. **Cargo\_Mensual:** Facturas más altas están directamente relacionadas con una mayor probabilidad de evasión.  
3. **Contrato\_Month-to-month:** La falta de un contrato a largo plazo es un indicador clave de riesgo.  
4. **Cargo\_Total:** Un cliente que ha gastado más en total a lo largo del tiempo es más leal.  
5. **Metodo\_Pago\_Electronic check:** El uso de este método de pago manual está asociado a un mayor riesgo.

### **Estrategias de Retención Sugeridas**

* **Fomentar la migración de contratos "Month-to-month"** a planes anuales o de dos años mediante ofertas personalizadas.  
* **Revisar la estructura de precios** y la calidad del servicio para los segmentos de clientes con Cargo\_Mensual más elevado.  
* **Implementar programas de lealtad y seguimiento** para clientes con baja antigüedad (customer\_tenure), enfocándose en mejorar su experiencia durante los primeros meses críticos.
