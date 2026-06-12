# Analisis de complejidad y notación Big O

El análisis de complejidad busca medir cómo crece el costo de un algoritmo cuando aumenta el tamaño de la entrada cualquiera n. Ese costo normalmente se mide en tiempo de ejecución o memoria utilizada. No nos interesa cuánto tarda exactamente en segundos porque eso depende del computador, sino cómo escala el algoritmo cuando el problema se vuelve más grande.

Por ejemplo, si duplicar el tamaño de los datos hace que el trabajo también se duplique, hablamos de crecimiento lineal. Si duplicar los datos cuadruplica el trabajo, hablamos de crecimiento cuadrático.

Debido a esto se creo la notación Big O que nos dice la complejidad dado un algoritmo, para calcular la complejidad se revisa la estructura del codigo y con base en esto se calcula dicha complejidad.


**NOTA:** Cada complejidad tendra ejemplos completos explicados porque esos algoritmos son esa complejidad, estos codigos e informes estaran en la carpeta Algoritmos

---

## Tipos de complejidades

### Constante O(1) 

El algoritmo realiza siempre la misma cantidad de trabajo sin importar el tamaño de la entrada, es decir que da igual si el arreglo tiene 10 o 10 millones de elementos, siempre se realiza una única operación.

Ejemplos:

```
array = [1, 2, 3, ..., 1000000]

print(array[0])
```
Aunque el arreglo sea de miles o millones de elementos el tiempo de ejecucion será el mismo.

---
### Logaritmica O(Log(n))

El algoritmo reduce significativamente el tamaño del problema en cada iteración, el ejemplo más usado es eliminando la mitad de los elementos restantes, por lo que cada iteración trabaja con una versión mucho más pequeña del problema.

Por eso el número de pasos crece muy despacio.

Ejemplo:
```
while n > 1:
    n = n // 2
```
---

### Lineal O(n)

En un recorrido lineal, cada iteración procesa un elemento más, es decir, si hay 10 elementos entonces se haran 10 iteraciones, si hay 100 elementos se haran 100 iteraciones y asi sucesivamente.

Ejemplo:
```
array = [1, 2, 3]

for num in array:
    print(num)
```
---

### O(nlog(n))
El algoritmo divide repetidamente el problema en partes más pequeñas y, además, en cada nivel de división debe procesar todos los elementos, un ejemplo muy conocido es `Merge Sort` ya que cada división genera aproximadamente `log(n)` niveles y en cada nivel se procesan `n` elementos.

---

### Cuadratica O(n²)

El algoritmo compara o procesa cada elemento con todos los demás, por lo que cada recorrido externo provoca otro recorrido completo interno.

Ejemplo:
```
array = [1, 2, 3]

for i in array:
    for j in array:
        print(i, j)
```
aqui se recorre la lista 2 veces de manera aparte, osea se recorrio los 3 elementos 2 veces: 3 x 3 = 9 osea 3².

---
### Cubica O(n³)

El algoritmo realiza tres recorridos anidados, generando un crecimiento cúbico en el número de operaciones.

Ejemplo:
```
array = [1, 2, 3]

for i in array:
    for j in array:
        for k in array:
            print(i, j, k)
```

---
### Exponencial O(2ⁿ)

Cada solución genera múltiples subproblemas nuevos, haciendo que el número de operaciones se duplique repetidamente.

El ejemplo es el problema de fibonacci usando recurencia, el cual se abordara en su propio informe.

---

### Factorial O(n!)
Significa que el algoritmo prueba todas las posibles formas de ordenar o acomodar los elementos.

Por ejemplo si tenemos

```
array = [1, 2, 3]
``` 
las posibles permutaciones seran:
```
[1,2,3]
[1,3,2]
[2,1,3]
[2,3,1]
[3,1,2]
[3,2,1]
```
osea 3! = 3 x 2 x 1 = 6.

esto en una cantidad muy pequeña de elementos no es tan grave, pero crece demasiado rapido, por ejemplo hacer lo mismo de todas las formas de tener elementos pero ahora con 10 elementos, son mas de 3 millones de posibilidades.