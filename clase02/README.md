# Apuntes clase 02 27/08/25

## Control de flujo y ciclos o loop

Si tuviera un selector de 4 pasos en un plugin necesito una variable para registrar su posición, si lo definiera como un entero, qué problema tendría?
De este modo se ocuparía demasiada memoria.

En el ciclo switch, la función 'break' se usa para hacer que el código deje de evaluar todos los casos en el ciclo una vez que haya encontrado aquel caso en el que la comparación es verdadera,
de esta forma ahorramos que el programa evalúe todos los casos innecesariamente.

### ¿Cuál es el sentido del ciclo while?

Supongamos que hay que ordenar silas en un gimnasio, llega un camión lleno de sillas y tenemos que ordenarlas, tenemos condicion de inicio y final, la condicion de inicio es que no hay sillas
y la condicion final es que no caben más. Otra historia similar sería que la instrucción fuese "de las sillas qu hay ahí, coloque 30". Agarro una, la coloco, otra, la coloco, y desde que comienzo, sé cuando 
detenerme. Este ejemplo sería el ciclo for, porque sabemos a priori cuando detenernos. 

En cambio en el while, si bien se puede implementar igual al for, podemos no saber desde el principio cuántas iteraciones tendremos, sino que podemos simplemente fijar una condición, que cuando se cumpla 
detendrá el ciclo.

Ejemplo: Cuando tenemos un archivo de audio cargado en un programa y le ponemos play para escuchar, lo que hace el pc internamente, es ir al lugar donde está el archivo y leer la primera muestra, que será 0, luego así 
con todas las muestras. Cuando ponemos play, el pc no sabe cuántas muestras hay con anterioridad, los archivos se leen hasta que el archivo se acaba. Hay una directiva de "EOF" (End Of File), y al instante
en el que el pc lee el EOF, concluye su tarea. Todos los archivos tienen EOF.

## Punteros

printf("\nLa variable var1 tiene asignada la direccion %p", &var1); ¿Qué significa el %p

Lo que habrá a la salida:

La variable var1 tiene asignada la direccion 00000088C8EFF9C4 ---> Hexadecimal, 16 caracteres.

cuando definimos por ejemplo int var1 = 77; el valor 77 es guardado en la RAM en un bloque vacío. ¿cómo podemos encontrar el 77 dentro de la RAM?
Con una dirección como la de arriba. Para el computador la variable no se llama var1, una vez que el pc complila, la variable se llama 00000088C8EFF9C4. Esto
es mun pointer, que corresponde simplemente a una dirección de memoria.

si escribo:

int ptr = var1; el computador debería buscar un espacio de memoria libre y grabar el 77, pero como es una nueva variable está en otra dirección y en consecuencia tendrá una nueva dirección. Pero si después digo

z = var1+ptr = 154 ¿Qué hará el pc? Meter el 154 en una dirección que esté desocupada, por lo que tendrá una nueva dirección. Así es como lo hemos estado 
haciendo hasta el momento.

¿Qué es lo nuevo ahora?

int* ptr1 = &var1;  lo que me está diciendo lo del lado izquierdo con el asterisco es que estoy creando una direcipon de memoria. Por lo tanto si quisiera definir algo en esta igualdad, no puede ser un valor, pues la expresión espera una dirección de memoria, por lo que debo igualarla con otra dirección.
¿Cómo hacerlo?

int *ptr1 = &var1; ---> El '&var1' no es directamente el valor de var1 sino su dirección de memoria.

¿Para qué sirve esto? Primero que nada para ocupar menos memoria, también para acelerar el cálculo, al usar punteros puedo actuar varias veces sobre la misma dirección. Por ej, crear tres direcciones significa acceder a la memoria tres veces. A nivel humano esas velocidades son micro o milisegundos, pero al sumar toda la info a procesar en un código real, se puede hacer considerable.

Ej: Un proyecto de audio a 44,1kHz de frecuencia de muestreo, 10 pistas, tres minutos. ---> 44100 * 10 * 3 * 60

*** NOTA: crear una variable no es lo mismo que inicializarla.

