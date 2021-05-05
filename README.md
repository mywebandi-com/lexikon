# lexikon
# Konsolprojekt i Visual Studio, language: C#.
using System;
using System.IO;
using System.Text;
using System.Linq;
using System.Threading;
using System.Collections.Generic;
//using System.Text.RegularExpressions;
//using System.Threading.Tasks;
namespace Console_CS
{
    public class Individ
    {
        public string Karaktar { get; private set; }
        public string Mostaende { get; }
        public string Halsa { get; }
        public string Styrka { get; }
        public string Tur { get; }
        private Individ(string karaktarName, string mostaendeName, string individHalsa, string individStyrka,
                        string individTur)
        {
            Karaktar = karaktarName;
            Mostaende = mostaendeName;
            Halsa = individHalsa;
            Styrka = individStyrka;
            Tur = individTur;
        }
        public static Individ CreateIndivid(string karaktarName, string mostaendeName, string individHalsa, string individStyrka,
                        string individTur)
        {
            return new Individ(karaktarName, mostaendeName, individHalsa, individStyrka, individTur);
        }
    }
    class Program
    {
#pragma warning disable IDE0060 // Remove unused parameter
        static void Main(string[] args)
#pragma warning restore IDE0060 // Remove unused parameter
        {
            string[] halsa ={   "Top hälsa, grattis! ;-)",
                                "Mycke bra hälsa, gratis!.",
                                "Jette bra hälsa ”no-problem?”",
                                "Bra energi.",

                                "Nu börja problem med artros.",
                                "Hjärna = Alert! return nervös.",
                                "Save changes in your positiva sidan?.",
                                "Alert! return astma.",

                                "Diabetisk, Kolesterol liknande :-(",
                                "Akta med rökning, cancer dödar, det är inte bra!",
                                "Demens problem.",
                                "Alert! paranoid schizofren pågår.",

                                "Alert! lungor... /Covid-19?",
                                "Parkinsons sjukdom",
                                "Type Zombi liknande :-_",
                                "Alert! return Komma. ++=0"
                              };
            string[] styrka = { "Styrka = Max:  Maximal positivt styrka. ;-)",
                                "Styrka = Vice: Ateist; Andlig, ateist",
                                "Styrka = Atletisk-objektivistisk",
                                "Styrka = Den positiva sidan i fokus.",
                                "Styrka = Alert! inget negativt svar: Allt är under kontroll."
                               };
            string[] tur ={     " 0%: varken lycka till eller otur.",
                                "10%: tur i denna session.",
                                "20%: mycket att lösa ännu. Ha ett positivt dag",
                                "Tu/r = 30%: verkar som att detta aldrig sluar.",
                                "40%: imorgon är nära men svårfångad",

                                "50%: Jämställdhet mellan förlust och förstörelse, vinst och skapand.",
                                "60%; Diskutera med dig själv",
                                "70%: om du förlorar vinner och vice versa.",
                                "80%: Från och med nu är problemen andra.",
                                "90%: Från och med nu är problemen andra.",
                               "100%: Allt är under kontroll." };
            //_______________________________________________________
            bool ej_slut = true;
            //          bool NeverEnd = false;
            bool gisa;
            int left = 0;
            int right = 0;
            const string bNs = "13";
            //----------the-begin
            while (ej_slut)
            {
                DateTime dat = DateTime.Now;//  Nu är nu hela tiden.
                Console.WriteLine("\t----------------------------------------------------------------------------------------");
                Console.WriteLine("\t    NET-Programmering Förberedande kurs.                            Deltagare: Jorge.");
                Console.WriteLine("\t    HUVUD_MENY->BACKAPLAN:            REINVENT->THE_WHEEL           [ GAMMA_M0000-R ]                                                            ");
                Console.WriteLine("\t----------------------------------------------------------------------------------------");
                Console.WriteLine("\t0 - Alternativet för att stänga ner programmet.");
                Console.WriteLine("\t1 - Funktion som skriver ut ”Hello World” i konsolen");
                Console.WriteLine("\t2 - Input(Förnamn, Efternamn, Ålder) och sedan skriver ut dessa i konsolen.");
                Console.WriteLine("\t3 - Funktion som ändrar färgen på texten i konsolen");
                Console.WriteLine("\t4 - Funktion för att skriva ut dagens datum");
                Console.WriteLine("\t5 - Funktion som tar två input värden, sedan skriver ut vilket av dem som är störst");
                Console.WriteLine("\t6 - Funktion som genererar att slumpmässigt tal mellan 1 och 100.");
                Console.WriteLine("\t    Användaren ska sedan gissa talet. Gissar användaren rätt");
                Console.WriteLine("\t    så ska ett meddelande säga detta, samt hur många försök det tog.");
                Console.WriteLine("\t    Gissar användaren fel ska ett meddelande visas som informerar");
                Console.WriteLine("\t    ifall talet var för stort eller för litet.");
                Console.WriteLine("\t7 - Funktion där användaren skriver in en textrad, som sedan sparas i en fil på");
                Console.WriteLine("\t    hårddisken.");
                Console.WriteLine("\t8 - Funktion där en fil läses in från hårddisken (för enkelhetens skull kan man ");
                Console.WriteLine("\t    använda filen från uppgift 7)");
                Console.WriteLine("\t9 - Funktion där användaren skickar in ett decimaltal och");
                Console.WriteLine("\t    får tillbaka roten ur, upphöjt till 2 och upphöjt till 10.");
                Console.WriteLine("\t10- Funktion där programmet skriver ut en multiplikationstabell från 1 till 10.");
                Console.WriteLine("\t    En ”tab” ska läggas in efter varje nummer.");
                Console.WriteLine("\t    Försöka att ställa upp det så det blir relativt läsbart.");
                Console.WriteLine("\t11- Funktion som skapar två arrayer. Den första fylls med slumpmässiga tal.");
                Console.WriteLine("\t    Den andra fylls med talen från den första i stigande ordning.");
                Console.WriteLine("\t12- Funktion som tar en input från användaren och kontrollerar ifall");
                Console.WriteLine("\t    det är en palindrom alltså samma ord från båda håll, såsom Anna eller radar.");
                Console.WriteLine("\t12+1 - Funktion som tar två inputs från användaren");
                Console.WriteLine("\t       och skriver sedan ut alla siffror som är mellan de två inputsen.");
                Console.WriteLine("\t14- Funktion där användaren skickar in ett antal värden (komma-separerade siffror)");
                Console.WriteLine("\t    som sedan sorteras och skrivs ut efter udda och jämna värden.");
                Console.WriteLine("\t15- Funktion där användaren skriver in ett antal värden(komma-separerade siffor)");
                Console.WriteLine("\t    om sedan adderas och skrivs ut.");
                Console.WriteLine("\t16- Funktionen skall själv lägga till slumpmässiga värden för Hälsa, Styrka och,");
                Console.WriteLine("\t    Tur, som sparas i en instans av en klass.");
                Console.WriteLine("\t                                                                                        ");
                Console.WriteLine("\t----------------------------------------------------------------------------------------");
                Console.Write("\t   Ditt val?:");
                switch (Console.ReadLine())
                {
                    case "0":
                        ej_slut = false;
                        Console.Write("           Hej då, tack för idag,");             //   return Hej då.
                        break;
                    case "1":
                        Console.WriteLine("           ”Hello World”                  ");//   retun The World.
                        break;
                    case "2":
                        Console.Write("\t   Ditt namn och sen press Enter:? ");
                        string PersNmn = Console.ReadLine();
                        Console.Write("\t   Ditt EfterNamn och sen press Enter:? ");
                        string PersEfterNmn = Console.ReadLine();
                        Console.Write("\t   Hur gammal är du?: ");
                        string years = Console.ReadLine();
                        if (int.TryParse(years, out int hurGammal))
                            Console.WriteLine($"\t   Ditt Namn är:  " + PersNmn + " " + PersEfterNmn + " och du är " + hurGammal + " år ;-) ");
                        else { { Console.WriteLine("Unable to parse hur gammal faktis du är med input: '{0}'.", years); break; } }
                        break;
                    case "3":
                        Console.ForegroundColor =
                        Console.ForegroundColor == ConsoleColor.Gray ?
                        Console.ForegroundColor = ConsoleColor.Red ://   Randomize here!
                        Console.ForegroundColor = ConsoleColor.Gray;
                        Console.WriteLine($"\t    Din " +
                      $"Console.ForegroundColor just från och menu blir: " +
                        Console.ForegroundColor);
                        break;//Take the break here!
                    case "4":
                        {
                            Console.Write("\t   Idag är {0:d} kl {0:T}", dat);
                            Console.WriteLine(" i enlighet med Linux Data Time.");
                        }
                        break;
                    case "5":
                        {
                            Console.Write("\t   Skriv ditt nummer och tryck på Enter, tack: ");
                            string lft_str = Console.ReadLine();
                            if (int.TryParse(lft_str, out int nummer_lft)) left = nummer_lft; else { Console.WriteLine("Unable to parse '{0}'.", lft_str); break; }
                            Console.Write("\t   Skriv ditt andra nummer och tryck på Enter igen : ");
                            string rgt_str = Console.ReadLine();
                            if (int.TryParse(rgt_str, out int nummer_rgt)) right = nummer_rgt; else { Console.WriteLine("Unable to parse '{0}'.", rgt_str); break; }
                            Console.WriteLine("\t   Talet " + (
                            left >
                            right ? (
                            left.ToString() + " är större än " +
                            right.ToString()) : (
                            left ==        //     boolean scope here.
                            right ? (     //     IDE0048: Add parentheses for clarity 
                            left.ToString() + " är lika dan som " +
                            right.ToString()) :
                            right.ToString() + " är större än " +
                            left.ToString())));
                        }//  Take a break here.
                        break;
                    case "6":
                        {
                            Console.WriteLine(
                                "\t   Ang. Random objects: Gisa det slumpmässigt tal mellan " +
                                "[lower]= 0, " + "och " +
                                "[upper]= 100 ");

                            string lft = "\t   För litet tvär, försök igen! ",
                                   rgt = "\t   För stort tvär, försök igen! ",
                                   msg = "\t   Gratis, du har klarat det ";
                            string gis;
                            int g, k;
                            int counter = 0;
                            Thread.Sleep(33);
                            Random ranD0M = new((int)DateTime.Now.Ticks & 0x0000FFFF);
                            k = ranD0M.Next(1, 100);
                            //                          test k0;Functions tha not saves the constant "zero".
                            //                          Console.Write($"\t->>> " + k );
                            gisa = false;
                            while (!gisa)
                            {
                                counter++;
                                Console.Write("\t   Gisa!   ");
                                gis = Console.ReadLine();
                                if (int.TryParse(gis, out int guest)) g = guest; else { Console.WriteLine("Unable to parse '{0}'.", gis); break; }
                                if (g < k)
                                    Console.WriteLine(lft);
                                else if (g > k)
                                    Console.WriteLine(rgt);
                                else
                                {
                                    Console.WriteLine(msg += "med " +
                                                   counter + " försök!");
                                    gisa = true;
                                    break;
                                }//   ==0
                            }
                        }
                        break;
                    case "7":
                        Console.WriteLine($"\t    Skriver in en textrad, tack? ");
                        string The_Texrad_To_Save = Console.ReadLine();
                        string path = @"C:\Users\jojo\source\repos\myFile.txt"; ;
                        try
                        {
                            // Create the file, or overwrite if the file exists.
                            using FileStream fs = File.Create(path);
                            byte[] info = new UTF8Encoding(true).GetBytes(The_Texrad_To_Save);
                            // Add some information to the file.
                            fs.Write(info, 0, info.Length);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine(ex.ToString());
                        }
                        //                        Console.WriteLine($"\t    Your result: 7 ");
                        break;
                    case "8":
                        string path8 = @"C:\Users\jojo\source\repos\myFile.txt";

                        // Open the stream and read it back.
                        using (StreamReader sr = File.OpenText(path8))
                        {
                            string s8 = "";
                            while ((s8 = sr.ReadLine()) != null)
                            {
                                Console.WriteLine(s8);
                            }
                        }
                        //                        Console.WriteLine($"\t    Your result: 8 ");
                        break;
                    case "9":
                        {
                            static Double whatever(Double x) => x * x;
                            // Declare variables and then initialize to zero.
                            // Ask the user to type the first number.
                            Console.Write("\t   Ditt decimaltal, tack?: ");
                            string left_STRING = Console.ReadLine();
                            Double left_Double;
                            //__________________________________________________
                            if (Double.TryParse(left_STRING, out left_Double))
                                Console.WriteLine("\t   Sqrt = " + Math.Sqrt(left_Double));
                            else
                            { Console.WriteLine("Unable to parse '{0}'.", left_STRING); break; }
                            Console.WriteLine("\t   x^2  = " + whatever(left_Double));
                            Console.WriteLine("\t   x^10 = " + (Double)Math.Pow(left_Double, 200));
                        }
                        break;
                    case "10":
                        //    multiplikationstabell från 1 till 10.
                        Console.WriteLine($"\t   Multiplikationstabell från 1 till 10.");
                        Console.Write("\t");
                        for (int i = 1; i <= 10; i++) Console.Write("   10*" + i + "=" + (10 * i));
                        Console.WriteLine();
                        break;
                    case "11":
                        int totalt = 10;//     Optional
                        Thread.Sleep(33);
                        Random r = new((int)DateTime.Now.Ticks & 0x0000FFFF);
                        List<int> wAr = new();
                        for (int k = 1; k <= totalt; k++) wAr.Add(r.Next(1, 1000));
                        foreach (int arr in wAr) Console.Write("\t   " + arr);
                        Console.WriteLine($"\t    ");
                        wAr.Sort();//              Sortera      here!
                        foreach (int arr in wAr) Console.Write("\t   " + arr);
                        Console.WriteLine($"\t    ");// Take break here!
                        break;
                    case "12":
                        Stack<char> lftChars = new();
                        Queue<char> rgtChars = new();
                        bool palindrom = true;
                        Console.Write($"\t   Ange ett namn, tack?  ");
                        string leftName = Console.ReadLine().ToLower();
                        //                      Console.Write($"\t   Ange ett annat namn, tack?  ");    //  REVISION 2021-04-30
                        string rightName = leftName;//    Console.ReadLine();   //  ADD '//' IN LINES( 296, 297 )
                                                    //                              AND ASSUME 'string rightName = leftName;'
                        char[] LeftChars = leftName.ToCharArray();
                        char[] RightChars = rightName.ToCharArray();
                        for (int ctr = 0; ctr <      //      As    predicate
                            LeftChars.Length; ctr++)
                        {
                            lftChars.Push(
                            LeftChars[ctr]);
                            rgtChars.Enqueue(
                            RightChars[ctr]);
                        }

                        for (int ctr = 0; ctr <     //      As    predicate
                            LeftChars.Length; ctr++) if (
                            lftChars.Pop() !=
                            rgtChars.Dequeue())
                            {
                                palindrom = false; break;
                            }
                        Console.WriteLine("\t   " + (
                            palindrom ?
                           "Palindrom: Bra jobb..." :
                           "Palindom gäller ej, tvär."
                                                     ));
                        break;
                    case "12+1":
                    case bNs:
                        {
                            Console.Write("\t   Type a number, and then press Enter: ");
                            string left_str = Console.ReadLine();
                            if (!int.TryParse(left_str, out int lft))
                            {
                                Console.WriteLine("Unable to parse '{0}'.", left_str);
                                break;
                            }
                            Console.Write("\t   Type another number, and then press Enter: ");
                            string right_str = Console.ReadLine();
                            if (!int.TryParse(right_str, out int rgt))
                            {
                                Console.WriteLine("Unable to parse '{0}'.", right_str);
                                break;
                            }
                            int The_Begin = 0;
                            int The_End = 0;
                            if (rgt > lft)
                            {
                                The_Begin = lft;
                                The_End = rgt;
                            }
                            else if (lft > rgt)
                            {
                                The_Begin = rgt;
                                The_End = lft;
                            }
                            for (int counter = The_Begin + 1; counter < The_End; counter++) Console.Write($"\t   " + counter + ", ");
                            Console.WriteLine();
                        }
                        break;
                    case "14":
                        {
                            List<long> left_Arr = new();
                            List<long> right_Arr = new();
                            Console.Write($"\t   Skickar in ett antal värden (komma-separerade siffror), tack? ");
                            string s14 = Console.ReadLine();
                            string[] subs14 = s14.Split(',');
                            //                             (int k = 1; k <= subs14.Length; k++)
                            foreach (var value in subs14)
                            {
                                if (long.TryParse(value, out long x))
                                {
                                    if (x % 2 == 0)
                                        left_Arr.Add(x);
                                    else
                                        right_Arr.Add(x);
                                }
                                else Console.WriteLine("Unable to parse '{0}'.", value);
                            }
                            left_Arr.Sort();
                            right_Arr.Sort();
                            Console.Write($"\tjämna: ");// udda och jämna
                            foreach (var value in left_Arr) Console.Write("    {0}", value);
                            Console.WriteLine();
                            Console.Write($"\t udda: ");//
                            foreach (var value in right_Arr) Console.Write("    {0}", value);
                            Console.WriteLine();
                        }
                        break;
                    case "15":
                        Console.Write($"\t   Skickar in ett antal värden (komma-separerade siffror), tack? ");
                        string s = Console.ReadLine();
                        string[] subs = s.Split(',');
                        foreach (var sub in subs)
                        {
                            Console.WriteLine($"Substring: {sub}");
                        }
                        Double BX = 0;
                        foreach (var value in subs)
                        {
                            if (Double.TryParse(value, out Double x)) { BX += x; }

                            else
                                Console.WriteLine("\t   oförmögen att analysera  '{0}'.", value);
                        }
                        Console.WriteLine($"\t   totalt: " + BX);//   Acumulator Liknande  här!
                        break;
                    case "16":
                        {
                            int t00 = 15;//     Optional
                            int t01 = 5;//     Optional
                            int t10 = 10;//     Optional
                            Thread.Sleep(33);
                            Random r0 = new((int)DateTime.Now.Ticks & 0x0000FFFF);
                            Queue<int> kAr = new();
                            kAr.Enqueue(r0.Next(0, t00));
                            kAr.Enqueue(r0.Next(0, t01));
                            kAr.Enqueue(r0.Next(0, t10));
                            Console.Write($"\t   Ange namnet på sin karaktär, tack?  ");
                            string karakterize = Console.ReadLine();
                            Console.Write($"\t   Ange namnet på en motståndare, tack?  ");
                            string mostaendarize = Console.ReadLine();
                            var l0000 = from whatever in Enumerable.Range(0, 1)
                                        select Individ.CreateIndivid(
                                            karakterize,
                                            mostaendarize,
                                            halsa[kAr.Dequeue()],
                                            styrka[kAr.Dequeue()],
                                            tur[kAr.Dequeue()]
                                                                    );
                            var l0001 = l0000.ToList();
                            foreach (var individuo in l0001)
                            {
                                Console.WriteLine($"\t   " + "Din karäktar:  {0}, din motståndare: {1}",
                                                                     individuo.Karaktar,
                                                                     individuo.Mostaende);
                                Console.WriteLine($"\t   Hälsa  :" + individuo.Halsa);
                                Console.WriteLine($"\t   Styrka :" + individuo.Styrka);
                                Console.WriteLine($"\t   Tur    :" + individuo.Tur);
                                Console.WriteLine("\t----------------------------------------------------------------------------------------");
                            }
                        }
                        break;
                    default:
                        Console.WriteLine($"\t   Tillämpas ej tvär. Försök igen.");
                        break;
                }
                // Wait for the user to respond before closing.
                //  if   ( ej_slut )
                Console.Write(ej_slut ? $"\t   Tryck på valfri knapp till Backa-Plan" : $"\tJojo");
                Console.ReadKey();
                Console.Clear();
            }
        }
    }
}
