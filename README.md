# ML Archaeological Objects Reconstruction
Trabajo para el curso de Machine Learning realizado a partir de la investigación "3D Reconstruction of Incomplete Archaeological Objects Using a Generative Adversarial Network" de los autores Renato Hermoza e Ivan Sipiran de la Pontificia Universidad Católica del Perú.

# Integrantes
* Anto Chávez, Carolain
* Atarama Leon, Diego Sebastian
* Yanayaco, David

# Marco teórico

## Modelos 3D

### Formatos
* **Geomview OFF**: Este es el formato usado para los modelos 3D en el dataset, el cual es recibido por el modelo para entrenar y validar.
* **Binvox**: Los modelos en 3D con formato OFF son procesados como una grilla voxel de tamaño $32^3$ usando el programa Binvox, el cual convierte los modelos al formato con el mismo nombre de programa.
* **STL (stereolithography CAD)**: Dado que los objetos binvox resultantes del modelo serán impresos, estos serán convertidos a formato STL, ya que es el formato más usado para impresión 3D. 

### Conversiones entre modelos 3D
Las conversiones necesarias son:
* $OFF \rightarrow Binvox$
* $Binvox \rightarrow STL$
