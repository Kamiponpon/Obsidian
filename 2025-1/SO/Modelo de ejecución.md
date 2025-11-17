en en contexto de sistemas operativos...


PU = **unidad de procesamiento** y en este contexto se hace referencia a la cpu, el modulo de computo

**PU** ejecuta instrucciones según el **Program Counter** =PC -> esto es e lo que se conoce como **hilo de hardware**

*¿que es un hilo? un contexto de ejecución*

---------------------
# Procesadores Logicos

LP = **Logic Procesor** es como llama al PU el sistema operativo.y por lo tanto para el SO los procesos de ejecutan en el **LP** 
como el LP representa un PU entones solo se puede ejecutar un *contexto de ejecucíon o hilo* en un instante
entonces el hilo que esta ejecutando el sistema operativo es el *hilo k* o **Hilo Kernel**

todo proceso = secuencia de instrucciones = hilo 
el programa que escribo con sus variables locales es el **Hilo Usuario**

------
# Procesamiento: Multi processing

si el sistema cuenta con MP (multi processing) entonces tendrá multiples LP

puede tambien tener su version *Leveleada* SMP (Symmetric Multi Procestsing) el sistema operativo va a **intentar** equilibrar la carga entre los LP's que tiene para lograr **Paralelismo**

**-> si no hay suficientes recursos habrá concurrencia <-**

# Procesamiento: Multi-Threading

esta tecnologia hace un clon de una PU (a grandes rasgos) de esta forma tenemos 2 PU y con ello tenemos 2 posibles contextos de hardware en un solo *reloj*

antes por un hilo de HW habia un hilo de Kernel, osea un solo LP, con MT duplican  los recursos del PU para tener 2 LP, es como una oferta: 2LP x 1PU

permite ejecutar el doble de procesos, pero a un costo de eficencia singular menor, es como dividir un slime?

