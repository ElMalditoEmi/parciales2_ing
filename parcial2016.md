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

- Agregar/quitar atributos
Quitar atributos puede simplificar las interfaces, baja el acoplamiento.
Solo se debería agregar en caso que los datos no tengan la información suficiente para 
realizar la función.

Ej:
```c
print_name(name,surename,age,weight){
    printf("%s.",name);
}
print_name_2(name,surename,age,weight){
    printf("%s.",name);
}
```

- Subir bajar metodos.
Cuando un mismo metodo esta siendo declarado para varias clases hijas en la misma jerarquia
seria mejor que estas, lo hereden.

ej:
```python

class Mammal():
    
class Dog(Mammal):
    def walk():
        print("walking...")

class Cat(Mammal):
    def walk():
        print("walking...")

```
Se cambia por:
```python

class Mammal():
    def walk():
        print("walking...")
    
class Dog(Mammal):

class Cat(Mammal):


```


- Condicionales por polimorfismo
Cuando la condición depende del tipo y se se esta chequeando con 'if', no se esta explotando
el potencial de la orientacion a objetos. Manejar la condicion con polimorfismo es mejor.

ej:
```python
class Dog(Mammal):

class Cat(Mammal):


def group_animals(animal):

    if(animal is Dog):
        dogs.append(animal)

    if(animal is Cat):
        cats.append(animal)

```
Cambia a:
```python
class Dog(Mammal):
    def add_to_group()
        dogs.append(self)

class Cat(Mammal):
    def add_to_group()
        cats.append(self)


def group_animals(animal):
    animal.add_to_group()

```

Faltaria ver ejemplos de:
- Desplazamiento de metodos

- Desplazamiento de atributos

- Extraccion de clases


# 3. Elija dos modelos de proceso de desarrollo y comparelos
Modelos elegidos: Iterativo, Prototipado

Fortalezas de Iterativo:
- Los pagos y las entregas son incrementales
- Se provee feedback en cada iteración

Debilidades de Iterativo:
- El diseño y la arquitectura podrian no ser optimos
- La revisión y el diseño pueden incrementarse
- El costo total puede ser mayor

Fortalezas de Prototipado:
- Los requerimientos se congelan mas tarde
- Feedback del cliente durante el prototipado
- Los desarrolladores ganan experiencia con el problema durante el desarrollo del prototipo

Debilidades de Prototipado:
- Potencial impacto en costo y tiempo

En proyectos de desarrollo donde los requerimientos podrian cambiar mucho, el modelo iterativo
reacciona mejor el el prototipado. Además el feedback provisto por el iterativo es 
en cada iteración del proceso de desarrollo, mientras que en el prototipado es un feedback
inicial. Se puede perder mucho tiempo haciendo el prototipo, que encima sera descartado. El 
modelo iterativo producira su implementación inicial como implementacion de un subconjunto del 
problema completo pero siempre la usará hasta el final para el producto.

# 4. ¿Cual es la principal motivación de tener un proceso de desarrollo de software separado en fases? ¿En que consiste el enfoque ETVX? Describa brevemente las actividades basicas del desarrollo de software

# 5. Describa cuales son las diferentes fases del proceso de administracion del proyecto
### 1. Planeamiento
Se realiza antes de comenzar el proyecto, algunas actividades básicas son
- Estimación de costos y esfuerzo
- Selección del personal
- Planear el seguimiento
- Planear el control de calidad

### 2. Seguimiento y control
Esta fase esta activa mientras se trabaja en el proyecto.
Sus actividades son:
- Seguir y observar los parametros claves como: riesgo,tiempo,costo.
- Tomar acciones correctivas si es necesario.

### 3. Analisis y terminación
Se hace al final del proyecto, o al final de cada iteración en modelos iterativos.

El proposito principal es analizar el desempeño del proceso y las lecciones aprendidads

La idea es mejorar el desempeño en futuros proyectos o en proximas iteraciones del mismo.

# 6. Describa los procesos de códificacion: incremental, TDD, programación de a pares
### Programación incremental
Partiendo de la especificación de requerimientos, se escribe código que implementa
la funcionalidad, posteriormente se escriben los test scripts para probar la funcionalidad
implementada. Se correr los tests usando la implementación, si la funcionalidad no los
pasa, debe ser corregida (se vuelve al paso anterior). En caso de pasarlos, se debe 
verificar si todos los requerimientos estan implementados, si no lo están, se vuelve al 
paso donde se escribe código para implementar la funcionalidad. En otro caso el producto de 
trabajo puede ser revisado.

### TDD
En este caso, a partir de la especificacion de requerimientos se debe:
1. Escribir los tests scripts que pueda pasar una implementación que implementa dichos requerimientos
2. Escribir el código suficiente como para pasar los tests.
3. Correr los tests scripts.
4. Si el test halla un error, debe ser corregido y volver al paso 3.
5. Si el código puede ser mejorado, debe volver al paso 2 y hacerlo.
6. Si el código no cubre todos los requerimientos, volver al paso 1.

En este proceso se depende mucho de la exhaustividad de los test para asegurar
que todos los requerimeitnos están siendo cumplidos.

### Programación de a pares
Para llevarse a cabo debe haber dos desarrolladores simultaneamente, uno tendrá el rol de 
codificar, y el otro debe leer el código y revisarlo activamente.
Los roles deben ser intercambiados periodicamente.

# 7. ¿Que son y para que sirven los criterios de selección de tests?
Dado que los casos de test podrían llegar a ser infinitos, o simplemente un número inviable
por los costos del testing, se quiere poder testear hallando el mayor número de defectos
en el código, con una cantidad razonable de tests cases.

Los criterios de selección de tests son reglas/heuristicas que permiten hallar casos 
de tests efectivos encontrando defectos, y descartando casos de tests que, según el
criterio no hallarian nuevos defectos.

Por ejemplo el criterio de clases de equivalencia considera, seprar el conjunto de 
valores de entrada en subconjuntos llamados clases de equivalencia. Siguiendo este 
criterio tomar una de las entradas de la clase de equivalencia, es representativo
para todos los elementos de la misma clase de equivalencia, por lo que no hace 
falta testear mas que una entrada por clase de equivalencia.
