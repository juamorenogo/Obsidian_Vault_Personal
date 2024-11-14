2024-09-29 16:02

Tags: #C

Inicializar se refiere a darle un espacio de memoria a la variable, mas no darle un valor a la misma. 
	- Initialized = The object is given a known value at the point of definition.
	- Assignment = The object is given a known value beyond the point of definition.
	- Uninitialized = The object has not been given a known value yet.

El comportamiento indefinido puede generarse por la generación de un código que el lenguaje no sabe interpretar correctamente, los síntomas de esto son:

	- Your program produces different results every time it is run.
	- Your program consistently produces the same incorrect result.
	- Your program behaves inconsistently (sometimes produces the correct result, sometimes not).
	- Your program seems like it’s working but produces incorrect results later in the program.
	- Your program crashes, either immediately or later.
	- Your program works on some compilers but not others.
	- Your program works until you change some other seemingly unrelated code.

#  Implementation-defined behavior:
Entendiendo _Implementation_ como el conjunto del compilador y librerías estándar de C++. Esto variara dado el siguiente código:

```C++
#include <iostream>

int main()
{
	std::cout << sizeof(int) << '\n'; // print how many bytes of memory an int value takes

	return 0;
}
```

Algunas implementaciones darán como resultado **2** mientras que otras darán **4**.
