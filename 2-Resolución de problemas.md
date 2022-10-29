# Resolución de problemas

* Capacidad que consideramos inteligente

* Somos capaces de resolver problemas muy diferentes

* El objetivo es que el programa también sea capaz de resolverlos

* Para resolverlos de manera automática, necesitamos:
    
    1. Una representación común para todos los problemas
    2. Algoritmos que usen alguna estrategia para resolver problemas de representación común

## Representación de problemas

### Representación general

    1. Espacio de estados: un problema se divide en un conjunto de pasos de resolución. 
    2. Reducción a subproblemas: un problema se puede descomponer en una jerarquía de subproblemas. 
    
### Representación a problemas específicos

    1. Resolución de juegos
    2. Satisfacción de restricciones
    
### Estados

Definir un problema por los elementos que intervienen y sus relaciones

En cada instante los elementos tendrán unas características y relaciones específicas

Un estado es la representación de los elementos que describen el problema en un momento

Distinguiremos dos estados especiales:

1. Estados inicial: punto de partida
2. Estado final: objetivo del problema

### Operadores

Para poder movernos entre los diferentes estados. Transformación. 

Es una función de transformación sobre la representación de un estado que lo convierte en otro estado

Los operadores definen una relación de accesibilidad entre estados

Representación de un operador:
1. Condiciones de aplicabilidad
2. Función de transformación 

Los estados y su relación de accesibilidad conforman lo que se denomina espacio de estados

Representa todos los caminos que hay entre todos los estados posibles

### Solución

Secuencia de pasos que llevan del estado inicial al final (secuencia de operadores) o estado final

Tipos de solución: una cualquiera, la mejor, todas

Coste de una solución: gasto en recursos de la aplicación de los operadores. Puede ser importante o no según el problema y que tipo de solución busquemos. 

### Tipos de algoritmos

#### Algoritmos de búsqueda ciega

    ◦ No tienen en cuenta el coste de la solución en la búsqueda
    ◦ Su funcionamiento es sistemático, siguen un orden de visitas y generación de nodos establecido por la estructura del espacio de búsqueda
    ◦ Anchura prioritaria, Profundidad prioritaria, Profundidad iterativa
    

##### Búsqueda en anchura prioritaria
Los nodos se visitan y generan por niveles

La estructura para los nodos abiertos es una cola (FIFO)

Un nodo es visitado cuando todos los nodos de niveles superiores y sus hermanos precedentes han sido visitados

*Características*

- Completitud: el algoritmos siempre encuentra una solución 
- Complejidad temporal: exponencial respecto al factor de ramificación y la profundida O(r**p)
- Complejidad espacial: exponencial respecto al factor de ramificación y la profundidad O(r**p)
- Optimalidad: la solución que se encuentra es óptima en un número de niveles desde la raíz


##### Búsqueda en profundidad prioritaria

Los nodos se visitan y generan buscando los nodos a mayor profundidad y retrocediendo cuando no se encuentren sucesores. 

La estructura para los nodos abiertos es una pila (LIFO)

Para garantizar que el algoritmo acaba debe imponerse un límite en exploración. 

*Características*

- Completitud: el algoritmo encuentra una solución si se impone un límite y la solución existe dentro del límite
- Complejidad temporal: exponencial respecto al factor de ramificación y la profundida del límite de exploración O(r**p)
- Complejidad espacial: en el caso de no controlar los nodos repetidos el coste es lineal respecto al factor de ramificación y el límite de profundidad O(rp). Si tratamos repetidos el coste es igual que en anchura. Si la implementación es recursiva el coste es O(p)
- Optimalidad: no se garantiza que la solución sea óptima


#### Algoritmos de búsqueda heurística

    ◦ Utilizan una estimación del coste de la solución para guiar la búsqueda
    ◦ No siempre garantizan el óptimo, ni una solución 
    ◦ Hill-climbing, Branch and Bound, A∗, IDA∗
