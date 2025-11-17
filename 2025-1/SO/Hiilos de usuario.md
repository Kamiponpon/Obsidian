esto es similar a lo que vi en EDA, tenemos diferentes espacios de memoria
- datos globales
- stack
- text
- estado de ejecuccion
y todos estos tienen su *espacio direccion*


La secuencia de instrucciones del proceso a un hilo que se le dice *hilo principal*
el hilo principal puede que tenga mas hilos dentro del hilo principal, el mismo hilo principal

- cada hilo tiene su stack independiente, con sus propias variables locales

# Modelo: Fork-Join

es como si hacemos un trabajo en grupo, dividimos las tareas y cada uno las soluciona por su cuenta y luego con las soluciones los juntamos en un documento

nosotros seriamos los hilos paralelos, el equipo de hilos que resuelve uno cada cosa y luego con sus calculos se juntan en join

a modo de ejemplo:

```Codigo ejemplo:
Leer_datos(){
	...
	for (...){
		texto_procesado.push(pathFile + ": " + line);
	}
	...
}
```
el codigo esta abreviado para simplicidad

notas que la funcion Leer_datos() funciona varias veces por su *for()*? bueno, aqui tenemos un ejemplo del fork, para el main esto es llamar paralelamente el for tanta veces pida y luego juntarlo todo en el main

# Zona critica - Condición de carrera

sucede cuando un codigo usa recursos compartidos al mismo tiempo cuando se corre de forma paralela

entonces digamos que importa el orden segun se lee o se guarda un elemento! esto importa si tenemos varios hilos pendientes del mismo recurso

-----------------------------


## **Solucion: Exclusión Mutua**

si un hilo ocupa el recurso compartido el resto **NO** puede utilizarlo

es como la tasa del baño! usa

``` MUTEX
Mutex m;

void FA(){
	...
	m.lock()
	
	// ZONA CRITICA DONDE ASEGURO LA ENTRADA DE UNO SOLO
	
	m.unlock()
	...
}
```

es como si entro al baño y le pongo pestilo, una vez listo, saco el pestillo y alguien mas puede ocuparlo

-----------------------------
## Solución: Semáforos

En caso donde es posible que el recurso pueda ser utilizado por mas de un hilo, pero siga siendo limitado se usa la funcion *Semaforo S01()*

se usa asi:
```Inicio semaforo
semaphore S01(A) // A es el cupo maximo de giles dentro del recurso

S01.wait() // le resta 1 al valor A, si el resultado es negativa bloquea al hilo que llamo y lo mete a una lista

S01.signal() // suma 1 al valor A, si hay hilos esperando despierta uno
```

piensa en un estacionamiento, A seria el espacio fisico y le vamos restando la gente que esta utilizando el espacio y aquellos que esperan

una vez se sale un auto, entra el que estaba esperando y chan chan
