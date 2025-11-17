los punteros son un tipo de variable, mas lo entiendo como una sub rama de variables
el lenguaje de C se trata manejo de memoria! por eso viene los punteros, gracias a ellos podemos copiar modificar y compartir datos sin modificarlos directamente y wear con estructuras, listas y arboles

## El atao con funciones=
cuando uno define una funcion, se podria decir que abrimos un portal en el tiempo, una simulacion interna donde en este universo propio pasan cosas pero una vez salido de ese universo los cambios no se ven reflejados en nuestra realidad (nuestra realidad siendo el main), en cambio con punteros le damos la direccion al valor de nuestra realidad y ahi si que podemos joder con ese valor!
es un poco complejo de entender, pero digamos que tengo una maquina que te da galletas al apretar el boton, pero tu a la galleta quieres que tenga el doble de crema entonces tomas tu galleta y le pones el doble de crema, una vez vuelto a la maquina de galletas te daras cuenta que las galletas siguen siendo las mismas!!!

el puntero es la parte de la maquina que realmente genera la galleta, lo estas apuntando, ahi esta el origen, si vas a la direccion y cambias los engrajes internos por otros ahi si que si tendremos galletas de doble crema para siempre que apretes el boton

## la ecuacion descubierta

pareciera que * y & son como inversos matematicamente, mira esto
```
int * puntero;
int numero_a_copiar = 5;

puntero = &numero_a_copiar;
printf("%d", *puntero);
```
primero inicializamos declarando que esta es una variable puntero(*) a numero(int) llamada puntero

despues damos un numero valor 5

cuando hacemos puntero =&numero_a_copiar usamos esta tontera (&) que entregara la direccion donde se guarda el valor que tiene esa variable osea, **DONDE esta lo que guarda numero_a_copiar** y eso es lo que realmente guarda la variable puntero

el operador (*) en este contexto es sacar el valor de donde sea que este la direccion que este en la variable
si usara *numero_a_copiar me daria el valor numerico de lo que sea que este en la memoria espacio 5 (no se si eso existe)

con tal que queda esta funcion matematica
(*) x (&) = 1
a que me refiero? a esto:
puntero = &numero_a_guardar; /multiplico a ambos lados por *
*puntero = numero_a_guardar; ves?

## cosas a considerar
al crear un array de este tipo 
`char texto[] = "hola"
la variable texto, que esto parece ser que solo pasa con los arrays y quizas los struct, **guardan directamente la direccion de memoria del primer caracter**, en este caso si printero texto me daria la direccion del primer caracter, a lo que voy es que no necesitas un & puntero = texto, ya es suficiente para apuntar a la direccion de "h"





espero que esto haya servido 











