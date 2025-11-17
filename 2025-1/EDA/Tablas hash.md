las tablas hash son una estructura de datos que guarda y busca datos rapidamente
con tiempos constantes, esto lo hace mas rapidos que arrays o listas 

por lo que entiendo, la tablas hash funcionan asi

tenemos M numeros, digamos que en este caso m=7, osea su capacidad de numeros que podemos guardar

{0, 1, 2, 3, 4, 5, 6}

casa uno de estos indices le correponde un valor numerico que **no podemos asignar**
será asignado por una funcion h(k)

h(k) = **k** mod **m**

aqui **k** es el valor numerico a guardar, digamos que **k** es 25 en esta ocacion

**m** el tamaño de la tabla,el cual le dimos un valor anteriormente, entonces

h(25) = 25 mod 7

mod es "modulo de division", el cual correspode al *residuo* que queda despues de dividir
un ejemplo:

5 mod 3 = **2** -> 5 = 3 * 1 + **2**

lo que quiero decir *dividimos el valor a guardar por el tamaño de la tabla y el residuo es la posicion donde se guarda*

## colisiones 

¿que pasa cuando 2 valores distintos tienen el mismo residuo?

si tengo que guardar un valor 10 y un valor 17 en una tabla de tamaño 7 sucede *ambos tienen el mismo resto... 3!* , el que llega primero se queda el verdadero indice 3, el que llega despues recorrera la tabla por el siguiente puesto libre del 3 en adelante, como que *rebota*

esto que acabo de explicar se llama *sorteo lineal* hay otros tipos de [[solucion de coliciones]]
## ¿para que mierda sirve?

las tablas hash se usan como analogo de *diccionario rapido* se 

## buscando y eliminando

para buscar usamos la misma funcion que usamos para guardar

h(k) = k mod m

si no hay nada, pues no existe

si lo encuentras, super!

si hay algo y no es lo que buscas... tendras que buscar segun que metodo de colicion usas

que pasa si quiero **eliminar** algo?

usamos la misma tecnica de busqueda y el valor será remplazado por una "tumba"

un simbolo arbitrario donde marca que se murio ese valorsito

## Factor de carga

A = (n / m)

- A es el factor de carga, un porcentaje de que tan llena ta la wea
- n es el numero de elementos guardados
- m es el tamaño de la tabla

entre mas chico sea A, mejor rendimiento sera las operaciones en la tabla, hasta un **70%**

**90%** es de la mierda y **mas alla del 100% solo pueden ser los "encadenamientos"** en cuaquier otro caso al 100% *la wea colapsa*

## REHASHING

una vez A > 70% la tabla empieza a colapsar, hay que hacer OTRA tabla, una con un "m" MAS grande, *el siguiente primo mas grande*

y ahi tomamos todos los valores y los metemos devuelta a la nueva tabla!