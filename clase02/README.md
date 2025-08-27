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
