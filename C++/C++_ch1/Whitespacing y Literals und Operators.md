2024-10-01 18:33

Tags: #C 

# Whitespacing y formateo

	Whitespace Se refiere a caracteres especificos para la creacion de un formato en C++.
* Espacios 
* Newlines 
* Tabs 

No importa como se aplique ni la cantidad mientras que existan para la correcta compilacion.

# Literales y Operadores 

Se trata de un valor fijo puesto de manera literal en el código, como:

```C++
int x {5};
```

Mientras que se entiende a los _operadores_  como:
* +
* -
* /
* *
* =
* <<
* >>
* ==
* new
* delete
* throw

Y muchos mas. La cantidad de inputs que acepta un operador es llamado _arity_, que se dividen en:
* _Unary_  : 1 input, "-". Ej: "-5".
* _Binary_  : 2 inputs, "+" ,">>", "<<"
* _Ternary_  : 3 inputs, tratados en [REFERENCIA] 
* _Nullary_  : 0 inputs, tratados en [REFERENCIA]

No todo operador retorna valores y algunos tienen _side effects_ que se define como un efecto observable de un operador posterior al retorno de un resultado. Tal es el caso del operador de asignación _=_.

Al combinar todo lo anterior se llegan a la concatenacion de operadores y posteriormente a la expresiones.

	Expresion : Secuencia no vacia de literales, variables, funciones y operadores. 
Tambien existen terminos como _Subexpression_, _Full expression_ , _Expression Statement_.

```C++
// five() is a function that returns the value 5
int five()
{
    return 5;
}

int main()
{
    int a{ 2 };             // initialize variable a with literal value 2
    int b{ 2 + 3 };         // initialize variable b with computed value 5
    int c{ (2 * 3) + 4 };   // initialize variable c with computed value 10
    int d{ b };             // initialize variable d with variable value 5
    int e{ five() };        // initialize variable e with function return value 5

    return 0;
}
```
