#  Análisis Exploratorio de Datos - Campañas de Marketing Bancario

Este proyecto forma parte del módulo **"Python for Data"**, en el que se realiza un análisis exploratorio de datos (EDA) utilizando **Python** y **Pandas**. El objetivo es comprender qué factores influyen en la suscripción de productos financieros por parte de clientes de un banco.

---

##  Estructura del Proyecto

- `datos`: Contiene los archivos de datos originales (`.csv`, `.xlsx`) y los datos limpios.
- `notebooks`: Archivos `.ipynb` con todo el análisis paso a paso.
- `README.md`: Este documento.

---

##  Objetivo

Analizar dos bases de datos:
- **`bank-additional.csv`**: Información sobre llamadas de campañas de marketing.
- **`customer-details.xlsx`**: Información demográfica y de comportamiento de los clientes.

El objetivo final es descubrir **patrones y relaciones que influyen en la suscripción de un depósito a plazo (`y`)**.

---

##  Herramientas utilizadas

- Python
- Pandas
- Seaborn
- Matplotlib
- Visual Studio Code

---

##  Transformación y limpieza de datos

- Unificación de identificadores entre ambos datasets.
- Conversión de fechas y tipos de datos.
- Eliminación de valores nulos y duplicados.
- Creación de nuevas variables:
  - 'Grupo_edad' (agrupación por rangos de edad)
  - 'Total_kids' (niños + adolescentes en casa)
  - 'Customer_seniority' (antigüedad del cliente en días)

---

##  Análisis descriptivo y visualización

Se analizó cómo influye en la probabilidad de suscripción (`y`) según tres tipos de variables: Variables categóricas, variables continuas y variables macroeconómicas. A continuación se detallara un informe con el análisis desarrollado para cada tipo de variable:

### Variables categóricas:

- Empezamos con el estudio de la probabilidad de suscripción basándonos en la edad de cada cliente. Basándonos en la grafica obtenida, comprobamos que el mayor porcentaje de suscripciones se centra en los mayores de 66 años y en las personas entre 18 y 25 años pero si nos basamos en la cantidad de personas comprobamos que el mayor numero de suscripciones se han registrado en personas entre 26 y 35 años.

- Con respecto al resto de variables, se ha realizado un estudio por separado para cada variable y a su vez se ha averiguado los perfiles mas comunes que aceptan la suscripción y los perfiles mas comunes que la rechazan. Se ha comprobado que el perfil mas común que se suscribe es: Una edad entre 26 y 35 años, cómo hemos visto antes en el estudio del grupo de edad, que trabaja como admin, que su estado es soltero, tiene educación universitaria, se contacto con el cliente mediante móvil y no existe un resultado de la campaña de marketing anterior. A continuación se muestra una tabla con los perfiles mas comunes:

| GRUPO_EDAD | JOB        | MARITAL   | EDUCATION         | CONTACT  | POUTCOME   | Frecuencia | % sobre total |
|------------|------------|-----------|-------------------|----------|------------|------------|---------------|
| 26-35      | admin.     | SINGLE    | university.degree | cellular | NONEXISTENT| 145        | 3.57          |
| 36-50      | admin.     | MARRIED   | university.degree | cellular | NONEXISTENT| 85         | 2.09          |
| 26-35      | admin.     | MARRIED   | university.degree | cellular | NONEXISTENT| 79         | 1.94          |
| 26-35      | admin.     | SINGLE    | high.school       | cellular | NONEXISTENT| 59         | 1.45          |
| 26-35      | admin.     | SINGLE    | university.degree | cellular | SUCCESS    | 51         | 1.26          |

Y se ha realizado lo mismo para los perfiles que menos han realizado la suscripción:

| GRUPO_EDAD | JOB         | MARITAL   | EDUCATION         | CONTACT   | POUTCOME    | Frecuencia | % sobre total |
|------------|-------------|-----------|-------------------|-----------|-------------|------------|---------------|
| 36-50      | blue-collar | MARRIED   | basic.4y          | telephone | NONEXISTENT | 493        | 1.48          |
| 36-50      | blue-collar | MARRIED   | basic.9y          | telephone | NONEXISTENT | 488        | 1.46          |
| 36-50      | blue-collar | MARRIED   | basic.9y          | cellular  | NONEXISTENT | 474        | 1.42          |
| 36-50      | technician  | MARRIED   | professional.course| cellular | NONEXISTENT | 420        | 1.26          |
| 26-35      | blue-collar | MARRIED   | basic.9y          | telephone | NONEXISTENT | 363        | 1.09          |

### Variables continuas:

- Con estas variables se ha realizado el mismo estudio que para las variables categóricas, con el cual voy a desgranar las conclusiones obtenidas:

-- Con respecto a la antigüedad del cliente se ha comprobado que conforme el cliente lleva mas tiempo en ese banco menos ha realizado la suscripción del servicio

-- Fijándonos en los ingresos, comprobamos que no existe gran variación en si se ha realizado la suscripción o no

-- Tambien, al igual que con los ingresos, basándonos en el numero de visitas web mensuales tampoco existe gran variación de un grupo a otro.

-- Con respecto a la duración de la llamada, percibimos en el grafico que a mayor duración e llamada mayor es la probabilidad de que realicen la suscripción.

-- Por ultimo, tanto para el numero de niños en casa como para el numero de contactos de campaña, se observa que no hay gran variación en los distintos rangos.

### Variables macroeconómicas:

-Finalmente, se ha estudiado como afecta las variaciones de las variables macroeconómicas en la probabilidad de realizar la suscripción.

-- Con respecto a EMP.VAR.RATE se observa que se han suscrito mas personas cuando la tasa era mas negativa.

-- Fijándonos en CONS.PRICE.IDX, se realizan mas suscripciones cuanto mas bajo es este índice.

-- Por ultimo, con respecto al índice de confianza, comprobamos que a mayor índice de confianza, mayor numero de suscripciones se produce.

