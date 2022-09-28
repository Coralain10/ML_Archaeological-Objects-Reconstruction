# ML Archaeological Objects Reconstruction
Trabajo para el curso de Machine Learning realizado a partir de la investigación "3D Reconstruction of Incomplete Archaeological Objects Using a Generative Adversarial Network" de los autores Renato Hermoza e Ivan Sipiran de la Pontificia Universidad Católica del Perú.

# Integrantes
* Anto Chávez, Carolain
* Atarama Leon, Diego Sebastian
* Yanayaco Temoche, David Martin

# Marco teórico

## Modelos 3D

### Formatos
* **Geomview OFF**: Este es el formato usado para los modelos 3D en el dataset original.
* **Binvox**: Los modelos en 3D con formato OFF son procesados como una grilla booleana de tamaño $32^3$ usando el programa Binvox, el cual es recibido por el modelo para entrenar y validar. Este es formato en el cual se encuentran los objetos en el dataset a analizar.
* **STL (stereolithography CAD)**: Dado que los objetos binvox resultantes del modelo serán impresos, estos serán convertidos a formato STL, ya que es el formato más usado para impresión 3D. 

### Conversiones entre modelos 3D
La conversión necesaria sería de Binvox a STL.

## Formato STL
El formato STL es un formato ideal para objetos 3D que deben ser impresos. Es una versión simplificada de un archivo CAD, contando con menos información, reducida al mínimo posible, sin perder lo esencial. De este tipo de archivo desaparecen los colores, la textura y la estructura interna. \
Existen dos tipos de formato STL, el tipo ascii y el tipo binario. Para este proyecto, nos interesa el primero, debido a que la función que desarrollamos nos devuelve el archivo STL en ascii. 
### ¿Cómo funcionan los archivos .stl ascii?
* Se empieza por la linea "**solid** name", donde "name" es un dato de tipo string. Es opcional, sin embargo, si no se coloca, aún debe haber un espacio después de "solid"
* Luego, siguen todos los triángulos, representados de la siguiente forma: \
**facet normal** $n_i n_j n_k$ \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**outer loop** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**vertex** $v1_x v1_y v1_z$ \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**vertex** $v2_x v2_y v2_z$ \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**vertex** $v3_x v3_y v3_z$ \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**endloop** \
**endfacet**
* Finalmente, se termina con la linea "**endsolid** name"
