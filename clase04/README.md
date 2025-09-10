# INTRODUCCIÓN A C++

C++ nace a partir de una extensipon de C, esto significa que la sintaxis de algunas funciones podrían cambiar, aunque las estructuras en general son compatibles

## Principales extensiones

### Una de las principales es la existencia de las CLASES

Las clases tienen varias funciones importantes como herencia y mutabilidad. Entonces C ++ es un C con clases.

Una analogía de una clase ---> digamos que hay una clase tipo 'automóvil'. Esta clase tiene por ejemplo, ruedas, asientos, motor, color, peso, manubrio.
Esto significa qu cada clase tendrá ciertas CARACTERÍSTICAS con las que podemos diferenciar elementos de una misma clase.

Las clases también tienen USOS. Por ejemplo, el automóvil sirve para movilizar personas, carga, para carreras clandestinas, desarmarlo, escuchar música, etc.

En C no existen clases sobre las que pueda definir usos. Las propiedades don análogas a las variables. 

## Herencia y mutabilidad

Herencia ---> Significa que si creamos una clase podemos crear OTRA clase que herede características que tenga la anterior además de sus características propias
con las que contaba anteriormente

Mutabilidad ---> Cuando proogramamos debemos decir expresamente de qué tipo serán (int, float, char, etc.). Sin la mutabilidad deberíamos crear varias funciones 
para que una clase pueda realizar distintas tareas. La mutabilidad permite que podamos definir UN SOLO NOMBRE DE FUNCION. ej: transporte/carga. Así, la función
mutará según sus variables de entrada.
  ---------------------------------------------------------------  ------------------------------------------------------------------------------

  Recordemos que #pragma once se usa para no recargar librerías en un código

Elementos nuevos ----> class, public, private

Pensemos que 'class' es un restorán, que tiene lugares públicos como mesas, baño, etc, mientras que también habrá partes privadas como cocina, oficinas, etc.

Recordemos que 'void' representa una función que no entregará una variable de salida.

cuando se escribe 'override' significa que se está volviendo a implementar una función que fue previamente definida.
qué significa el doble dos puntos? (::) ---> es la concadenación entre una clase y su función.

### YA NO SE USA PRINTF PARA IMPRIMIR EN PANTALLA YA QUE CORRESPONDE A UNA FUNCIÓN DE C

Imprimir en cpp es más sencillo que en c. En cpp se usa std::out, que significa standard command out. std::endl significa final de línea como el\n en c.


