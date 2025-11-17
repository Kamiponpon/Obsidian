las listas son estructuras de la forma como vimos es [[Estructuras]]
asi:
```ejemplo_de_listas
struct nodo{
	int dato_dentro;
	struct nodo *puntero_siguiente_nodo;
}
```

esta es la estructura de un nodo simplemente enlazado, es la base para las siguientes tipos de organización que veremos

es importante notar que cuando generamos otro nodo lo definiremos como un puntero, ya que cada nodo esta compuesto de diferentes componentes debemos saber a cual *apuntamos* ¿si?
```ejemplo_creacion_de_nodo
nodo *crear_nodo(int valor){
	nodo *nuevo = malloc(sizeof(nodo));
	nodo->dato_dentro = valor;
	nodo->puntero_siguiente_nodo = NULL;
	return nuevo
}
int main(){
	nodo *head = crear_nodo(10);
	head->next = crear_nodo(11);
	head->next->next = crear_nodo(12);
	...
	
}
```
es buena idea llamar a el nodo principal un nombre distintos, pareciera que creamos un nodo y le vamos conectando valores a el en cadena, de tal forma que el "head"  es el unico nodo con nombre real, los otros nodos son los que conectan a el

## modificando valores y doble puntero

si fuesemos a modificar un valor de un nodo, debemos wear con doble punteros ¿porque? porque estamos modificando un puntero! y para modifcar un puntero necesitamos a otro puntero ¿porque?

¿recuerdas que nosotros dabamos direcciones para modificar valores del programa princial? pues es lo mismo aqui, queremos modificar el valor que apunta el puntero original, entonces debemos darle la direccion del puntero

si no usasemos el doble puntero, estariamos dando una *copia* del puntero original y nada cambiase! para eso debemos realmtente donde vive el puntero

¡ya se cual es la mejor forma de explicar esto!

valores                          ptr2  ->     ptr    ->   valor
direccion(                    0x03        0x02        0x01
valor almacenado       0x02        0x01            1

ptr guarda la direccion de valor, y conseguimos el verdadero valor accediendo a lo que apunta el puntero con un * y podemos decir lo mismo de pt2 de tal forma que encontramos estas ecuaciones segun las flechas "->" que sigifica que apunta quien

1) ptr = &valor 
2) 2ptr = &ptr
si juntamos el 1 al 2:
 - 2ptr = &(&valor)
 recordar que * con & se cancela!, entonces multiplicamos por ** !
 - 2ptr = &(&valor) /*
 - * 2ptr = &valor /*  (al final * 2ptr = ptr)
 - ** 2ptr= valor

creo que ahora si queda claro