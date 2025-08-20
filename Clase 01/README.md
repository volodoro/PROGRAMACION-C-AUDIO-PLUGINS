### INTEL ---> Hasta el 2020 aprox ellos proveían los procesadores tanto para WIN como para MAC. Luego Mac empezó a producir computadores con una tecnología llamada ARM. Son dos tecnologías diferentes de 
procesadores

ARM es la tecnología, y el primer procesador que lanzaron bajo esta tecnología fue llamado "M1", ahora van en "M4"

Microsoft suele ir atrasado en los cambios tecnológicos, en su momento lanzaron una versión windows de ARM, que se puede instalar en PCs que tengan procesador ARM. Intel no ha lanzado tecnología ARM. Por lo
tanto, un MAC con procesador ARM podría tener Windows (ARM) instalado. Si creamos un plugin para Intel y queremos que corra en MAC se puede hacer, pero necesitamos usar el hardware MAC para compilarlo.

Para este propósito debemos usar 'Xcode' en MAC, que es el análogo a VisualStudio para WIN

Si queremos imprimir variables usando la funcion printf en c, debemos hacerlo de la siguiente . ej:


#include <stdio.h>

int main()
{
    int x = 7;
    int y = 3;
    int z = x + y;

    printf("La suma de % y % es %", x, y, z);

     return 1;
}

donde las variables son las que van después de la coma y se corresponden con el orden en el que aparecen los símbolos % respectivamente. Además de eso, debemos declarar justo después del % el timpo de variable que estamos usando, como en este caso es un número, debemos usar "%n"

Porqué los punto flotante se llaman de esa manera?
Dependiendo del numero de bits que usemos para representar un numero binario la cantidad de posibilidades varían, ej, si tengo 2 bits son 4, si tengo 3 son 8 etc etc etc.

Algún día alguien pensó cómo podríamos guardar más variables usando x cantidad de bits. Por lo tanto, es una forma de representar combinaciones haciendo que 
la parte entera represente una cosa y la decimal, representada por la coma, que se va moviendo, representa otra.

'float' representa un número de punto flotante en 32 bits, 'double' representa uno en 64.

me acabo de dar cuenta de que 'char' viene de 'character'. los 'char' ocupan 8 bits. Por ejemplo una variable de 32 bits utiliza 4 bytes, cada byte son 8 bits

## Manejo de memoria

lo que uno puede almacenar son los bytes (1 byte equivale a 8bits). 
por ejemplo. char x = "a" ----> esto utiliza solo 1 byte, si escribo char y[] ya estoy comunicndo que utilizaré varios bytes, pero no especifico cuántos
ej: y [] = "Ricardo" ----> está utilizando 7 bytes


