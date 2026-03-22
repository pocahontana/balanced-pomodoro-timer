# balanced-pomodoro-timer
My first C# project: A cozy Pomodoro Timer to balance coding sessions and self-care. 
using System;
using System.Threading;

class lerntimer
{
    static void Main()
    {
        Console.Title = "💕Lern Workspace💕";
        Console.ForegroundColor = ConsoleColor.Magenta;

        Console.WriteLine ("🎀Mini Workspace mit Pomodoro🎀")
        Console.Write ("⏰Gib die Lernzeit ein: ")
        int minuten = int.Parse (Console.ReadLine())

        int sekunden = minuten *60;
        int pauseIntervall = 5 * 60; //alle 5min Mini Pause
        string [] sprueche = new string []

    {
        "💪🏽Kopf hoch, Krone richten!👑"
        "✨Du rockst das!✨"
        "🐌Jeder Schritt zählt!"
    };

    while (sekunden > 0)
    {
         Console.Clear();
         DateTime jetzt = DateTime.Now;

         //Echtzeituhr
         Console.ForegroundColor=
         ConsoleColor.Cyan;
         Console.WriteLine ("Uhrzeit: {0:HH:mm:ss}",jetzt);

         //Countdown
         Console.ForegroundColor = ConsoleColor.Magenta;
         Console.WriteLine ("\n🌸 Zeit übrig: {0:D2}:{1:D2}🌸",sekunden/60, sekunden%60);

         //Motivation
         Console.WriteLine("\n Motivation:" + sprueche[sekunden%sprueche.Length]);

         //Mini Pause hinweis alle 5Min
         if (sekunden % pauseIntervall==0 && sekunden !=minuten*60)
         {
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine ("\n☕️Mini-Pause! Streck dich kurz, atme tief druch!");
         }
        Thread.Sleep(1000);
        sekunden--;
    }
    Console.Clear();
    Console.ForegroundColor=ConsoleColor.Green;
    Console.WriteLine("✨Fertig!Du hast es geschafft!✨");
    Console.WriteLine("💕"+sprueche[new Random().Next(sprueche.Length)]);
    Console.WriteLine("\nDrück eine Taste zum beenden...");
    Console.ReadKey();
    }
}
