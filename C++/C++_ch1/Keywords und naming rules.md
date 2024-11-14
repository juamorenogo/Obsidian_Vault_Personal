2024-10-01 18:18

Tags: #C

Para la version _C++23_ se reservan 92 palabras _keywords_ que cumplen con alguna función especifica. La lista de estas palabras es:

| Palabra clave     | Descripción                                                                                       |
| ----------------- | ------------------------------------------------------------------------------------------------- |
| alignas           | Especifica el alineamiento de un tipo de dato o variable.                                         |
| alignof           | Devuelve el requisito de alineación de un tipo.                                                   |
| and               | Operador lógico "y" (equivalente a `&&`).                                                         |
| and_eq            | Operador compuesto "y igual" (equivalente a `&=`).                                                |
| asm               | Inserta código ensamblador en un programa C++.                                                    |
| auto              | Deducción automática del tipo de una variable.                                                    |
| bitand            | Operador "y" a nivel de bits (equivalente a `&`).                                                 |
| bitor             | Operador "o" a nivel de bits (equivalente a '\|')                                                 |
| bool              | Tipo de dato booleano (`true` o `false`).                                                         |
| break             | Interrumpe el ciclo o estructura de control más interna.                                          |
| case              | Define una etiqueta en una sentencia `switch`.                                                    |
| catch             | Captura excepciones lanzadas por un `throw`.                                                      |
| char              | Tipo de dato de carácter de un byte.                                                              |
| char8_t (C++20)   | Tipo de dato para caracteres UTF-8.                                                               |
| char16_t          | Tipo de dato para caracteres UTF-16.                                                              |
| char32_t          | Tipo de dato para caracteres UTF-32.                                                              |
| class             | Define una clase.                                                                                 |
| compl             | Operador de complemento a nivel de bits (equivalente a `~`).                                      |
| concept (C++20)   | Define un concepto para restricciones en plantillas (templates).                                  |
| const             | Especifica que una variable o función es constante.                                               |
| consteval (C++20) | Fuerza que una función se evalúe en tiempo de compilación.                                        |
| constexpr         | Especifica que una expresión puede evaluarse en tiempo de compilación.                            |
| constinit (C++20) | Indica que la variable debe ser inicializada en tiempo de compilación.                            |
| const_cast        | Realiza un cast para remover o agregar `const` a un tipo.                                         |
| continue          | Salta a la siguiente iteración de un bucle.                                                       |
| co_await (C++20)  | Suspende una coroutine hasta que una tarea esté lista.                                            |
| co_return (C++20) | Finaliza una coroutine devolviendo un valor.                                                      |
| co_yield (C++20)  | Suspende una coroutine y produce un valor intermedio.                                             |
| decltype          | Deduce el tipo de una expresión.                                                                  |
| default           | Proporciona una implementación predeterminada de un constructor o método.                         |
| delete            | Destruye un objeto previamente creado con `new`.                                                  |
| do                | Inicia un bucle `do-while`.                                                                       |
| double            | Tipo de dato de coma flotante de doble precisión.                                                 |
| dynamic_cast      | Realiza un cast dinámico en tiempo de ejecución.                                                  |
| else              | Define una alternativa para una sentencia `if`.                                                   |
| enum              | Define un tipo enumerado.                                                                         |
| explicit          | Especifica que un constructor o conversión no se puede invocar implícitamente.                    |
| export            | Permite la exportación de plantillas (poco utilizado).                                            |
| extern            | Declara una variable o función que está definida en otro lugar.                                   |
| false             | Literal booleano para el valor falso.                                                             |
| float             | Tipo de dato de coma flotante de precisión simple.                                                |
| for               | Inicia un bucle `for`.                                                                            |
| friend            | Permite que otra clase o función acceda a los miembros privados o protegidos.                     |
| goto              | Transfiere el control a una etiqueta.                                                             |
| if                | Evalúa una expresión y ejecuta un bloque de código si es verdadera.                               |
| inline            | Sugiere al compilador que inserte el código de la función en su lugar.                            |
| int               | Tipo de dato entero.                                                                              |
| long              | Tipo de dato entero de mayor tamaño que `int`.                                                    |
| mutable           | Permite modificar miembros en una clase marcada como `const`.                                     |
| namespace         | Define un espacio de nombres para evitar colisiones de nombres.                                   |
| new               | Asigna memoria dinámicamente en el montón.                                                        |
| noexcept          | Indica que una función no lanza excepciones.                                                      |
| not               | Operador lógico "no" (equivalente a `!`).                                                         |
| not_eq            | Operador de desigualdad (equivalente a `!=`).                                                     |
| nullptr           | Literal para representar un puntero nulo.                                                         |
| operator          | Define o sobrecarga un operador.                                                                  |
| or                | Operador lógico "o" (equivalente a '\|\|').                                                       |
| or_eq             | Operador compuesto "o igual" (equivalente a '=').                                                 |
| private           | Especifica miembros privados de una clase.                                                        |
| protected         | Especifica miembros protegidos de una clase.                                                      |
| public            | Especifica miembros públicos de una clase.                                                        |
| register          | Sugiere almacenar la variable en un registro de la CPU (obsoleto).                                |
| reinterpret_cast  | Realiza un cast de tipos sin comprobar compatibilidad.                                            |
| requires (C++20)  | Especifica restricciones para una plantilla basada en conceptos.                                  |
| return            | Finaliza una función y devuelve un valor.                                                         |
| short             | Tipo de dato entero más pequeño que `int`.                                                        |
| signed            | Especifica que una variable entera puede contener valores negativos.                              |
| sizeof            | Devuelve el tamaño en bytes de un tipo o variable.                                                |
| static            | Especifica que una variable o función tiene duración de vida estática.                            |
| static_assert     | Realiza una verificación en tiempo de compilación.                                                |
| static_cast       | Realiza un cast entre tipos de manera segura en tiempo de compilación.                            |
| struct            | Define una estructura.                                                                            |
| switch            | Inicia una estructura de control de selección múltiple.                                           |
| template          | Define una plantilla de clase o función.                                                          |
| this              | Puntero que refiere al objeto actual.                                                             |
| thread_local      | Especifica que una variable es local a un hilo de ejecución.                                      |
| throw             | Lanza una excepción.                                                                              |
| true              | Literal booleano para el valor verdadero.                                                         |
| try               | Inicia un bloque de código para manejo de excepciones.                                            |
| typedef           | Define un alias para un tipo de dato.                                                             |
| typeid            | Proporciona información sobre el tipo en tiempo de ejecución.                                     |
| typename          | Especifica que un identificador es un tipo en plantillas.                                         |
| union             | Define una unión, donde todos los miembros comparten la misma ubicación en memoria.               |
| unsigned          | Especifica que una variable entera solo puede contener valores positivos.                         |
| using             | Introduce un nombre en un espacio de nombres o un alias de tipo.                                  |
| virtual           | Especifica que una función puede ser sobrescrita por una clase derivada.                          |
| void              | Indica que una función no retorna ningún valor o un puntero sin tipo.                             |
| volatile          | Indica que una variable puede ser modificada en cualquier momento fuera del control del programa. |
| wchar_t           | Tipo de dato para caracteres anchos (generalmente 16 o 32 bits).                                  |
| while             | Inicia un bucle basado en una condición.                                                          |
| xor               | Operador lógico "o exclusivo" (equivalente a `^`).                                                |
| xor_eq            | Operador compuesto "o exclusivo igual" (equivalente a `^=`).                                      |

A su vez se tienen _override_, _final_, _import_,  y _module_ como identificadores, no obstante, no soy keywords. 

Para el nombramiento de _funciones / variables, etc..._ Se requiere cumplir las siguientes condiciones:

- The identifier can not be a keyword. Keywords are reserved.
- The identifier can only be composed of letters (lower or upper case), numbers, and the underscore character. That means the name can not contain symbols (except the underscore) nor whitespace (spaces or tabs).
- The identifier must begin with a letter (lower or upper case) or an underscore. It can not start with a number.
- C++ is case sensitive, and thus distinguishes between lower and upper case letters. `nvalue` is different than `nValue` is different than `NVALUE`.
