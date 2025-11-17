	vease tambien [[Listas]]

el ejercisio es simple, una lista simplemente enlazada de la forma

4->6->2->NULL

la idea es invertila y que quede

2->6->4->NULL

mi programa:
``` invertir lista
#include <stdio.h>

#include <stdlib.h>

  
  

//se busca hacer una funcion que inverta el orden de valores en una lista simplemente enlazada

//la lista original es 4->6->2->NULL y queremos invetirla a 2->6->4->NULL

  

typedef struct nodo{

int dato;

struct nodo *next;

} nodo;

  

void listaoriginal(){

nodo *n4 = malloc(sizeof(nodo));

nodo *n6 = malloc(sizeof(nodo));

nodo *n2 = malloc(sizeof(nodo));

  

n4->dato=4;

n6->dato=6;

n2->dato=2;

  

n4->next=n6;

n6->next=n2;

n2->next=NULL;

  

printf("la lista se inicializo!");

}

  

void invertirlista(nodo **head){

  

printf("inicializando lista!");

printf("revisando dato: %d", (*head)->dato);

  

nodo *ant = malloc(sizeof(nodo));

nodo **sig = malloc(sizeof(nodo));

+

*sig = (*head)->next;

  

if(ant == NULL){

(*head)->next = NULL;

}else{

(*head)->next = ant;

}

  

ant = (*head);

  

invertirlista(sig);

}

  

int main(){

//ṕrimero definiremos los elementos de la lista

nodo *n4 = malloc(sizeof(nodo));

nodo *n6 = malloc(sizeof(nodo));

nodo *n2 = malloc(sizeof(nodo));

nodo **cabeza = malloc(sizeof(nodo));

  

n4->dato=4;

n6->dato=6;

n2->dato=2;

  

n4->next=n6;

n6->next=n2;

n2->next=NULL;

  

*cabeza = n4;

  

printf("la lista se inicializo!");

  

invertirlista(cabeza);

  

free(n2);

free(n4);

free(n6);

free(cabeza);

free(ant);

free(sig);

  
  

}
```

este programa tiene varias falencias:
1) No invierto la lista correctamente:
la recursividad no tiene retorno y la logica no avanza bien

2) mala gestion de memoria:
ant y sig no es enecsario que les aplique malloc, sig deberia ser un simple puntero
deberia usar nodo *sig = (*head)->next; sin usar el malloc

3) liberando variables invalidas:
ant y sig solo existen dentro de la funcion el free() solo funciona donde existen las cosas

4) no imprimo la lista:
nunca chucha sabre si la lista la hice bien o no

ahora, con las correcion llegue a entender bastante, aqui el nuevo codigo corregido:

```corregido
#include <stdio.h>

#include <stdlib.h>

  
  

//se busca hacer una funcion que inverta el orden de valores en una lista simplemente enlazada

//la lista original es 4->6->2->NULL y queremos invetirla a 2->6->4->NULL

  

typedef struct nodo{

int dato;

struct nodo *next;

} nodo;

  

nodo *nuevo_nodo(int valor){

nodo *nuevo = malloc(sizeof(nodo));

nuevo->dato = valor;

nuevo->next = NULL;

return nuevo;

  

}

  

void leer_lista(nodo *cara){

while(cara){

printf("el dato es %d\n", cara->dato);

printf("estoy en.. %p\n", (void*)&cara->dato);

printf("y apunta a %p\n", cara->next);

printf("- - - - - - - \n");

cara = cara->next;

}

printf("llegamos al final!\n");

}

  

void invertirlista(nodo **head){

nodo *anterior = NULL;

nodo *actual = *head;

nodo *siguiente = NULL;

  

while(actual != NULL){

siguiente = actual->next;

actual->next = anterior;

anterior = actual;

actual = siguiente;

}

  

*head=anterior; //esta parte es importante, ya que dimos vuelta la lista entera debemos actualizar quien es la cara!

//si no estuviese esta linea al llamar a cara nos daria el valor 4 que apunta al vacio y ahi muere la lista!

//por lo tanto la cara nueva va a ser aquel que esta conectado a toda la funcion, osea 2!

//cuando estemos en NULL recordaremos el nodo anterior y ese gil sera la cara nueva ya que estando en NULL significa que vimos todo

}

 

void liberar_lista(nodo *cara){

nodo *tmp;

while(cara != NULL){

tmp = cara;

cara = cara->next;

free(tmp);

}

printf("memoria liberada correctamente...\n");

}

  

int main(){

//ṕrimero definiremos los elementos de la lista

nodo *cara = nuevo_nodo(4);

cara->next = nuevo_nodo(6);

cara->next->next = nuevo_nodo(2);

//con esto definimos 4->6->2->null

  
  

leer_lista(cara);

printf("esa fue la lista original...\n..................\n");

//con esta funcion podemos leer bien que onda

  

//me cuesta entender lo del puntero doble

invertirlista(&cara);

leer_lista(cara);

  
  

liberar_lista(cara);

printf("fin del progama...\n");

}
```


## Cosas que aprendi

- entendi bien el concepto de doble puntero, lo anote en [[Listas]]
- es importante muchas de las funciones que hice ahi en especial la de imprimir y de liberar listas, podria reutilizarse