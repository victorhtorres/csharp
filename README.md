# C sharp

Referencias rápidas de la sintaxis y snippet sobre el lenguaje de programación c#.

## Tabla de contenido

- [Hola Mundo](#holamundo).
- [Tipos de datos](#tiposdedatos).
- [Comentarios](#comentarios).
- [Argumentos por posición](#argumentos-por-posicion).

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
            Console.WriteLine("Hola mundo!");
            Console.ReadLine();
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

## Argumentos por posicion

Sintaxis:

```csharp

string cadena = "Mundo";

Console.WriteLine("Hola {0}", cadena);

// salida: Hola Mundo

```
El {0} define la posición del argumento para reemplazarlo por el valor que tenga dicha variable.
