# Clases y objetos

Una clase se puede entender como un nuveo tipo de dato que va más allá de las strings, los enteros y los decimales.
Cuando creamos una clase estamos creando un nuevo tipo de datos en c++. 
Una clase es básicamente una especificación de este nuevo tipo de datos.

por ejemplo --- class Book (se suelen anotar las clases con mayúscula). Le daremos atributos a la clase, y estos la describirán.
en este caso, sus atributos serán autor, titulo y cantidad de páginas.


``` cpp
class Book {
   public:
	   string title;
	   string author;
	   int pages;


};
```

un OBJETO es una instancia de esa clase. Un objeto es la cosa concreta que estoy representando con la clase
La clase es la plantilla y la instancia es su aplicación.

```cpp
int main()
{

	Book book1;
	book1.title = "Harry Potter";
	book1.author = "JK Rowling";
	book1.pages = 500;

	


	return 0;
}
```

Aquí se puede evidenciar cómo se usan los atributos que le fueron asignados a la clase anteriormente en la forma
nombreinstancia.atributo .

```cpp
int main()
{

	Book book1;
	book1.title = "Harry Potter";
	book1.author = "JK Rowling";
	book1.pages = 500;

	Book book2;
	book1.title = "Lord of the rings";
	book1.author = "Tolkein";
	book1.pages = 700;

	book2.title = "Hunger games"; //puedo ir cambiando los atributos como cualquier variable

 
	cout << book2.title; //debería imprimir "Hunger Games" ahora



	return 0;
}
```

# Constructores dentro de las clases

Un constructor es una función especial que será llamada cada vez que creemos un objeto a partir de una clase.

```cpp
class Book {
   public:
	   string title;
	   string author;
	   int pages;
	   Book() {
		   cout << "Creating Object" << endl;
		 }


};
```

En este caso, la función 'Book' imprimirá "Creating Object" tanto para book1 como para book2 en el código de más arriba.
La función también puede aceptar parámetros. Por ejemplo:

```cpp
class Book {
   public:
	   string title;
	   string author;
	   int pages;
	   Book (string name) {
		   cout << name << endl;
		 }


};


int main()
{

	Book book1("Harry Potter");
	book1.title = "Harry Potter";
	book1.author = "JK Rowling";
	book1.pages = 500;

	Book book2("Lord of the rings");
	book1.title = "Lord of the rings";
	book1.author = "Tolkein";
	book1.pages = 700;

	book2.title = "Hunger games"; //puedo ir cambiando los atributos como cualquier variable

 
	cout << book2.title; //debería imprimir "Hunger Games" ahora



	return 0;
}
```
en este caso definimos un string para introducir el nombre de cada libro. y en ambas instancias debemos introducir el tipo de dato
correspondiente (en este caso string) según lo que hayamos definido en la clase. En el último ejemplo, el código imprimirá el título de
los libros que será alojado en 'name'.

Cuando queremos crear estos objetos y les queremos dar información, hasta el momento hemos tenido que hacerlo manualmente indicando el tipo de datos.
¿Pero qué pasa si queremos crear 100 objetos? Podemos ocupar el constructor para inicializar nuestros objetos con información.
Por ejemplo, cuando creamos el book1, en lugar de especificar el título, nombre del autor y número de páginas, pasar esos valores a través del constructor.

Para eso primero debemos especificar los argumentos que utilizaremos con el constructor
por eso la 'a' antes de cada argumento.

```cpp
class Book {
   public:
	   string title;
	   string author;
	   int pages;
	   Book (string aTitle, string aAuthor, int aPages) {
		   title = aTitle;
		   author = aAuthor;
		   pages = aPages;
		 }


};
 ```
Abajo quedaría
```cpp
int main()
{

	Book book1("Harry Potter", "JK Rowling", 500);
	

	Book book2("Lord of the rings", "Tolkein", 700);


	
 
	cout << book1.title << endl;



	return 0;
}
```
# Funciones de Objeto}

Es una función que podemos poner dentro de nuestras clases. 

Ejemplo:

```cpp
#include <iostream>
using namespace std;

class Student {
   public:

	string name;
	string major;
	double gpa;
	Student(string aName, string aMajor, double aGpa){
	name = aName;
	major = aMajor;
	gpa = aGpa;

	}

};


int main()
{

	Student student1("Jim", "Business", 2.4);
	Student student2("Pam", "Art", 3.6);




	return 0;
}
```

Imaginemos que dentro de estos dos estudiantes queremos encontrar si alguno de ellos entró con una calificación mayor a 3.5 a su universidad. Para eso podemos crear una función en la clase Student que cada uno de los objetos puede utilizar para averiguar si la nota es mayor a 3.5 o no.

Para eso, dentro de la clase creamos una función que utilizará información de tipo booleano para analizar si el gpa es mayor o igual a 3.5

```cpp
// proyecto1.cpp : Este archivo contiene la función "main". La ejecución del programa comienza y termina ahí.
//

#include <iostream>
using namespace std;

class Student {
   public:

	string name;
	string major;
	double gpa;
	Student(string aName, string aMajor, double aGpa){
	name = aName;
	major = aMajor;
	gpa = aGpa;

	}
	bool hasHonors() {

		if (gpa >= 3.5) {

			return true;
		}
		return false;
	}

};


int main()
{

	Student student1("Jim", "Business", 2.4);
	Student student2("Pam", "Art", 3.6);

	cout << student1.hasHonors() << endl;



	return 0;
}

```
Lo bakán de la función es que cada uno de los objetos que utilizamos puede llamar a la función, y dependiendo del gpa arrojará una determinada respuesta. Como se puede apreciar arriba, si el if no se ejecuta, el código sabrá que debe dar una respuesta distinta, que en este caso será el 0.

# Getters and setters
Nos permiten controlar el acceso a los distintos atributos y elementos dentro de nuestras clases en c++.


```cpp
#include <iostream>
using namespace std;

class Movie { //nombre de la clase
   public:
	   string title; //atributo 1
	   string director; //atributo 2
	   string rating; //atributo 3
	   Movie(string aTitle, string aDirector, string aRating) { //constructor(argumento1, argumento2, argumento2)

		   title = aTitle;
		   director = aDirector;
		   rating = aRating;
	   }


};


int main()
{

	Movie avengers("The Avengers", "Joss Whedon", "PG-13");

	cout << avengers.rating;
}
```

El tema es que muchas veces en cpp cuando creamos algo como una clase queremos controlar qué información puede ser almacenada por un objeto en particular.

Por ejemplo, en este caso el rating es PG-13, pero podrían haber otros como:
G, PG, PG-13, R, NR, etc.

En este caso estamos introduciendo PG-13, pero imaginemos que queremos ingresar otra cosa
Por ejemplo:

```cpp
	Movie avengers("The Avengers", "Joss Whedon", "Dog");
```
En este caso quisiéramos forzar el uso de una nomenclatura válida.

