using System;

// Definición de una clase abstracta que representa una forma geométrica
public abstract class Forma
{
    // Propiedad para almacenar el nombre de la forma
    public string Nombre { get; set; }

    // Método abstracto para calcular el área (abstracción)
    public abstract double CalcularArea();
}
// Definición de una clase derivada que hereda de la clase Forma
public class Rectangulo : Forma
{
    // Propiedades para almacenar la base y la altura del rectángulo (encapsulación)
    public double Base { get; set; }
    public double Altura { get; set; }

    // Implementación del método abstracto para calcular el área (polimorfismo)
    public override double CalcularArea()
    {
        return Base * Altura;
    }
}
// Definición de otra clase derivada que hereda de la clase Forma
public class Circulo : Forma
{
    // Propiedad para almacenar el radio del círculo (encapsulación)
    public double Radio { get; set; }

    // Implementación del método abstracto para calcular el área (polimorfismo)
    public override double CalcularArea()
    {
        return Math.PI * Math.Pow(Radio, 2);
    }
}
class Program
{
    static void Main()
    {
        // Creación de instancias de las clases Rectangulo y Circulo
        Rectangulo rectangulo = new Rectangulo { Nombre = "Rectángulo", Base = 10, Altura = 35 };
        Circulo circulo = new Circulo { Nombre = "Círculo", Radio = 4 };

        // Uso del polimorfismo para calcular el área de diferentes formas
        MostrarArea(rectangulo);
        MostrarArea(circulo);
    }
    // Método que utiliza polimorfismo para mostrar el área de cualquier forma
    static void MostrarArea(Forma forma)
    {
        Console.WriteLine($"Área del {forma.Nombre}: {forma.CalcularArea()}");
    }
}
