# Contador
Programa Contador no C#

namespace Stopwhatch;
internal class Program
{
    private static void Main(string[] args)
    {
        Menu();
    }

    static void Menu()
    {
       
        Console.Clear();
        Console.WriteLine("---------------------");
        Console.WriteLine("Quanto será a contagem?");
        Console.WriteLine("S - Segundos");
        Console.WriteLine("M - Minutos");
        Console.WriteLine("0 - Sair");
        Console.WriteLine("");
        Console.WriteLine("Inserir numero e o metodo da contagem.");
        Console.WriteLine("---------------------");

        string numero = Console.ReadLine().ToLower();
        char tipo = char.Parse(numero.Substring(numero.Length - 1, 1));
        int tempo = int.Parse(numero.Substring(0, numero.Length - 1));

        int multiplicador = 1;

        if (tipo == 'm')
            multiplicador = 60;

        if (tempo == 0)
            System.Environment.Exit(0);


        Inicio();
        Start(tempo * multiplicador);
        Menu();
    }
    static void Start(int time)
    {
        int cronometro = 0;

        while (time != cronometro)
        {
            Console.Clear();
            cronometro++;
            Console.WriteLine(cronometro);
            Thread.Sleep(1000);
        }
    }

    static void Inicio()
    {
        Console.Clear();
        Console.WriteLine("Preparar...");
        Thread.Sleep(1000);
        Console.WriteLine("Apontar...");
        Thread.Sleep(1000);
        Console.WriteLine("FOGO!");
        Thread.Sleep(2000);
    }
}
