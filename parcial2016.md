# 1. ¿Que es la estructura estatica de un programa? ¿Que la estructura dinamica? ¿cual es el objetivo de la programacion estructurada?
La estructura estatica de un programa describe la forma en que se declaran las sentencias, por otro lado la estrucutra dinamica
es el orden en que dichas sentencias son ejecutadas. Estas no siempre son iguales, en lenguajes no estructurados
la ejecucion salta de bloques de sentencias a otros.

El objetivo de la programacion estructurada es que la estructura dinamica sea igual a la estructura estatica, es decir
que los programas ejecuten las sentencias en el orden en que aparecen. Esto ya que el análisis de correctitud del código
se hace sobre la estructura estatica.

La programación estructurada logra esto usando constructores de única salida y única entrada (while,if,for). Por otro 
lado, en las estructuras de datos , solo hay unas ciertas operaciones válidas para usarlas y en prog. estr. Solo 
se proveen las operaciones permitidas (Principio de ocultamiento).

# 2. ¿Que es la refactorización de código?
Durante la etapa de codificación, a medida que se van introduciendo cambios para implementar nuevas funcionalidades
se deteriora el diseño original del código, además de que este podría se mucho mas mantenible y testeable.
La refactorización es la acción de modificar el código para sin alterar
las funcionalidades existentes ni su comportamiento externo para mejorar la cohesión, reducir el acoplamiento y
mejorar la respuesta ante el OCP.

La refactorización debe parar la implementación de nuevos features, y continuarla una vez terminada la refactorización.


La refactorización suele hacerse enfocandose en mejorar metodos, clases y jerarquia de clases, algunas de las
refactorizacions mas comunes son:

- Extracción de metodos.
En metodos que son demasiado largos, una sección con una acción bien definida podria ser extraida
como otro metodo, donde la signatura describe la acción. Mejora en gran medida la legibilidad y en
consecuencia la mantenibilidad y el testeo del metodo.

Ej:
```C
funcioncita(){
    int arr[N]:

    // Inicializar el arreglo

    for (int i = 0; i < N-1 ; i++){ // Selection sort
        for (int j = 0; j < N-1 ; j++)
            if ( arr[j] >= arr[j+1]){
                swap(j,j+1,arr);
            }
    }

    // Mas operaciones en el arreglo

    return 0;
}
```
Podría pasar a ser:
```C
funcioncita(){
    int arr[N]:

    // Inicializar el arreglo

    selection_sort(&arr[N]);

    // Mas operaciones en el arreglo

    return 0;
}
```

# 3.
# 4.
# 5.
# 6.
# 7.
# 8.
# 9.