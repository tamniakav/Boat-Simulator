# Boat-Simulator
Just another repository
using System;

namespace _14.Boat_Simulator
{
    class Program
    {
        static void Main(string[] args)
        {
            char firstChar = char.Parse(Console.ReadLine());
            char secondChar = char.Parse(Console.ReadLine());
            int n = int.Parse(Console.ReadLine());

            int firstInt = firstChar;
            int secondInt = secondChar;

            int firstBootMoves = 0;
            int secondBootMoves = 0;

            for (int i = 1; i <= n; i++)
            {
                if (firstBootMoves >= 50 || secondBootMoves >= 50)
                {
                    break;
                }

                string moves = Console.ReadLine();
                int evenOrOdd = i % 2;

                if (evenOrOdd == 1)
                {
                    if (moves == "UPGRADE")
                    {
                        firstInt += 3;
                        secondInt += 3;
                    }
                    else
                    {
                        if (firstBootMoves >= 50)
                        {
                            break;
                        }
                        else
                        {
                            int firstBootIndex = moves.Length;
                            firstBootMoves += firstBootIndex;
                        }
                    }
                }
                else
                {
                    if (moves == "UPGRADE")
                    {
                        firstInt += 3;
                        secondInt += 3;
                    }
                    else
                    {
                        if (secondBootMoves >= 50)
                        {
                            break;
                        }
                        else
                        {
                            int secondBootIndex = moves.Length;
                            secondBootMoves += secondBootIndex;
                        }
                    }
                }
            }

            char firstBoot = (char)firstInt;
            char secondBoot = (char)secondInt;

            if (firstBootMoves > secondBootMoves)
            {
                Console.WriteLine(firstBoot);
            }
            else
            {
                Console.WriteLine(secondBoot);
            }
        }
    }
}
