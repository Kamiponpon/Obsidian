el metodo maestro es *una herramienta para resolver ecuaciones recursivas* de este tipo

$T(n)=A*T(n/B)+f(n)$ 

cuando nos enfrentamos a estos ejercios debemos simplemente identificar $A$, $B$, y $f(n)$

luego usamos $A$ y $B$ en la formula del $punto de comparacion$ o $umbral$

$n^{{log}_{B}(A)}$ 

osea enrealidad buscamos calcular  ${log}_B(A)$

ahora debemos teniendo esta valor RARO lo comparamos con $f(n)$

$f(n)¿>=<?n^{{log}_B(A)}$ 

## Caso 1: si $f(n)$ < $umbral$: 
"el trabajo fuera de la recursión es poco importante"


entonces el resultado es:

$T(n)=\Theta(n^{{log}_{B}(A)})$ 

## Caso 2: si $f(n)=umbral$
"la recursion y el trabajo exterior estan equilibrados"

$T(n)=\Theta({n^{log_B(A)}}*{log^{k+1}}*n)$ 

## Caso 3: si $f(n)>umbral$
"el trabajo fuera de la recursión domina todo"
**pero** no es tan simple... necesitamos saber que $f(n)$ es **mayor** por un margen solido

entonces al comparar valores debemos sumarle un $\epsilon$ al exponente de $umbral$:

$f(n)>n^{log_B(A)+\epsilon}$ 

este $\epsilon$ que sale de la NADA es un valor teorico que denota **que tanta diferencia hay entre los dos**

## condicion de regularidad

$A* f(\frac{n}{B}) <= c * f(n)$ y c < 1

*la pega es encontrar un C para que se cumpla lo anterior, si no hay C y no se cumple lo anterior entonces la wea mato*

si eso anterior se cumple entonces:

$T(n)=\Theta(f(n))$ 

**si no se cumple** entonces se nos complica la cosa...

[[Expansion recursiva]]
