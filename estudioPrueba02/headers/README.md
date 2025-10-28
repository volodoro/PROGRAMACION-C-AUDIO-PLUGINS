# HEADERS en C++

Recordemos que si queremos definir una variable, primero debemos definir el tipo de info que
estará alojada en ella y lugo inicializarla dándole un valor. Y si queremos usar una función
necesitamos declararle y lugo definirla. La declaración va antes del main y la definición despues.

```cpp
#include <iostream>
using namespace std;

const char* RecomendMeAFood(char firstLetter);

int main()
{


}
const char* RecomendMeAFood(char firstLetter) {

	if (firstLetter == 'a' || firstLetter == 'A') {
		return "apple";
	}
	else if (firstLetter == 'b' || firstLetter || 'B') {
		return "banana";
	}
	else if (firstLetter == 'c' || firstLetter || 'C') {
		return "chocolate cake";
	}
	else return "pizza";
}
```
arriba hemos definido una función que acepta como parámetro un caracter y en funcion de eso 
recomendará una comida devolviendo una constante en forma de string
La declaramos antes del main pero definimos su funcionamiento después. 
Ahora, podremos llamar la función desde el main.

Ahora, hasta el momento solo tenemos un archivo cpp, pero qué pasaría si fuera más de uno?
Y qué pasaría si más de un archivo quisiera utilizar esa función?
Para entender esto debemos entender cómo funciona la compilación. Cuando un programa es compilado
cada archivo cpp será compilado en un unidades de compilación independientes. Así es como 
se hacen los archivos de objeto. Estsas unidades de compilación son independientes, por lo que
no pueden 'saber' qué tipo de código está declarado en otro archivo cpp.

Si intentamos copiar la definición en cada archivo cpp en que queramos usarla, obtendríamos 
un error. ¿Por qué?

Porque cuando nuestro linker intenta enlazar todos los archivos .objse dará cuenta de que 
tenemos múltiples definiciones para la misma función.

Para eso emplearemos los archivos tipo 'Header', en este archivo ubicaremos las declaraciones.
Luego hacemos otro archivo .h de implementación donde irán ubicadas las declaraciones.

En este caso, hemos creado dos archivos:

1) Food.h ---> Carpeta archivos de encabezado ---> Aquí se declararán la función a emplear
2) Food.cpp ---> carpeta archivos de origen ---> Este será el archivo encargado de Implementar la función.

En el archivo Food.cpp, que será el encargado de implementar las funciones declaradas en el
archivo de encabezado, debemos dar la orden de responder a dichas declaraciones. Esto se debe
indicar incluyendo el archivo de encabezado de la siguiente manera
```cpp
#include "Food.h" //cabe destacar que son comillas dobles
```
Cuando traslademos la declaración y la definición de la función RecommendMeAFood a los archivos de declaración e implementación respectivamente, el archivo principal arrojará un
error, ya que no tendrá definida dicha función, por lo que esta vez debemos incluir el archivo de encabezado de la siguiente manera.

```cpp
#include <iostream>
#include "Food.h"



int main()
{
	std::cout << "Today I will eat " << RecommendMeAFood('c');


}
```

Ahora, para implementar otra función, debemos definirla en el archivo Food.h, lo hacemos así:

```cpp
#pragma once

const char* RecommendMeAFood(char firstLetter);
void GetPizzaRecipe();
```

Ahora implementamos la función en el archivo Food.cpp

```cpp
#include "Food.h"

const char* RecommendMeAFood(char firstLetter) {

	if (firstLetter == 'a' || firstLetter == 'A') {
		return "apple";
	}
	else if (firstLetter == 'b' || firstLetter == 'B') {
		return "banana";
	}
	else if (firstLetter == 'c' || firstLetter == 'C') {
		return "chocolate cake";
	}
	else return "pizza";
}

void GetPizzaRecipe() {

	std::cout << "To make pizza you need... ";
}
```

Podemos notar que, al intentar imprimir con std::cout, el programa arroja un error. Esto se debe a la ausencia de la librería iostream, la cual se encarga de funciones básicas como std::cout. Por lo que debemos incluir la librería en nuestro archivo de implementación.
