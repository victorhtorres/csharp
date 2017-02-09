# C sharp

Referencias rápidas de la sintaxis y snippet sobre el lenguaje de programación c#.

## Tabla de contenido

- [Hola Mundo en consola](#hola-mundo-en-consola).
- [Hola Mundo en GUI](#hola-mundo-en-gui).
- [Tipos de datos](#tipos-de-datos).
- [Operadores](#operadores).
- [Comentarios](#comentarios).
- [Argumentos por posición](#argumentos-por-posicion).
- [Secuencias de escape](#secuencias-de-escape).
- [Variables de tipo constante](#variables-de-tipo-constante).
- [Interpolación de cadenas](#interpolacion-de-cadenas).
- [Formato de cadenas numéricas](#formato-de-cadenas-numericas)
- [Controles de flujo](#controles-de-flujo).
 - [if-else](#if-else).
 - [Operador condicional ternario](#operador-condicional-ternario).
 - [switch](#switch).
- [Instrucciones de bucle](#instrucciones-de-bucle).
 - [For](#for).
 - [Foreach](#foreach).
 - [While y do while](#while-y-do-while).
- [Propiedades implementadas automáticamente - Getter y Setter](#propiedades-setter-y-getter-automatico).
- [Los namespaces más utilizados en .NET Framework](#los-namespaces-mas-utilizados).
- [Enumeraciones](#enumeraciones).
- [Matrices](#matrices).
 - [Matriz unidimensional](#matriz-unidimensional).
 - [Matriz Multidimensional](#matriz-multidimensional).
 - [Inicializador de matrices para un arreglo de dos dimensiones](#inicializador-de-matrices).
 - [LINQ](#linq).
- [Snippets](#snippets).
 - [Números aleatorios](#numeros-aleatorios).
- [Fuentes](#fuentes).


## Hola mundo en consola

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

## Hola Mundo en GUI

En Visual Studio > File > New > Project > Windows Form Application

![Hola Mundo en GUI](util/hola-mundo-gui.png)

- Para agregar un texto en la ventana: View > Toolbox > opción Label > arrastrar a la ventana.
- Para agregar una imagen en la ventana: View > Toolbox > opción pictureBox > arrastrar a la ventana.

Para ver las propiedades de cada opción, se debe dar clic derecho encima de cada una en la ventana GUI y podrá personalizarlo.


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

## Secuencias de escape

| Secuencia de escape | Descripción |
| ----- | ---- |
| `\n` | Nueva linea |
| `\t` | Tab |
| `\"` | Doble cita. Se utiliza para colocar un carácter de comillas dobles (") en una cadena. |
| `\n` | Retorno de carro |
| `\\` | Para poner blackslash en la cadena |

## Variables de tipo constante

En C# utiliza la palabra clave `const`. Además de const, C# proporciona la palabra clave `readonly` para declarar variables a las que se puede asignar un valor una vez en tiempo de ejecución, ya sea en la instrucción de declaración o en otra parte del constructor. Después de la inicialización, el valor de una variable readonly no puede cambiar.

## Interpolacion de cadenas

Consiste en introducir valores de variables o expresiones en el interior de cadenas.

Sintaxis:

```csharp

string nombre = "Victor";

Console.WriteLine($"Hola {nombre}!");

// Hola Victor!

```

## Formato de cadenas numericas

![Tabla de posibles formatos de cadenas numéricas](util/formato-estandar-numeros.png)

Ejemplo 1:

```csharp

decimal value = 123.456m;
Console.WriteLine(value.ToString("C2"));
// $123.46

```
Ejemplo 2:

```csharp

decimal value = 123.456m;
Console.WriteLine("Your account balance is {0:C2}.", value);
// Your account balance is $123.46.

```

## Controles de flujo

Las instrucciones de control de flujo, como if else y switch, son muy similares en Java y C#.

### if-else

Estas instrucciones son idénticas en ambos lenguajes.

Sintaxis:

```csharp

if(condición){
	// bloque de código
}


if(condición){
	// bloque de código
}else{
	// bloque de código
}


if(condición){
	// bloque de código
}else if(condición){
	// bloque de código
}else{
	// bloque de código
}

```

### Operador condicional ternario

Devuelve una de dos expresiones, dependiendo de una condición.

Sintaxis:

`condicion booleana ? acción si es verdadera : acción si es falso `

Ejemplo:

```csharp

var now = new Date();
var greeting = "Good" + ((now.getHours() > 17) ? " evening." : " day.");

```

### Switch

C# exige el uso de una instrucción break o goto al final de cada caso y, si no hay ninguna presente, el compilador produce el siguiente error: El control no puede pasar explícitamente de una etiqueta de caso a otra.

Se debe tener en cuenta que donde un caso no especifica un código para ejecutar cuando coincide ese caso, el control pasará al caso siguiente.

Ejemplo:

```csharp

static void Main(string[] args)
{
    switch (args[0])
    {
        case "copy":
            //...
            break;

        case "move":
            //...
            goto case "delete";

        case "del":
        case "remove":
        case "delete":
            //...
            break;

        default:
            //...
            break;
    }
}

```

## Instrucciones de bucle

La sintaxis y el funcionamiento de los bucles for son iguales en C# y Java.

### For

Ejemplo:

```csharp

for (int i = 0; i<=9; i++)
{
    System.Console.WriteLine(i);
}

```

### Foreach

C# introduce un nuevo tipo de bucle denominado bucle foreach. El bucle foreach permite la iteración a través de cada elemento en una clase contenedora, como una matriz, que admite la interfaz `IEnumerable`. El código siguiente muestra el uso de la instrucción foreach para obtener el contenido de una matriz:

```csharp

static void Main()
{
    string[] arr= new string[] {"Jan", "Feb", "Mar"};

    foreach (string s in arr)
    {
        System.Console.WriteLine(s);
    }
}

```

### While y do while

La sintaxis y el funcionamiento de las instrucciones while y do...while son iguales en ambos lenguajes.

Sintaxis:

```csharp

while (condition)
{
    // statements
}

```

Sintaxis:

```csharp

do
{
    // statements
}
while(condition);  // Don't forget the trailing ; in do...while loops

```

## Propiedades setter y getter automatico

Ejemplo:

```csharp

	// This class is mutable. Its data can be modified from
    // outside the class.
    class Customer
    {
        // Auto-Impl Properties for trivial get and set
        public double TotalPurchases { get; set; }
        public string Name { get; set; }
        public int CustomerID { get; set; }

        // Constructor
        public Customer(double purchases, string name, int ID)
        {
            TotalPurchases = purchases;
            Name = name;
            CustomerID = ID;
        }
        // Methods
        public string GetContactInfo() {return "ContactInfo";}
        public string GetTransactionHistory() {return "History";}

        // .. Additional methods, events, etc.
    }
    
    class Program
    {
        static void Main()
        {
            // Intialize a new object.
            Customer cust1 = new Customer ( 4987.63, "Northwind",90108 );

            //Modify a property
            cust1.TotalPurchases += 499.99;
        }
    }

```

También, puedes auto-implementar las propiedades:

```csharp

public string FirstName { get; set; } = "Jane"; 

```


Si necesitas código extra en las propiedades:

```csharp

public class Date
        {
            private int month = 7;  // Backing store

            public int Month
            {
                get
                {
                    return month;
                }
                set
                {
                    if ((value > 0) && (value < 13))
                    {
                        month = value;
                    }
                }
            }
        }

```

## Los namespaces mas utilizados

![Tabla de los namespaces más utilizados en .NET Framework](util/most-important-namespaces.png)

## Enumeraciones

La palabra clave `enum` se utiliza para declarar una enumeración, un tipo distinto que consiste en un conjunto de constantes nombradas denominadas enumerador.

Sintaxis:

```csharp

enum <nombreEnum> : <tipoBase>
 {
  <constantes>
 } 

```
- nombreEnum: Un nombre para definir el conjunto de las constantes.
- tipoBase: El tipo de valores que podrán tomar las constantes, ejemplo: int, short, byte, etc...


Ejemplo

```csharp

enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};

```

Si no se inicializa una constante, entonces arrancan desde cero.

## Matrices

Puede almacenar distintas variables del mismo tipo en una estructura de datos de matriz. Para declarar una matriz especifique el tipo de sus elementos.

### Matriz unidimensional

Sintaxis:

```csharp

type[] arrayName = new type[size];

```

### Matriz multidimensional

Sintaxis:

```csharp

type[,] arrayName = new type[size1, size2];

```

### Inicializador de matrices

Ejemplo:

```csharp

int[][] jagged = {new int[] {1, 2},
                  new int[] {3},
                  new int[] {4, 5, 6}};

```

[Gráfica donde ilustra un inicializador de matrices multidimensional](util/inicializador-matrices.png)

## LINQ

Language-Integrated Query (LINQ) es un conjunto de características presentado en Visual Studio 2008 que agrega capacidades de consulta eficaces a la sintaxis de los lenguajes C# y Visual Basic. LINQ incluye patrones estándar y de fácil aprendizaje para consultar y actualizar datos, y su tecnología se puede extender para utilizar potencialmente cualquier tipo de almacén de datos. Visual Studio incluye ensamblados de proveedores para LINQ que habilitan el uso de LINQ con colecciones de .NET Framework, bases de datos SQL Server, conjuntos de datos de ADO.NET y documentos XML.

Ejemplo:

```csharp

// LINQ to Objects using an int array.
using System;
using System.Linq;

class LINQWithSimpleTypeArray
{
   static void Main()
   {
      // create an integer array
      var values = new[] {2, 9, 5, 0, 3, 7, 1, 4, 8, 5};

      // display original values
      Console.Write("Original array:");
      foreach (var element in values)
      {
         Console.Write($" {element}");
      }

      // LINQ query that obtains values greater than 4 from the array
      var filtered =
         from value in values // data source is values
         where value > 4
         select value;

      // display filtered results
      Console.Write("\nArray values greater than 4:");
      foreach (var element in filtered)
      {
         Console.Write($" {element}");
      }

      // use orderby clause to sort original values in ascending order
      var sorted =
         from value in values // data source is values
         orderby value
         select value;

      // display sorted results
      Console.Write("\nOriginal array, sorted:");
      foreach (var element in sorted)
      {
         Console.Write($" {element}");
      }

      // sort the filtered results into descending order
      var sortFilteredResults =
         from value in filtered   // data source is LINQ query filtered
         orderby value descending
         select value;

      // display the sorted results
      Console.Write(
         "\nValues greater than 4, descending order (two queries):");
      foreach (var element in sortFilteredResults)
      {
         Console.Write($" {element}");
      }

      // filter original array and sort results in descending order
      var sortAndFilter =
         from value in values     // data source is values
         where value > 4
         orderby value descending
         select value;

      // display the filtered and sorted results
      Console.Write(
         "\nValues greater than 4, descending order (one query):");
      foreach (var element in sortAndFilter)
      {
         Console.Write($" {element}");
      }

      Console.ReadLine();
   }
}

```

Ejemplo 2:


```csharp

// Employee class with FirstName, LastName and MonthlySalary properties.
class Employee
{
   public string FirstName { get; } // read-only auto-implemented property
   public string LastName { get; } // read-only auto-implemented property
   private decimal monthlySalary; // monthly salary of employee

   // constructor initializes first name, last name and monthly salary
   public Employee(string firstName, string lastName,
      decimal monthlySalary)
   {
      FirstName = firstName;
      LastName = lastName;
      MonthlySalary = monthlySalary;
   }

   // property that gets and sets the employee's monthly salary
   public decimal MonthlySalary
   {
      get
      {
         return monthlySalary;
      }
      set
      {
         if (value >= 0M) // validate that salary is nonnegative
         {
            monthlySalary = value;
         }
      }
   }

   // return a string containing the employee's information
   public override string ToString() =>
      $"{FirstName,-10} {LastName,-10} {MonthlySalary,10:C}";
}


```

```csharp

// LINQ to Objects querying an array of Employee objects.
using System;
using System.Linq;

class LINQWithArrayOfObjects
{
   static void Main()
   {
      // initialize array of employees
      var employees = new[] {
         new Employee("Jason", "Red", 5000M),
         new Employee("Ashley", "Green", 7600M),
         new Employee("Matthew", "Indigo", 3587.5M),
         new Employee("James", "Indigo", 4700.77M),
         new Employee("Luke", "Indigo", 6200M),
         new Employee("Jason", "Blue", 3200M),
         new Employee("Wendy", "Brown", 4236.4M)};

      // display all employees
      Console.WriteLine("Original array:");
      foreach (var element in employees)
      {
         Console.WriteLine(element);
      }

      // filter a range of salaries using && in a LINQ query
      var between4K6K =
         from e in employees
         where (e.MonthlySalary >= 4000M) && (e.MonthlySalary <= 6000M)
         select e;

      // display employees making between 4000 and 6000 per month
      Console.WriteLine("\nEmployees earning in the range " +
         $"{4000:C}-{6000:C} per month:");
      foreach (var element in between4K6K)
      {
         Console.WriteLine(element);
      }

      // order the employees by last name, then first name with LINQ
      var nameSorted =
         from e in employees
         orderby e.LastName, e.FirstName
         select e;

      // header
      Console.WriteLine("\nFirst employee when sorted by name:");

      // attempt to display the first result of the above LINQ query
      if (nameSorted.Any())
      {
         Console.WriteLine(nameSorted.First());
      }
      else
      {
         Console.WriteLine("not found");
      }

      // use LINQ to select employee last names
      var lastNames =
         from e in employees
         select e.LastName;

      // use method Distinct to select unique last names
      Console.WriteLine("\nUnique employee last names:");
      foreach (var element in lastNames.Distinct())
      {
         Console.WriteLine(element);
      }

      // use LINQ to select first and last names
      var names =
         from e in employees
         select new { e.FirstName, e.LastName };

      // display full names
      Console.WriteLine("\nNames only:");
      foreach (var element in names)
      {
         Console.WriteLine(element);
      }

      Console.WriteLine();
   }
} 

```

## Snippets

Algunos pedazos de códigos reutilizables.

### Numeros aleatorios

```csharp

using System;

class RandomIntegers
{
    static void Main()
    {
        // loop 20 times
        for (int counter = 1; counter <= 20; ++counter)
        {
            // pick random integer from 1 to 6
            int number = randomNumbers.Next(1, 7);
            Console.Write($"{number} "); // display generated value
        }

        Console.WriteLine();
    }
}

```

## Fuentes

- [Csharp para desarrolladores java](https://msdn.microsoft.com/es-es/library/ms228358(v=vs.90).aspx).
- [How to program in c#](http://www.deitel.com/Books/C/VisualCHowtoProgram6e/tabid/3680/Default.aspx).