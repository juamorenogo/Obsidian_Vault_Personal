	2024-09-29 14:46

Tags: #C #Clibreria
# cout
Llamada  **input/output library** hace parte default de las librerias de _C++_ , donde _cout (character output)_ muestra texto en la consola usando _Operador de insercion "<<"_. El cual puede concatenar impresiones: 
```C++
#include <iostream> // for std::cout
int main()
{
    std::cout << "Hello" << " world!"<< endl;
    return 0;
}
```
Esta sentencia se almacena en el _Buffer_ , osea tiene un limite de transferencia y un tiempo de espera de esta misma.

### Saltos de linea
	std::endl vs \n.
La primera opcion _std::endl_ es menos eficiente ya que añade datos al buffer, mientras que _\n_ hace el salto directo, de la siguiente forma:
```c++
#include <iostream> // for std::cout

int main()
{
    int x{ 5 };
    std::cout << "x is equal to: " << x << '\n'; // single quoted (by itself) (conventional)
    std::cout << "Yep." << "\n";                 // double quoted (by itself) (unconventional but okay)
    std::cout << "And that's all, folks!\n";     // between double quotes in existing text (conventional)
    return 0;
}
```

#### Nota
* Comilla simple : caracteres simples.
* Comilla doble : texto _Recomendado para \n_ .

# cin

Siendo que se trata de _character input_ donde se lee el input del teclado, usando el _Operador de insercion ">>"_ .
```c++
#include <iostream>  // for std::cout and std::cin

int main()
{
    std::cout << "Enter two numbers separated by a space: ";

    int x{}; // define variable x to hold user input (and value-initialize it)
    int y{}; // define variable y to hold user input (and value-initialize it)
    std::cin >> x >> y; // get two numbers and store in variable x and y respectively

    std::cout << "You entered " << x << " and " << y << '\n';

    return 0;
}
```

Detendra el programa para la toma de datos tomando multiples datos para diferentes variables. A su vez tambien es una sentencia que usa el _buffer_. 

#### Nota : 
	Ejemplo: Si se extrae un dato del buffer `[1, 2, 3]`, el número 1 será procesado primero, y el buffer se convertirá en `[2, 3]`.
Si se toma la informacion al final del _buffer_ y se remueve del inicio del _buffer_, se asegura que sera procesado al tiempo y orden en que se añada (FIFO). 

Esta sentencia siempre necesita el enter y lo añade al _buffer_ de manera que:

+ Al ingresar _5a_ en el buffer se vera _5a\n_ .
## Ejemplos generales:

```c++
#include <iostream>  // for std::cout and std::cin

int main()
{
    std::cout << "Enter a number: "; // ask user for a number
    int x{}; // define variable x to hold user input
    std::cin >> x; // get number from keyboard and store it in variable x
    std::cout << "You entered " << x << '\n';

    return 0;
}
```

* Si *x=h* x se asignara como 0 debido a que no hay ningun entero, no obstante, no dara un error al compilar.
* Si _x = 123abc_ x se asignara al valor 123.
* Si _x = abc123_  x se asignara a 0, debido a que las letras daran a entender que en la variable no hay enteros (Extraccion invalida desde a).
* Si _x=3.2_ o _x=3.7_ siempre x se asignara el valor de 3.