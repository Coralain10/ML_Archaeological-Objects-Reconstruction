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
Existen dos tipos de formato STL, el tipo ascii y el tipo binario. Para este proyecto, nos interesa el último, debido a que es más sencillo de trabajar y es menos extenso que el de tipo ascii. 
### ¿Cómo funcionan los archivos .stl binarios?
* Se empieza por la cabezera, que cuenta con 80 caracteres. Normalmente es ignorada, pero nunca debe empezar con la palabra "solid", ya que podría ser confundido por un archivo ascii.
* Luego, sigue un entero de 4 bytes indicando el número de triángulos en el archivo.
* Finalmente, la data sobre cada triángulo de la siguiente manera: \
Cada triángulo es descrito por números flotantes de 32 bytes, 3 por la normal y 3 por las coordinadas X/Y/Z de cada vértice. Después, sigue un número entero de 2 bytes que sirve como el atributo "byte count". Normalmente, este número es cero.
