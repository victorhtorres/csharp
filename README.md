# C sharp

Referencias rápidas de la sintaxis y snippet sobre el lenguaje de programación c#.

## Tabla de contenido

- [Hola Mundo](#hola-mundo).
- [Tipos de datos](#tipos-de-datos).
- [Operadores](#operadores).
- [Comentarios](#comentarios).
- [Argumentos por posición](#argumentos-por-posicion).
- [Variables de tipo constante](#variables-de-tipo-constante).
- [Controles de flujo](#controles-de-flujo).

## Hola mundo

Hola mundo por medio de consola.

Sintaxis:

```csharp

using System;

namespace HolaMundo
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hola mundo!"); // Hola mundo!
            Console.ReadLine(); // Permite que el programa no termine, después de haber leído la linea anterior.
        }
    }
}

```

## Tipos de datos

![Tabla de tipos de datos](util/tipos-datos.png)


## Comentarios

Sintaxis:

```csharp

// Esto es un comentario de una linea.

/* Esto es un comentario
de más de una linea */

```

## Operadores

C# ofrece todos los operadores compatibles con Java aplicables, como se muestra en la tabla siguiente. Al final de la tabla, verá algunos operadores nuevos disponibles en C#, pero no en Java:

![Tabla de operadores en c#](util/operadores.png)

## Argumentos por posicion

Sintaxis:

```csharp

string cadena = "Mundo";

Console.WriteLine("Hola {0}", cadena);

// Hola Mundo

```
El {0} define la posición del argumento para reemplazarlo por el valor que tenga dicha variable.

## Variables de tipo constante

 En C# utiliza la palabra clave `const`. Además de const, C# proporciona la palabra clave `readonly` para declarar variables a las que se puede asignar un valor una vez en tiempo de ejecución, ya sea en la instrucción de declaración o en otra parte del constructor. Después de la inicialización, el valor de una variable readonly no puede cambiar.

## Controles de flujo

Las instrucciones de control de flujo, como if else y switch, son muy similares en Java y C#.

### if, else y else if

Estas instrucciones son idénticas en ambos lenguajes.

