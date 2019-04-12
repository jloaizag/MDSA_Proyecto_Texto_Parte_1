# MDSA_Proyecto_Texto
# 1. DESCRIPCIÓN DEL PROYECTO
Esta es la parte 1 del proyecto denominado "Text Mining".
Básicamente se tiene un conjunto muy grande de documentos tipo texto (txt, html o pdf) y los  metadatos de dichos documentos. El objetivo es realizar una sistema/aplicación para la ingesta,   almacenamiento , indexación , búsqueda, recuperación , navegación y visualización de documentos. Estos documentos pertenecen al mismo dominio de interés, por ejemplo: ingeniería, medicina, o astronomía, entre muchos otros campos de conocimiento o aplicación.
El objetivo de esta primera parte es la preparación de la data y la indexación de la misma. En esta parte se leen los documentos, se limpia la data, se tokenizan y se llega a tener una BoW (Bag of Words) con las palabras unicas y su frecuencia.

# II. ARQUITECTURA DEL CÓDIGO
El código para realizar la tarea propuesta está escrito para Jupyter, específicamente en formato MarkDown.

# III. GUIA DE USO, DEPENDENCIAS, CONSIDERACIONES.
Para ejecutar el código en Jupyter basta con posicionar el cursor en la caja donde se encuentra el código a ejecutar y presionar CONTROL+ENTER.

En cuanto a las dependencias, estas son librerías para la ejecución de las tareas a ejecutar y generalmente se importan todas al inicio del programa. A continuación, una copia de las librerías usadas en esta parte del proyecto:

import re

import nltk

from nltk import FreqDist

from nltk.corpus import stopwords

from nltk.stem.porter import PorterStemmer

from nltk.stem.lancaster import LancasterStemmer

from nltk.stem import WordNetLemmatizer

wordnet_lemmatizer = WordNetLemmatizer()

import glob

