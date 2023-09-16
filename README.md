# learningC#
using System;

namespace GenshinImpact
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("How many primogens do you have?");
            int primogen = int.Parse(Console.ReadLine());

            if (primogen < 160)
            {
                Console.WriteLine("You do not have enough primogens. Find more on your adventures.");
                return;
            }

            while (primogen >= 160)
            {
                Console.WriteLine("Do you want to play the wishing game? (yes/no)");
                string answer = Console.ReadLine();

                if (answer.ToLower() == "yes")
                {
                    primogen -= 160;
                    Random rand = new Random();
                    int diceRoll = rand.Next(1, 7);

                    switch (diceRoll)
                    {
                        case 1:
                            Console.WriteLine("You got a common item.");
                            break;
                        case 2:
                            Console.WriteLine("You got a rare item.");
                            break;
                        case 3:
                            Console.WriteLine("You got an epic item.");
                            break;
                        case 4:
                            Console.WriteLine("You got a four-star character.");
                            break;
                        case 5:
                            Console.WriteLine("You got a five-star character.");
                            break;
                        case 6:
                            Console.WriteLine("Jackpot! You got a special item.");
                            break;
                    }

                    Console.WriteLine($"You have {primogen} primogens left.");
                }
                else
                {
                    break;
                }
            }

            Console.WriteLine("Game over. Thanks for playing!");
        }
    }
}


