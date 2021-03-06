# MDSA_Proyecto_Texto
# I. DESCRIPCIÓN DEL PROYECTO
Esta es la parte 1 del proyecto denominado "Text Mining".
Básicamente se tiene un conjunto muy grande de documentos tipo texto (txt, html o pdf) y los  metadatos de dichos documentos. El objetivo es realizar una sistema/aplicación para la ingesta,   almacenamiento , indexación , búsqueda, recuperación , navegación y visualización de documentos. Estos documentos pertenecen al mismo dominio de interés, por ejemplo: ingeniería, medicina, o astronomía, entre muchos otros campos de conocimiento o aplicación.
El objetivo de esta primera parte es la preparación de la data y la indexación de la misma. En esta parte se leen los documentos, se limpia la data, se tokenizan y se llega a tener una BoW (Bag of Words) con las palabras unicas y su frecuencia.

# II. ARQUITECTURA DEL CÓDIGO
El código para realizar la tarea propuesta está escrito para Jupyter, específicamente en formato MarkDown.
Para realizar este proyecto, se utilizaron las estructuras de datos que se detallan a continuación:


 1. LISTA doc_id : Una Lista python, la cual contiene un Diccionario pyton. 
 El Diccionario tiene: 
 
 Clave: doc_id : Un id que se le asigna a cada documento
 
 Valor: doc_length : nro de caracteres del documento original
 
 Veamos un Ejemplo de de esta lista

doc_id=[{'doc_id': 1, 'doc_length': 1424},\
        {'doc_id': 2, 'doc_length': 1740},\
        {'doc_id': 3, 'doc_length': 1522},\
        {'doc_id': 4, 'doc_length': 988},\
        {'doc_id': 5, 'doc_length': 4022}]
       
       
 2. LISTA freqDict_list : Una Lista python, la cual contiene un Diccionario pyton.
 El Diccionario tiene: 
 
 Clave: doc_id : id del doc
 
 Valor: freq_dict : este es otro Diccionario, el Cual contiene:
 
        Clave: una palabra
        
        Valor: Frecuencia de la palabra (número de veces que esta aparece en el documento)
        
 La lista tiene tantos registros como documentos leídos
 
 El diccionario de cada documento tiene tantas claves(palabras) como palabras diferentes tenga el documento (ya limpio)
 
 Veamos un ejemplo de un registro de la lista; es decir, la información de un documento

freqDict_list=[{'doc_id': 1, 'freq_dict': {'entropi': 112, 'earli': 3, 'function': 13}}]



 3. LISTA TF_scores : Una Lista python, la cual contiene un Diccionario pyton.
 
 El Diccionario tiene: 
 
 Clave: doc_id : id del doc
 
 Valor: TF_score : este es otro Diccionario, el Cual contiene:
 
        Clave: una palabra
        
        Valor: Frecuencia relativa de la palabra
        
 La lista tiene tantos registros como documentos se hayan leído
 
 El diccionario de cada documento tiene tantas claves(palabras) como palabras diferentes tenga el documento (ya limpio)

Veamos un ejemplo de un registro de la lista; es decir, la información de un documento

TF_scores=[{'doc_id': 1, 'TF_score': {'entropi': 0.07865168539325842, 'earli': 0.002106741573033708}}]




 4. LISTA IDF_scores : Una Lista python, la cual contiene un Diccionario pyton.
 
 El Diccionario tiene: 
 
 Clave: doc_id : id del doc
 
 Valor: IDF_score : este es otro Diccionario, el Cual contiene:
 
        Clave: una palabra
        
        Valor: índice inverso de la palabra en el documento
        
 La lista tiene tantos registros como documentos se hayan leído.
 
 El diccionario de cada documento tiene tantas claves(palabras) como palabras diferentes tenga el documento (ya limpio)
 
 Veamos un ejemplo de un registro de la lista; es decir, la información de un documento

IDF_scores=[{'doc_id': 1, 'IDF_score': {'entropi': 1.9972034434428638, 'earli': 1.5452183196998066}}]



 5. LISTA TFIDF_scores : Una Lista python, la cual contiene un Diccionario pyton.
 
 El Diccionario tiene: 
 
 Clave: doc_id : id del doc
 
 Valor: TFIDF_score : este es otro Diccionario, el Cual contiene:
 
        Clave: una palabra
        
        Valor: Este valor se calcula multiplicando el TF_Score * IDF_Score de cada palabra
        
 La lista tiene tantos registros como documentos se hayan leído
 
 El diccionario de cada documento tiene tantas claves(palabras) como palabras diferentes tenga el documento (ya limpio)
 
 Veamos un ejemplo de un registro de la lista; es decir, la información de un documento
 
TFIDF_scores=[{'doc_id': 1, 'TFIDF_score': {'entropi': 0.15708341690000052, 'earli': 0.0032553756735248735}}]



# III. GUIA DE USO, DEPENDENCIAS, CONSIDERACIONES.

Este proyecto está desarrollado usando la herramienta jupyter. Para ejecutar el código lo primero que se debe hacer es cargar el código fuente del notebook del proyecto, el cual se encuentra en este repositorio de GitHub con el nombre ProyectoIntegrador1.ipynb o en la dirección suministrada en el correo. 

Después de cargado el notebook, la ejecución se puede hacer de varias formas. Las 2 más sencillas son:
- Paso a paso: para esto se posiciona el cursor en la primera caja de código del programa y se presina SHIFT + ENTER para ejecutar el codigo de la caja. Tan pronto este haya terminado, el cursor pasará a la siguiente caja. Una vez allí, de nuevo se presiona SHIFT+ENTER para ejecutar el codigo de la caja, y así sucesivamente hasta llegar al final.

- Ejecutar todo el código: Después de tener cargado el notebook de jupyter, en el menú de la parte superior de la pantalla, se selecciona KERNEL / RESTART & RUN ALL. De esta forma se irán ejecutando todas las cajas de código, hasta llegar al final.

En cuanto a las dependencias, estas son librerías para la ejecución de las tareas a ejecutar y generalmente se importan todas al inicio del programa. A continuación, una copia de las librerías usadas en esta parte del proyecto:

import math

import re                        #regular expressions

import matplotlib.pyplot as plt

import nltk                      #libreria de procesamiento natural del lenguaje 

import glob

from nltk.corpus import stopwords

from nltk.stem.porter import PorterStemmer

from nltk.stem.lancaster import LancasterStemmer # otra lib para stemming

from nltk.stem import WordNetLemmatizer

from nltk.corpus import wordnet

from nltk.stem import PorterStemmer

from nltk.tokenize import sent_tokenize, word_tokenize

from nltk import FreqDist

import time


