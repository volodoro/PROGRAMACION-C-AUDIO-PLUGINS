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

class Movie { //nombre de la clase
   public: //esto significa que cualquier otra pieza fuera de la clase puede acceder a los datos dentro 
	   string title; //atributo 1
	   string director; //atributo 2
	   string rating; //atributo 3
	   Movie(string aTitle, string aDirector, string aRating) { //constructor(argumento1, argumento2, argumento2)

		   title = aTitle;
		   director = aDirector;
		   rating = aRating;
	   }


};

Cuando usamos private:, hacemos que ninguna otra parte del código que se encuentre fuera de la clase  Movie pueda acceder a la fracción de código que esto afecte

por ejemplo 

```
class Movie { //nombre de la clase
private:
	   string title; //atributo 1
   public:
	   string director; //atributo 2
	   string rating; //atributo 3
	   Movie(string aTitle, string aDirector, string aRating) { //constructor(argumento1, argumento2, argumento2)

		   title = aTitle;
		   director = aDirector;
		   rating = aRating;
	   }


};
```
En el caso de arriba, niguna otra parte del código podrá acceder a los datos almacenados 
en el atributo title, no se podrá imprimir, modificar, etc.

Podemos aprovechar lo público y privado para controlar qué ratings se asignan a la película

```cpp
#include <iostream>
using namespace std;

class Movie { //nombre de la clase
private:
	string rating; //atributo 3
   public: //esto significa que cualquier otra pieza fuera de la clase puede acceder a los datos dentro 
	   string title; //atributo 1
	   string director; //atributo 2
	   Movie(string aTitle, string aDirector, string aRating) { //constructor(argumento1, argumento2, argumento2)

		   title = aTitle;
		   director = aDirector;
		   setRating(aRating);
	   }

	   void setRating(string aRating) {

		   rating = aRating;
	   }

};


int main()
{

	Movie avengers("The Avengers", "Joss Whedon", "PG-13");
	avengers.setRating("Dog");
	
}
```
en este caso, no podemos acceder al rating directamente porque es privado, sin embargo al
definir la función setRating, que se encuentra en la parte pública de la clase, podemos acceder al rating a través de ella pero llamando a avengers.setRating e ingresando el string en su argumento.

Ahora lo que podemos hacer es implementar reglas dentro de la función setRating para
qué datos serán válidos

```cpp
#include <iostream>
using namespace std;

class Movie { //nombre de la clase
private:
	string rating; //atributo 3
   public: //esto significa que cualquier otra pieza fuera de la clase puede acceder a los datos dentro 
	   string title; //atributo 1
	   string director; //atributo 2
	   Movie(string aTitle, string aDirector, string aRating) { //constructor(argumento1, argumento2, argumento2)

		   title = aTitle;
		   director = aDirector;
		   setRating(aRating);
	   }

	   void setRating(string aRating) {

		   if (aRating == "G" || aRating == "PG" || aRating == "PG-13" || aRating == "R" || aRating == "NR") {
			   rating = aRating;
		   }
		   else
			   rating = "NR";

	   }

	   string getRating() {

		   return rating;
	   }

};


int main()
{

	Movie avengers("The Avengers", "Joss Whedon", "PG-13");
	avengers.setRating("PG-13");

	cout << avengers.getRating();
	
}
```
en el código de arriba lo que hicimos fue implementtar un if para restringir los posibles
ratings que pueden ser ingresados a través de la función setRating, por lo que en caso de que el string ingresado coincida con alguno de los estipulados en el if, se dará paso a que rating sea igual a aRating, en el caso de que no coincida, con else harmeos que
el rating automáticamente tome el string "NR". Luego se implementó una función que nos 
entrega el rating para poder imprimirlo, ya que de otra manera no podríamos acceder a él 
debido a su carácter privado.

# Herencia

La herencia permite definir una clase, luego otras, y hacer que esas otras puedan extender esas pueden extender o heredar las funciones de la clase original

```cpp
#include <iostream>
using namespace std;

class Chef {

  public:
	  void makeChicken() {
		  cout << "The chef makes chicken" << endl;
	  }
	  void makeSalad() {
		  cout << "The chef makes salad" << endl;
	  }
	  void makeSpecialDish() {
		  cout << "The chef makes special Dish" << endl;
	  
	  }
};


int main()
{

	Chef chef;
	chef.makeChicken();
	return 0;
	
}
```
En el código anterior hemos definido una clase llamada Chef, donde existen tres funciones bastante evidentes.

Ahora, ¿qué pasa si además de representar un chef común y corriente queremos representar un chef italiano? Crearemos una clase para eso.

Digamos que para este propósito queremos que el chef italiano sea capaz de preparar todos los platos del chef genérico (pollo, ensalada, special dish). Para una ocasión como esta es que podemos utilizar la herencia. Podemos heredar todas las funciones de chef al chef italiano.

```cpp
#include <iostream>
using namespace std;

class Chef {

  public:
	  void makeChicken() {
		  cout << "The chef makes chicken" << endl;
	  }
	  void makeSalad() {
		  cout << "The chef makes salad" << endl;
	  }
	  void makeSpecialDish() {
		  cout << "The chef makes bbq ribs" << endl;
	  
	  }
};

class ItalianChef : public Chef {

  public:

	void makePasta() {
		cout << "The chef mañes pasta" << endl;
	}
	void makeSpecialDish() {
		cout << "The chef makes chicken parm" << endl;

	}
};

int main()
{

	Chef chef;
	chef.makeSpecialDish();

	ItalianChef italianChef;

	italianChef.makeSpecialDish();
	
	return 0;
	
}
```
Como podemos apreciar en el fragmento de código de arriba, hemos creado una clase llamada ItalianChef que hereda todas las fucniones del chef corriente a través de la línea public: Chef.

También podemos notar que, además de heredar todas las funciones existentes en la clase Chef, hemos implementado una función llamada makesPasta, que solo podrá ser realizada por la subclase ItalianChef y no por la corriente.

Otra cosa que podemos hacer es sobreescribir ciertos aspectos de alguna función heredada.
Por ejemplo, se puede ver que en ItalianChef la función makesSpecialDish ahora imprimirá en la consola "The chefakes Chicken Param" y no el "The chef makes
bbq ribs" como lo dictaba la función originalmente.


