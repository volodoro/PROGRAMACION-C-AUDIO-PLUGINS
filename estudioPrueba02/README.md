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

#continuará...

