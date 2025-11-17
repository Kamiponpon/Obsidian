
1) supongamos que tenemos una funcion que *busca un numero en una lista ordenada de n elemetos* **usando busqueda binaria**
- escribir la funcion en *pseudocodigo* la funcion busca(x, lista)
- determinar la *complejidad de tiempo en el peor caso*
- justifica por que esas complejidad es $O(log(n))$

*busqueda binaria:*
*miramos a la mitad del arreglo, el numero de al medio lo comparo con el que busco, si el numero de al medio es mas grande de el que busco, voy hacia atras, de los numeros que quedan reviso al medio y asi... ¿me explico?*

respuesta:

```pseudo codigo
busca(x, lista){ //siendo x lo que busco, y lista el array
	mitad = (sizeof(lista))2;
	repetir lo siguiente hasta que lista(mitad) = 0 o sizeof(lista)
	¿lista(mitad) == x?
		si: return 1
		no: ¿lista(mitad) > x?
			si : mitad = mitad - mitad/2
			no : mitad = mitad + mitad/2
}
```
este pseudo codigo tiene problemas:
1) no retorna nada cuando no encuentra el valor
2) el rango puede mejorar, hay formas mejores
3) uso sintaxis de c, pero esto es pseudo codigo
version recorregida:
``` pseudocodigoV2
busca(x,lista){
	inicio = 0 
	fin = (el largo de lista) - 1 (esto es para los indices)
	
	mientras: inicio <= fin
		mitad <- (inicio + fin) / 2
		¿lista(mitad) == x?
			si: retornar TRUE
			no: ¿lista(mitad) > x?
				si: fin <- mitad - - 1
				no: inicio <- mitad + 1
}
```

## Determinando la complejidad

primero debemos llegar cual es le peor caso...
el peor caso es cuando el x no esta o esta en los extremos, osea el numero mas pequeño o el mas grande

hay que pensar en un caso base, digamos...
una lista de tamaño $\omega$ cierto? entonces hagamos el recorrido...
primero dividimos esa lista en dos entonces nos queda 

$\frac{\omega}{2}$ 

lo hacemos denuevo y entonces:

$\frac{\omega}{4}$

y denuevo y denuevo y denuevo...
¿cual es el limite de esto? puesto estamos buscando indices estos son numeros enteros y la divicion no nos va a llevar mas pequeño que 1...
entonces...

$\frac{\omega}{2^k} = 1$ 

siendo $k$ el numero que iteraciones que tomamos para llegar a este caso

si intentamos despejar $k$ nos queda:

$log_{2}(\omega)$ 

ahi tenemos nuesta complejidad!