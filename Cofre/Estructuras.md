parte importantisima de eda, las estructuras se usan bastante para organizar variables bajo un mismo nombre

se guardan como arrays, un gran edificio con diferentes departamentos para cada componente del array

solo que para estructuras es otro tipo, en las estructuras uno basicamente "crea" su propia variable

``` 
struct persona{
	char nombre[30];
	int edad;
	float altura;
}: 
```

esta es la definicion de una estructura, el siguiente paso es realmente usarla en main()

` struct persona p1;
con eso creo una estructura tipo persona llamada p1

## ¿como accedo a sus valores?
con puntos! de esta forma
``` 
p1.edad = 20
strcpy(p1.nombre, "gabriel")
```
NOTA: strcpy() copia lo que esta a la derecha a la izquierda, en c no es posible llegary poner algo pero existe esa funcion en la libreria
## Combinaciones con punteros y memorias
ver [[Punteros]] y [[Memoria]]

hay una combi muy clave en EDA, es la estructura con punteros  y memoria
```
struct nodo{
	int numero;
	struct nodo *siguiente; // se puede llamar a la esctructura misma cuando la defines!
}; 

int main(){
struct nodo *nodo1 =malloc(sizeof(struct nodo))
struct nodo *nodo2 =malloc(sizeof(struct nodo))

//aqui asignamos valores namas
nodo1->numero = 10;
nodo2->numero = 20;

nodo1->siguiente = nodo2;
nodo2->siguiente = NULL; //la cola de al lista, apunta nada

//aqui abria una parte donde printeo todo para que lo veas paero me dio lata
}
```

voy a intentar explicar un poco el codigo

primero definimos la estructura, la cual tiene dentro un numero y un puntero que apunta una estructura de su mismo tipo, que esto es la base de las listas enlazadas

en el main definimos nodos y les damos el espacio dinamico con malloc para que pase al heap y este ahi
luego definimos los valores de la estructura, los numeros y luego los siguientes nodos de cada nodo
si vemos bien el nodo2 apunta a NULL y ahi se muere

## otros trucos
```typedef
typedef struct{
	int numemero;
	*nodo siguiente;
} nodo
```
con esto en vez de llamar la variable "struct nodo" solo decimos "nodo" un truquiño

