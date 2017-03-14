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
- [Structs](#structs).
- [Herencia y clases derivadas](#herencia-y-clases-derivadas).
- [Manejo de excepciones](#manejo-de-excepciones).
  - [Crear tus propias excepciones](#crear-excepciones).
- [CRUD de un registro con SQL Server](#crud-de-un-registro-con-sql-server).
  - [Consultar](#consultar).
  - [Crear](#crear).
  - [Modificar](#modificar).
  - [Borrar](#borrar).
- [Snippets](#snippets).
  - [Números aleatorios](#numeros-aleatorios).
  - [Login en asp.net y SQL Server](#login).
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

Ejemplo 1:

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

Ejemplo 2: Con POO.


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

Ejemplo 3: Con listas genericas

```csharp


// LINQ to Objects using a List<string>.
using System;
using System.Linq;
using System.Collections.Generic;

class LINQWithListCollection
{
   static void Main()
   {
      // populate a List of strings 
      var items = new List<string>();
      items.Add("aQua"); // add "aQua" to the end of the List
      items.Add("RusT"); // add "RusT" to the end of the List
      items.Add("yElLow"); // add "yElLow" to the end of the List
      items.Add("rEd"); // add "rEd" to the end of the List

      // display initial List
      Console.Write("items contains:");
      foreach (var item in items)
      {
         Console.Write($" {item}");
      }

      Console.WriteLine(); // output end of line

      // convert to uppercase, select those starting with "R" and sort
      var startsWithR =
         from item in items
            let uppercaseString = item.ToUpper()
            where uppercaseString.StartsWith("R")
            orderby uppercaseString
            select uppercaseString;

      // display query results
      Console.Write("results of query startsWithR:");
      foreach (var item in startsWithR)
      {
         Console.Write($" {item}");
      }

      Console.WriteLine(); // output end of line

      items.Add("rUbY"); // add "rUbY" to the end of the List      
      items.Add("SaFfRon"); // add "SaFfRon" to the end of the List

      // display initial List
      Console.Write("items contains:");
      foreach (var item in items)
      {
         Console.Write($" {item}");
      }

      Console.WriteLine(); // output end of line

      // display updated query results
      Console.Write("results of query startsWithR:");
      foreach (var item in startsWithR)
      {
         Console.Write($" {item}");
      }

      Console.WriteLine(); // output end of line
   }
}


```

## Structs

Un struct es un tipo de valor. Cuando se crea un struct, la variable a la que se asigna incluye los datos reales del struct. Cuando el struct se asigna a una nueva variable, se copia. La nueva variable y la variable original contienen por tanto dos copias independientes de los mismos datos. Los cambios realizados en una copia no afectan a la otra copia. En general, las clases se utilizan para modelar comportamiento más complejo o datos que se piensan modificar una vez creado un objeto de clase. Los structs son más adecuadas para pequeñas estructuras de datos que contienen principalmente datos que no se piensan modificar una vez creado el struct.

Cuando se realiza una llamada con el operador New sobre una clase, se asigna espacio en el montón. Sin embargo, cuando se crea una instancia de una estructura, el espacio se asigna en la pila. De esta forma, se consigue mejorar el rendimiento. Además, a diferencia de las clases, no tendrá que tratar con referencias a instancias de estructuras. Se trabaja directamente con la instancia de la estructura. Debido a esto, cuando se pasa una estructura a un método, se pasa por valor en vez de como una referencia.

**Cuando utilizar Structs**

- El tipo struct resulta adecuado para representar objetos pequeños como Point, Rectangle y Color.
- Representa lógicamente un valor único, de forma similar a los tipos primitivos (int, double, etc..).
- Tiene un tamaño de instancia inferior a 16 bytes.
- Es inmutable.
- No tiene que aplicar la conversión boxing con frecuencia.

En todos los demás casos, se debe definir los tipos como clases.

Ejemplo:

```csharp

// struct1.cs
using System;
struct SimpleStruct
{
    private int xval;
    public int X
    {
        get 
        {
            return xval;
        }
        set 
        {
            if (value < 100)
                xval = value;
        }
    }
    public void DisplayX()
    {
        Console.WriteLine("The stored value is: {0}", xval);
    }
}

class TestClass
{
    public static void Main()
    {
        SimpleStruct ss = new SimpleStruct();
        ss.X = 5;
        ss.DisplayX();
    }
}

```

Resultado: The stored value is: 5

NOTA: Un struct puede implementar interfaces, tener métodos, constructores (pero con parámetros), pero no puede heredar de otros structs o clases.

## Herencia y clases derivadas

En C#, el operador `:`, que equivale a `extends` e `implements` en Java, define la herencia e implementación de interfaces. La clase base siempre debe estar en el extremo izquierdo en la declaración de clase.

Como Java, C# no admite herencia múltiple, lo que significa que las clases no pueden heredar más de una clase. Sin embargo, se pueden utilizar interfaces para ese propósito, de la misma manera que en Java.

Ejemplo:  El código siguiente define una clase denominada CoOrds con dos variables miembro privadas x e y que representan la posición del punto. Se tiene acceso a estas variables mediante propiedades denominadas X e Y, respectivamente:

```csharp

public class CoOrds
{
    private int x, y;

    public CoOrds()  // constructor
    {
        x = 0;
        y = 0;
    }

    public int X
    {
        get { return x; }
        set { x = value; }
    }

    public int Y
    {
        get { return y; }
        set { y = value; }
    }
}

```

Luego, ColorCoOrds hereda todos los campos y métodos de la clase base, a la cual se pueden agregar nuevos campos y métodos para proporcionar características adicionales en la clase derivada, según sea necesario. En este ejemplo, se agrega un miembro privado y descriptores de acceso para agregar color a la clase:

```csharp

public class ColorCoOrds : CoOrds
{
    private System.Drawing.Color screenColor;


    public ColorCoOrds()  // constructor
    {
        screenColor = System.Drawing.Color.Red;
    }

    public System.Drawing.Color ScreenColor
    {
        get { return screenColor; }
        set { screenColor = value; }
    }
}

```

**La palabra clave base**

Se puede tener acceso a los miembros de clase base en una subclase incluso cuando los miembros de base se reemplazan en la superclase utilizando la palabra clave base. Por ejemplo, puede crear una clase derivada que contenga un método con la misma firma que la clase base. Si se precede ese método con la palabra clave new, se indica que se trata de un método totalmente nuevo que pertenece a la clase derivada. También se podría proporcionar un método para tener acceso al método original de la clase base con la palabra clave base.

Ejemplo:

```csharp

public class ColorCoOrds : CoOrds
{
    public System.Drawing.Color color;

    public ColorCoOrds() : base ()
    {
        color = System.Drawing.Color.Red;
    }

    public ColorCoOrds(int x, int y) : base (x, y)
    {
        color = System.Drawing.Color.Red;
    }
}

```

En Java, esta funcionalidad se implementa con la palabra clave `super`.

## Manejo de excepciones

Similar a java.

Ejemplo: División por cero.

```csharp


// FormatException and DivideByZeroException handlers.
using System;

class DivideByZeroExceptionHandling
{
   static void Main(string[] args)
   {
      var continueLoop = true; // determines whether to keep looping

      do
      {
         // retrieve user input and calculate quotient                   
         try
         {
            // int.Parse generates FormatException                    
            // if argument cannot be converted to an integer          
            Console.Write("Enter an integer numerator: ");
            var numerator = int.Parse(Console.ReadLine());
            Console.Write("Enter an integer denominator: ");
            var denominator = int.Parse(Console.ReadLine());

            // division generates DivideByZeroException               
            // if denominator is 0                                    
            var result = numerator / denominator;

            // display result                                         
            Console.WriteLine(
               $"\nResult: {numerator} / {denominator} = {result}");
            continueLoop = false;
         }
         catch (FormatException formatException)
         {
            Console.WriteLine($"\n{formatException.Message}");
            Console.WriteLine(
               "You must enter two integers. Please try again.\n");
         }
         catch (DivideByZeroException divideByZeroException)
         {
            Console.WriteLine($"\n{divideByZeroException.Message}");
            Console.WriteLine(
               "Zero is an invalid denominator. Please try again.\n");
         }
      } while (continueLoop);
   }
}

```

### Crear excepciones

Se recomiendan los siguientes pasos:

- Un constructor sin parámetros,
- Un constructor que recibe un argumento de cadena (el mensaje de error), y
- Un constructor que recibe un argumento string y un argumento Exception (el error y el objeto de excepción como tal).

Ejemplo: Una excepción para no recibir un valor menor o igual a cero.

```csharp

// NegativeNumberException represents exceptions caused by
// illegal operations performed on negative numbers.
using System;

public class NegativeNumberException : Exception
{
   // default constructor                                
   public NegativeNumberException()
      : base("Illegal operation for a negative number")
   {
      // empty body                                      
   }

   // constructor for customizing error message         
   public NegativeNumberException(string messageValue)
      : base(messageValue)
   {
      // empty body                                     
   }

   // constructor for customizing the exception's error
   // message and specifying the InnerException object 
   public NegativeNumberException(string messageValue, Exception inner)
      : base(messageValue, inner)
   {
      // empty body                                    
   } 
}

```

Clase con el método principal:


```csharp

// Demonstrating a user-defined exception class.
using System;

class SquareRootTest
{
   static void Main(string[] args)
   {
      var continueLoop = true;

      do
      {
         // catch any NegativeNumberException thrown
         try
         {
            Console.Write(
               "Enter a value to calculate the square root of: ");
            double inputValue = double.Parse(Console.ReadLine());
            double result = SquareRoot(inputValue);

            Console.WriteLine(
               $"The square root of {inputValue} is {result:F6}\n");
            continueLoop = false;
         }
         catch (FormatException formatException)
         {
            Console.WriteLine("\n" + formatException.Message);
            Console.WriteLine("Please enter a double value.\n");
         }
         catch (NegativeNumberException negativeNumberException)
         {
            Console.WriteLine("\n" + negativeNumberException.Message);
            Console.WriteLine("Please enter a non-negative value.\n");
         }
      } while (continueLoop);
   }

   // computes square root of parameter; throws 
   // NegativeNumberException if parameter is negative
   public static double SquareRoot(double value)
   {
      // if negative operand, throw NegativeNumberException
      if (value < 0)
      {
         throw new NegativeNumberException(
            "Square root of negative number not permitted");
      }
      else
      {
         return Math.Sqrt(value); // compute square root
      }
   }
}


```


## CRUD de un registro con SQL Server

### Consultar

```csharp

string cadenaConexion = "YOUR DATA SOURCE:";

            SqlConnection conexion = new SqlConnection(cadenaConexion);
            conexion.Open();

            SqlDataAdapter sda = new SqlDataAdapter("SELECT * FROM Your_Table", conexion);

            DataSet dsDatos = new DataSet();
            sda.Fill(dsDatos, "Persona");
		
	    // Mostrar los resultados en un GridView
            gv_result.DataSource = dsDatos;
            gv_result.DataBind();

            conexion.Close();

```

### Crear

```csharp

string cadenaConexion = "YOUR DATA SOURCE:";
string nombre;
string apellido;.

            SqlConnection conexion = new SqlConnection(cadenaConexion);
            conexion.Open();

            SqlCommand script = new SqlCommand("INSERT INTO Your_Table (Nombre, Apellido) " +
                                                $"VALUES('{nombre}', '{apellido}')", conexion)


            try
            {
                script.ExecuteNonQuery();
                conexion.Close();
            }
            catch(SqlException ex)
            {
                Console.WriteLine("Error: " + ex.Message);
                conexion.Close();
            }

```

### Modificar

```csharp

	    string cedula;
            string celular;
            string cadenaConexion = "YOUR DATA SOURCE";

            SqlConnection conexion = new SqlConnection(cadenaConexion);
            conexion.Open();

            SqlCommand script = new SqlCommand($"UPDATE Your_Table SET Celular='{cel}' WHERE Cedula='{cedula}'", conexion);

            try
            {
                script.ExecuteNonQuery();
                conexion.Close();
            }
            catch (SqlException ex)
            {
                Console.WriteLine("Error: " + ex.Message);
                conexion.Close();
            }

```

### Borrar

```csharp

	    string cedula;
            string cadenaConexion = "YOUR DATA SOURCE";

            SqlConnection conexion = new SqlConnection(cadenaConexion);
            conexion.Open();

            SqlCommand script = new SqlCommand($"DELETE FROM Your_Table WHERE Cedula='{cedula}'", conexion);

            try
            {
                script.ExecuteNonQuery();
                conexion.Close();
            }
            catch (SqlException ex)
            {
                Console.WriteLine("Error: " + ex.Message);
                conexion.Close();
            }

```

### Recorrer una tabla de la bd



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

### Login

Una forma rápida y sencilla es haciendo uso de la clase `SqlDataReader`. Ejemplo:

```csharp

// Evento del botón del login

protected void btn_accept_Click(object sender, EventArgs e)
        {
            string cadenaConexion = "Data Source=...";
            string user = txt_user.Text;
            string pass = txt_pass.Text;

            using (SqlConnection conexion = new SqlConnection(cadenaConexion))
            {
                conexion.Open();
		
                String query = $"Select Usuario, Contrasena From Usuario Where Usuario='{user}' AND Contrasena='{pass}';";
                SqlCommand command = new SqlCommand(query, conexion);

                SqlDataReader reader = command.ExecuteReader();

		// si el query fue correcto, reader debería de tener una fila de resultados, de lo contrario, no existe.
                if (reader.HasRows)
                {
		    // como el logueo fue exitoso, se redirecciona a una nueva página.
                    Response.Redirect("~/User.aspx");
                }
                else
                {
                    lbl_msgError.Text = "Error: Nombre y/o usuario incorrecto.";
                }
		
		reader.Close();
            }
	    
        }

```

## Fuentes

- [Csharp para desarrolladores java](https://msdn.microsoft.com/es-es/library/ms228358(v=vs.90).aspx).
- [How to program in c#](http://www.deitel.com/Books/C/VisualCHowtoProgram6e/tabid/3680/Default.aspx).
