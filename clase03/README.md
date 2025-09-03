
## Funciones en C

Hay dos tipos de variables o dos formas de declararlas ------> void (){} y nombre de función (int = x, float = y) [o cualquier tipo de variable],

Existe una diferencia fundamental entre ambas: mientras que el segundo tipo de función DEVUELVE una variable con la que se pueden hacer operaciones posteriores, las funciones creadas con void(){} NO DEVUELVE
VARIABLES, y sirve principalmente para calcular e imprimir valores en la consola.

cuando definimos una CONSTANTE usando '#' (con el precompilador) lo hacemos de la siguente forma:

#define PI 3.14159265 ------> Cabe destacar que se utiliza signo es igual (=), simplemente porque esa es su sintaxi, también, por convención estas constantes se definen en mayúsculas

Existen dos formas de pasarle variables a una función; todos los lenguajes derivaddos de C funcionan con ambos tipos

1) Función con paso de variable como dato
Ejemplo

float sum(float x,float y){

return x + y;
{
luego si tengo más variables:

float a = 7;
float b = 3;
float c = 0;

En total, se usaron 3 variables

c = sum(a, b); ---> estoy pasando los datos de la función como un dato más. y asignando a con x y b con y.


2) Función con paso de variable por referencia
   
La funcion initialize_vector es con paso de variable por referencia (a una dirección de memoria(puntero)):

cómo se podría definir la función sum en este estilo?

¿qué debo considerar?---> ¿necesito una variable de salida?

Yo podría decir, en vez de que me de un valor y asignarle una variable a un valor (por ejemplo z), puedo usar un puntero que me indique dónde se aloja dicha variable.

void sum(float x, float y, float z) como no va a tener un return tengo que 'inyectar' el puntero

z = x + y; } ---> tengo que aclarar que el pc no me pase esta variable como dato sino como dirección.

float z;
sum(7,3,z)

En la definicion de la funcion, a la variable de entrada z, debo añadirle un * para que se sepa que ésta es un puntero.

void sum(float x, float y, float* z)
{z = x + y;
}

malloc: (memory allocation) ---> tengo que decirle cuantos bytes estoy tratando

------------------------------------

float z = 0;
print z---> imprime z = 0;
sum(7,3,&z);
print(z) ---->z = 10
