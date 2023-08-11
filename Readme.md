<p align=center><img src=https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png><p>

# <h1 align=center> **PROYECTO INDIVIDUAL Nº1** </h1>
<h1 align=center> **Antonio Claudio Ortiz** </h1>
# <h1 align=center>**`Machine Learning Operations (MLOps)`**</h1>

<p align="center">
<img src="https://user-images.githubusercontent.com/67664604/217914153-1eb00e25-ac08-4dfa-aaf8-53c09038f082.png"  height=300>
</p>

¡Bienvenidos al primer proyecto individual de la etapa de labs! En esta ocasión, deberán hacer un trabajo situándose en el rol de un ***MLOps Engineer***.  

<hr>  

Para resolver el desafío planteado, en primera instancia se trabajó en distintas etapas:
Se Desanidaron los registros tipo:
	
    {'id': 10194, 'name': 'Toy Story Collection', 'poster_path': '/7G9915LfUQ2lVfwMEEhDsn3kT4B.jpg', 'backdrop_path': '/9FBwqcd9IRruEDUrTdcaafOMKUq.jpg'}

	[{'id': 16, 'name': 'Animation'}, {'id': 35, 'name': 'Comedy'}, {'id': 10751, 'name': 'Family'}]

Para ello se utiliza como herramienta de apoyo colaboratory google

<p align="center">
<img src="https://www.marketing-branding.com/wp-content/uploads/2020/07/google-colaboratory-colab-guia-completa.jpg"  height=300>
</p>

Donde se realizó las distintas transformaciones y pruebas requeridas:

from google.colab import drive
drive.mount('/content/drive')

...
import pandas as pd
import ast
import numpy as np
……

print(df_raw['belongs_to_collection'].head())
0    {'id': 10194, 'name': 'Toy Story Collection', ...
1                                                  NaN
2    {'id': 119050, 'name': 'Grumpy Old Men Collect...
3                                                  NaN
4    {'id': 96871, 'name': 'Father of the Bride Col...
Name: belongs_to_collection, dtype: object
...

print(df_raw['belongs_to_collection'].head())
0              Toy Story Collection
1                               NaN
2         Grumpy Old Men Collection
3                               NaN
4    Father of the Bride Collection
Name: belongs_to_collection, dtype: object
...

Los valores nulos del campo release date deben eliminarse.

df.dropna(subset=['release_date'])

**Para el desarrollo de la consigna:** 

Desarrollo API: Propones disponibilizar los datos de la empresa usando el framework FastAPI. Las consultas que propones son las siguientes…
Se trabajó con entornos virtuales para el desarrollo de cada Api, realizando distintas pruebas desde visual code

#python3 -m venv env
#pip3 install fastapi
#pip3 install "uvicorn[standard]"
#main.py
   from fastapi import FastAPI
app = FastAPI()
def index():
    return "greeting Hello world"
uvicorn main:app --reload 

<p align="center">
<img src="https://drive.google.com/drive/folders/1G2JN1t6CtZlzu2-Cs_Fcs1pvv7L5CiOF?usp=drive_link" height=300>
</p>

**En la etapa de Análisis exploratorio de los datos: (Exploratory Data Analysis-EDA)**

Se tuvo en cuenta el material proporcionado:
Introduction to Exploratory Data Analysis (EDA) | by Vervit Khandelwal | The Startup | Medium   
https://medium.com/swlh/introduction-to-exploratory-data-analysis-eda-d83424e47151

Realizando distintas pruebas a los DatasSets proporcionados 

plt.figure(figsize=(10,5))
sns.regplot(x="revenue",y="budget",data=df)


<p align="center">
<img src="https://drive.google.com/file/d/1LnRitXMZG3HNmhxpIcIapf7zL_lHslD6/view?usp=drive_link" height=300>
</p>

**Sistema de Recomendación**

Implementación de un sistema de recomendación utilizando FastAPI y el algoritmo de similitud coseno con TF-IDF para recomendar películas basadas en el título.
Se Importa las bibliotecas necesarias:  FastAPI, pandas, y las funciones necesarias de scikit-learn (TfidfVectorizer y linear_kernel). Ademas

1.	Creas una instancia de FastAPI: Creas una instancia de la aplicación FastAPI.
2.	Cargas el dataset: Utilizas pandas para cargar el conjunto de datos "movies_dataset.csv" con un límite de 5000 filas.
3.	Creas la matriz de características TF-IDF: Utilizas TfidfVectorizer para crear una matriz TF-IDF basada en los títulos de las películas en el conjunto de datos.
4.	Calculas la similitud coseno: Utilizas linear_kernel para calcular la similitud coseno entre las películas utilizando la matriz TF-IDF.
5.	Definición de la función de recomendación: Creas una función llamada "recomendación" que toma el título de una película como entrada. Encuentra el índice de la película en el DataFrame, calcula los puntajes de similitud coseno con otras películas, los ordena en orden descendente y selecciona los 5 más similares.
6.	Definición de la ruta de API: Creas una ruta de API usando FastAPI ("/recomendación/") que acepta un título de película como parámetro. Dentro de la función de la ruta, llamas a la función "recomendación" y devuelves una lista de películas recomendadas.


****************Enlaces**************** 


1. https://sistema-recomendacion-movies.onrender.com

2. https://github.com/claudiogit2019/ProyDeployer23.git


Imagenes y Bases de Datos Utilizadas para el desarrollo del trabajo:

3. https://drive.google.com/drive/folders/1joaaHDi0czkXkQ0RnysEOZQpKC8f_Q0J?usp=sharing









## **Fuente de datos**

+ [Dataset](https://drive.google.com/drive/folders/1mfUVyP3jS-UMdKHERknkQ4gaCRCO2e1v): Carpeta con los 2 archivos con datos que requieren ser procesados (movies_dataset.csv y credits.csv), tengan en cuenta que hay datos que estan anidados (un diccionario o una lista como valores en la fila).
+ [Diccionario de datos](https://docs.google.com/spreadsheets/d/1QkHH5er-74Bpk122tJxy_0D49pJMIwKLurByOfmxzho/edit#gid=0): Diccionario con algunas descripciones de las columnas disponibles en el dataset.
<br/>

## **Material de apoyo**

En este mismo repositorio podras encontrar algunos [links de ayuda](hhttps://github.com/HX-PRomero/PI_ML_OPS/raw/main/Material%20de%20apoyo.md). Recuerda que no son los unicos recursos que puedes utilizar!



  
<br/>

