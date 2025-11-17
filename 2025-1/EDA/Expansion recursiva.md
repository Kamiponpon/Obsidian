cuando las cosas se van al carajo con el metodo maestro... ESTE ES EL PLAN B

resolvemos una ecuacion recursiva escribiendola muchas veces **hasta encontrar el patron**

desarmando la muñeca rusa...

## Ejemplo:

$T(n)=T(n-1)+3$ con $T(1) = 2$ 

primero debemos desarmar hacia atras, esto nos dara mas o menos una buena vista de como se comporta esta ecuacion:
un paso atras:
	$T(n-1)=T(n-2)+3$
segundo paso atras:
	$T(n-2)=T(n-3)+3$
tercero:
	$T(n-3)=T(n-4)+3$
con esto solo nos falta reemplazar uno dentro del otro, ¡como muñecas rusas!

$T(n)=[[[T(n-3)+3]]+3]+3]$

ahora la parte complicada es entender **cual es el patron** si nos fijamos el 3 se va sumando una y otra vez, por cada iteracion nueva se suma 3 denuevo... osea que primera instancia es 3, segunda es 6 y tercera es 9 ¡se multiplica! por el numero que resta n...
por  lo tanto:

	$T(n)=T(n-k)+3*k$

ahi tenemos una expresion mas general, ahora **¿que pasa con el caso base?**
nos lo dan en el enunciado si $T(1)=2$
entonces si $n$ $es un numero muyyy grande va a llegar un punto que le restemos un numero $k$ y nos dara el caso base! osea, en nuestro caso, buscamos el momento que:
	$n-k=1$
1 -> porque es el indice de nuestro caso base $T(1)=2$
k -> numero de iteraciones que se debe hacer
n -> numero que queremos saber el valor

despejando k:
	$k=n-1$

teniendo k podemos reemplazarlo en la generalizacion anterior

	$T(n)=T(n-[n-1])+3*[n-1]$

si desarrollamos eso nos da:

	$T(n)=T(1)+3*n-3$

como nos decian en el enunciado $T(1)=2$ lo reemplazamos en la ecuacion

	$T(n)=2-3+3n$

finalmente *LO ENCONTRAMOS*

	$T(n)=3n-1$

## ¿ahora que?

ahora es momento de *evaluar la complejidad asintótica*

la complejidad asintotica se determinado simplemente viendo la ecuacion
hay que encontrar **que termino con "n" crece mas rapido**

nuestra ecuacion:
	$T(n)=3n-1$

aqui es facil, solo hay 1 termino con n y ese es el que domina, osea:
	$T(n)=\Theta(n)$

## LA TABLA

$log(n)<<n^{1/2}<<n<<n*log(n)<<n²<<2^n<<n!$

este es la ley de la selva, el que gane va dentro de $\Theta()$

