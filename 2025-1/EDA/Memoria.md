
se recomienda ver: [[Punteros]]

C es un lenguaje de memorias
y manejar memorias es ir en moto sin casco, hace una wea mal y te sacas la chucha

## MALLOC

digamos que haces un programa que lee datos, no sabes cuantos, pero sabes que son hartos ¿que haces? pues probablemente uno usaria algo como 
`int muchosnumeros[1000];
y listo, ¿no?
pero ¿que pasa si llegan 1001 datos? o si llegan 2? en el primer caso perderemos datos y en el segundo terminaremos *asignando un valor de memoria fijo y no ocuparemos ni la mitad*

¿la solucion a eso? malloc

`int *muchosnumeros = (int *)malloc(CANTIDAD * sizeof(int));
hay dos parametros a notar, primero, la CANTIDAD es la cantidad de valores que va a hacer espacio y en este caso es todas las instancias que dice int uno debe reemplazar por la variable del dia ahi, sea char o que se yo, tambien aplica a estructuras

de forma que caben CANTIDAD de VARIABLE en ese espacio de memoria dado por malloc 

se tiene que darle un puntero a malloc, porque malloc devuele un puntero al primer bloquesito de memoria dado

esto sirve para hacer programas a la medida, sin mas ni menos, ¡justo! ¡preciso!

# ¡considerar!

en funciones (mundos paralelos) las cosas y variables que uno define ahi se quedan ahi **perooo**
si usamos un malloc... esa variable *se mantiene dentro y fuera de mundos paralelos*
¿por que? no lo se pero funciona


## REALLOC

digamos que te pegaste un maloc pero la CANTIDAD que pusiste es menos de la que debiste poner y debes ajustarlo

*ahi* viene realloc, simplemente cambia la cantidad de memoria que le habias dicho, no cambia mas

`nuevo_puntero = realloc(puntero_orginal, nuevo tamaño en bytes)

nuevo tamaño en bytes puede ser (CANTDAD_NUEVA * TIPO DE VARIABLE) asi como el ejemplo de malloc antes
