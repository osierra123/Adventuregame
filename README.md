# Adventuregame
using System;
using System.Threading;

namespace Adventure_game
{
    class Adeventuregame 
    {
        static void Main() 
        {
            gameTitle();
            first();
        }

        public static void gameTitle()
        {
            Console.WriteLine("The fall of Olympus");
            Console.WriteLine("Press 'Enter' to begin");
            Console.ReadLine();
            Console.Clear();
        }

        public static void first()
        {
            string choice;

            Console.WriteLine("The day starts off with you traning outside. You hear a voice calling you.");
            Console.WriteLine("What do you do?");
            Console.WriteLine("1. ignore it");
            Console.WriteLine("2. Go to where the voice is calling you");
            Console.WriteLine("3. pause and think ");
            Console.Write("Choice: ");
            choice = Console.ReadLine().ToLower();
            Console.Clear();
            // Had tutor help me wih this part
            switch (choice)
            {
                case "1":
                case "ignore it":
                case "ignore":
                    {
                        Console.WriteLine(" You decide to ignore the voice.");
                        Console.WriteLine("You choose to go back into tranning.");
                        Console.WriteLine("As you keep on training for hours. ");
                        Console.WriteLine("You end up forgeting about the voice and decide to go back home.");
                        Console.WriteLine("Press 'Enter' to continue");
                        Console.ReadLine();
                        GameOver(); 
                        break;
                         
                    }
                    case "2":
                    case " Go to where the voice is calling you":
                case "go":
                    {
                        Console.WriteLine(" You decide to go to where the voice is calling you.");
                        Console.WriteLine("Your met with an unfamiliar person you've never seen before. He tells you he was sent by the gods to give you a message.");
                        Console.WriteLine("Press 'Enter' to continue.");
                        Console.ReadLine();
                        second();
                        break; 
                    }
                case "3":
                case "pause and think":
                case "pause": 
                    {
                        Console.WriteLine("You decide to just stop what your doing and think for a moment.");
                        Console.WriteLine(" As you were lost in thought you completely forgot about the voice. Afterwards you just decided to go home since it became very late.");
                        Console.WriteLine("Press 'Enter' to continue.");
                        Console.ReadLine();
                        GameOver();
                         break;
                    }
                default:
                    {
                        Console.WriteLine("I dont understand that command.....");
                        Console.WriteLine("Press 'Enter' to try again.");
                       Console.ReadLine();
                        first();
                        break;
                    }

            }

        }
        
        // tutor helped me with this part too
        public static void second()
        {
            Random rnd = new Random();
             string[] secoptions = {" You question the messenger if he was sent by the gods. He assures you is he by showing the symbol of olympus.," +
                    "He tells you his name is Hermes and he is here to deilver you a message.," +
                    "He tells you that you have been task to save olympus from the titans. Since they seek the destruction of olympus. "};
            int RandomNumber = rnd.Next(0, 3);
            string secText = secoptions [RandomNumber];  
            
            string secChoice;
            
            Console.WriteLine(secText);
            Console.WriteLine("Do you trust him and go along with what he is saying; Yes or No");
            Console.WriteLine("choice: ");
            secChoice = Console.ReadLine().ToLower();
            //up to here 
            if (secChoice == "yes" || secChoice == "y" )
            {
                third();
            }
            else if (secChoice == "no" || secChoice == "n")
            {
                Console.WriteLine("You decide not to trust what he is saying and decide to go home. You choose to forget about the whole thing and carrying on with your life.");
                Console.WriteLine("Press 'Enter' to continue.");
                Console.ReadLine();
                GameOver();

            }
            else
            {
                Console.WriteLine("I dont understand that command.....");
                Console.WriteLine("Press 'Enter' to try again.");
                Console.ReadLine();
                second();  
            }
        }

        public static void third() 
        {
            

            Console.WriteLine("You decide to trust him and hear what he has to say.");
            Console.WriteLine("He says you have about 3 months to save olympus from destruction.");
            Console.WriteLine("We hope your able to become a great warrior by then. To defeat the great titans and save olympus.");
            Console.ReadLine();
            
        }

        public static void GameOver() 
        {
            Console.Clear();
            Console.WriteLine("Next time choose a better option.");
            Console.WriteLine("Better luck next time.");
            Console.WriteLine("Press 'Enter' to try again.");
            Console.ReadLine();
            Console.Clear();
            gameTitle(); 
        }
        
        public static void Youwin() 
        {
            Console.Clear(); 
        }


        
    }
}
