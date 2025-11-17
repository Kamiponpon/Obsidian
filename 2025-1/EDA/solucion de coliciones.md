otros tipos de solucion de coliciones es

## Encadenamiento

cuando quiero guardar distintos numeros ej:
(20, 25, 30, ...) y m = 5 pasa que todos caen en el indice 0!

entonces el encadenamiento es que los espacios donde caen sean arrays que se expanden, de forma que no rebotan solo se hace espacio en el indice 0 y ahi caben todos! 

lo malo de esto es que consume mucha memoria ya que debemos ir expandiendo cada vez mas el arreglo que esta dentro de cada indice

## Sondeo Cuadratico

es igual al lineal, solo que cuando esta la colicion en vez de checkear un espacio mas al lado, ese salto se eleva al cuadrado
osea
primeor intenta en el espacio siguiente
luego intenta al (2)² espacios siguientes
luego intenta al 3² espacio siguiente

¿por que? no se

## Doble hashing

para clasificar los valores en a tablla en vez de usar una funcion ¡usamos 2!

entonces nuesta super funcion es

h(k,i) = (h_1(k) + i * h_2(k)) mod m

- h_1(k) = k mod m // la tipica
- h_2(k) =R - (k mod R) // nueva funcion secudaria
- R < m // R suele ser primo
en pocas palabras, si el indice directamente esta libre entonces no hay problema

si el indice esta ocupado entonces resolvemos h_2(k) multiplicamos por i, supononiendo que este es el numero de iteraciones de que va haciendo esto
y eso