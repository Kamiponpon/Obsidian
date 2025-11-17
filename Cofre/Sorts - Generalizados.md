Tenemos muchos algoritmos que ordenan cada uno con su wea, para lo que es el certamen 2 **supuestamente no necesitamos aprendera a codificarlo de 0** pero si
**entenderlos**

# INSERTION SORT - "el caballero paciente"

1) recorremos el arreglo de izquierda a derecha
2) mira el valor actual y lo inserta donde debería estar

- funciona bien si esta *casi* ordenado! :D

Ej:
		$A=[5,2,4,6,1,3]$
1) comparamos el 2 con el 5, el 2 se va al principio -> [2,5,4,6,1,3]
2) miro el 4, va antes del 5 -> [2,4,5,6,1,3]
3) miro el 6, es mas grande que 5 entonces todo ok...
4) miro el 1, este va antes que el 2 -> [1,2,4,5,6,3]
5) miro el 3, este va antes del 4 -> [1,2,3,4,5,6]

**Estabilidad**
si hay dos elemetos iguales **¿el orden es el mismo?**
el insertion es estable, dado que cuando compara solo mueve a la derecha si es que el actual es mas grande

# INSERTION BUBBLE

1) recorremos el arreglo de izquierda a derehca, uno en uno
2) en el lugar donde estoy comparo con el siguiente, si el siguiente es menor al actual los invierto
3) voy haciendo esto por cada espacio, luego repito hasta que este ordenado

INFERIOR EN TODO ASPECTO A INSERTION

ej:
		$A=[5,1,4,2,8]$
Primera vuelta:
- miro posicion 0: 5 y comparo con 1, 5>1? -> [1,5,4,2,8]
- miro posicion 1: 5 y comparo con 4, 5>4? -> [1,4,5,2,8]
- miro posicion 2: 5  y comparo con 2, 5>2? -> [1,4,2,5,8]
- miro posicion 3: 5 y comparo con 8, 5>8? -> NO! no cambia!
Segunda vuelta:
- miro posicion 0: 1 y comparo con 4, 1>4? -> NO! no cambia!
- miro posicion 1: 4 y comparo con 2 , 4>2? -> [1,2,4,5,8]
- de aqui adelante hace lo mismo, hasta que chequea que esta todo bien

## Optimizado vs NO Oprimizado

- bubble op: cuenta con una flag, si dentro de la vuelta **no hace swaps** entonces termina al terminar la vuelta
- bubble NO op: cuenta hacer n-1 vueltas

si no estuviese optimisado el mejor caso es el peor caso, porque siempre hace lo mismo

# MERGE SORT

1)divide un array en 2, y luego divide las partes divididas **hasta** que son de 1 solo elemento
2)compara los dos fragmentos de array diididos, compara el sus valores y el que sea menor se mueve a un nuevo, tercer array, que se va llenando de menor a mayor

ej:
		$A=[5, 1, 4, 2]$
1) primero dividimos en 2 partes iguales -> A se divide en -> $[5,1]$ y $[4, 2]$
2) esas mismas partes divididas se dividen denuevo -> $[5,1]$ se divide en  $[5]$ , $[1]$  y $[4, 2]$ se divide en $[4]$ y $[2]$
3) cuando se llega a la division mas baja empezamos a armar devuelta, se compaa los hijos de la ultima division, el que es menor se va a un array ordenado: comparamos $[4]$ con $[2]$, el menor de este se va al array, osea $[2]$, despues el siguiente se suma quedando ordenado $[2,4]$, hacemos lo mismo para $[5]$ y $[1]$ -> $[1, 5]$
4) subimos un escalon mas: comparamos $[2, 4]$ y $[1, 5]$, comparamos los primeros indices, gana el 1 entonces nuestro nuevo array va $[1, x, x, x]$ 
5) repetimos $[2, 4]$ y $[1, 5]$ pero como "se fue el 1" solo esta el 5 en el array de la derecha ¿quien es mas chico? ¿2 o 5? -> $[1, 2, x, x]$
6) repetimos, mismo de antes "se fue 1 y 2" solo quedan 4 y 5 en los array, y hacemos la misma comparacion ¿quien es mas chico? -> $[1, 2, 4, x]$ y como solo queda 1 valor -> $[1, 2, 4, 5]$

NO ES IN-PLACE // ESTABLE

# QUICK SORT

1) elije un pivote, se elije de una forma en especifica
2) eleijido este pivote se separa el arreglo en aquellos que son menores y los que mayores
3) de esa separacion hacemos lo mismo por cada lado
4) cuando ya hayamos separado a su unidad, volvemos a fusionar

*funciona como el merge, pero en vez de siempre dividir en la mitad, dividemos segun el pivote que elegimos, esto no se muy bien como garantiza la victoria*

ej:
		eh....

IN-PLACE - NO ESTABLE

# HEAP SORT

1) Se construye un *max heap* a partir del arreglo
2) el maximo está en posicion 0 del arreglo
3) intercambiamos el primer elemento con el ultimo
4) reduzco el tamaño del heap y reorganizo [heapify] para mantener la propiedad
5) repetir hasta tener el heap tamaño 1


??? que coño