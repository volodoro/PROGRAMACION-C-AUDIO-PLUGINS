### Clase 05

## Clases 

Una de las principales extensiones de C++ en relación a C

```cpp
#include <iostream>
#include <string>

// Definicion de la clase MyClass - - - - - - - - - - - - - - - - - - 
class MyClass
{
public:
	MyClass();	// Constructor    ---> ambas clases deben ser publicas
	~MyClass();	// Destructor     ---> ambas clases deben ser publicas



	/*el constructor y destructor difieren de otras variables porque no necesitan una clave de declaración previa
	solo tienen que tener el mismo nombre de la clase*/

	void MyFuncion(); // ---> Aquí por ejemplo estoy declarando que MyFuncion es un void, i.e. no entrega un valor de salida

private:

};

```

Hay varias formas de armar los programas. Por ejemplo, podríamos definir la estructura o implementación de la clase, es básicamente lo que estaría en los corchetes. Sería el cuerpo de la función.

Ejemplo:

```cpp
public:
	MyClass();
{
}  

	~MyClass();	    

{
}  

	void MyFuncion(); 
{
} 
private:

};
```

La implementación podría estar directamente después de que defino la clase, pero en el flujo de trabajo real, la definición y la implementación se hacen en instancias separadas y de hecho las últimas suelen estar en archivos .h

```cpp
// Implementacion de la clase
MyClass::MyClass()
{
}

MyClass::~MyClass()
{
}

```
```cpp
	this->length = length;
	this->values = new float[length];
```

recordar que la función 'this' indica que una variable está asociada a la clase con la que estamos trabajando

