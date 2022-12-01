using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Threading;
using static System.Net.Mime.MediaTypeNames;

namespace collect
{
    class Program
    {
        static void Main(string[] args)
        {
            //set up
            DateTime tijd = DateTime.Now;
            DateTime tijd2 = DateTime.Now;
            string buttonpressed = "no";
            Console.WindowHeight = 30;
            Console.WindowWidth = 40;
            int screenwidth = Console.WindowWidth;
            int screenheight = Console.WindowHeight;
            Random randomnummer = new Random();
            int score = 0;
            int gameover = 0;
            pixel hoofd = new pixel();
            hoofd.xpos = screenwidth / 2;
            hoofd.ypos = screenheight / 2;
            List<int> odd = new List<int>();
            odd.Add(1);
            odd.Add(3);
            odd.Add(5);
            odd.Add(7);
            odd.Add(9);
            odd.Add(11);
            odd.Add(13);
            odd.Add(15);
            odd.Add(17);
            odd.Add(19);
            odd.Add(21);
            odd.Add(23);
            odd.Add(25);
            odd.Add(27);
            odd.Add(29);
            odd.Add(31);
            odd.Add(33);
            odd.Add(35);
            odd.Add(37);
            odd.Add(39);
            List<int> even = new List<int>();
            even.Add(2);
            even.Add(4);
            even.Add(6);
            even.Add(8);
            even.Add(10);
            even.Add(12);
            even.Add(14);
            even.Add(16);
            even.Add(18);
            even.Add(20);
            even.Add(22);
            even.Add(24);
            even.Add(26);
            even.Add(28);
            even.Add(30);
            even.Add(32);
            even.Add(34);
            even.Add(36);
            even.Add(38);
            even.Add(40);
            string movement = "PAUSE";
            List<int> xposlijf = new List<int>();
            List<int> yposlijf = new List<int>();
            int berryx = randomnummer.Next(0, screenwidth);
            int berryy = randomnummer.Next(0, screenheight);
            //hurt 1
            pixel hurt = new pixel();
            int hurtx = randomnummer.Next(0, screenwidth);
            int hurty = randomnummer.Next(0, screenheight);
            hurt.xpos = hurtx;
            hurt.ypos = hurty;
            hurt.schermkleur = ConsoleColor.Blue;
            //hurt 2
            pixel hurt2 = new pixel();
            int hurtx2 = randomnummer.Next(0, screenwidth);
            int hurty2 = randomnummer.Next(0, screenheight);
            hurt2.xpos = hurtx2;
            hurt2.ypos = hurty2;
            hurt2.schermkleur = ConsoleColor.Blue;
            //side hurt 1
            pixel sHurt = new pixel();
            int sHurtx = randomnummer.Next(0, screenwidth);
            int sHurty = randomnummer.Next(0, screenheight);
            sHurt.xpos = sHurtx;
            sHurt.ypos = sHurty;
            sHurt.schermkleur = ConsoleColor.White;
            //side hurt 2
            pixel sHurt2 = new pixel();
            int sHurtx2 = randomnummer.Next(0, screenwidth);
            int sHurty2 = randomnummer.Next(0, screenheight);
            sHurt2.xpos = sHurtx2;
            sHurt2.ypos = sHurty2;
            sHurt2.schermkleur = ConsoleColor.DarkYellow;
            //side hurt 3
            pixel sHurt3 = new pixel();
            int sHurtx3 = randomnummer.Next(0, screenwidth);
            int sHurty3 = randomnummer.Next(0, screenheight);
            sHurt3.xpos = sHurtx3;
            sHurt3.ypos = sHurty3;
            sHurt3.schermkleur = ConsoleColor.DarkYellow;
            //score / gameover
            while (true)
            {
                Console.ForegroundColor = ConsoleColor.Green;
                if (berryx == hoofd.xpos && berryy == hoofd.ypos)
                {
                    score++;
                    berryx = randomnummer.Next(1, screenwidth - 2);
                    berryy = randomnummer.Next(1, screenheight - 2);
                }
                if (odd.Contains(berryx))
                {
                    berryx++;
                }
                if (even.Contains(berryy))
                {
                    berryy--;
                }
                if (even.Contains(sHurt.ypos))
                {
                    sHurt.ypos--;
                }
                if (odd.Contains(sHurt2.xpos))
                {
                    sHurt2.xpos++;
                }
                if (odd.Contains(sHurt3.xpos))
                {
                    sHurt3.xpos++;
                }
                if (gameover >= 2)
                {
                    Console.WriteLine("Game Over!\n Score: {0}", score);
                    Environment.Exit(0);
                }
                //Hurt 1
                if (hurt.xpos > hoofd.xpos)
                {
                    Task.Delay(500);
                    hurt.xpos--;
                }
                if (hurt.xpos < hoofd.xpos)
                {
                    Task.Delay(500);
                    hurt.xpos++;
                }
                if (hurt.ypos > hoofd.ypos)
                {
                    Task.Delay(500);
                    hurt.ypos--;
                }
                if (hurt.ypos < hoofd.ypos)
                {
                    Task.Delay(500);
                    hurt.ypos++;
                }
                //Hurt Damage
                if (hurt.xpos == hoofd.xpos & hurt.ypos == hoofd.ypos)
                {
                    gameover++;
                    gameover++;
                }
                //Hurt 2 Damage
                if (hurt2.xpos == hoofd.xpos & hurt2.ypos == hoofd.ypos)
                {
                    gameover++;
                    gameover++;
                }
                //Side Hurt Damage
                if (sHurt.xpos == hoofd.xpos & sHurt.ypos == hoofd.ypos)
                {
                    gameover++;
                }
                //Side Hurt 2 Damage
                if (sHurt2.xpos == hoofd.xpos & sHurt2.ypos == hoofd.ypos)
                {
                    gameover++;
                }
                //Side Hurt 3 Damage
                if (sHurt3.xpos == hoofd.xpos & sHurt3.ypos == hoofd.ypos)
                {
                    gameover++;
                }
                //Extra Lives / 3 Lives
                if (berryx == hoofd.xpos + 2 & berryy == hoofd.ypos || berryx == hoofd.xpos - 2 & berryy == hoofd.ypos || berryx == hoofd.xpos & berryy == hoofd.ypos + 2 || berryx == hoofd.xpos & berryy == hoofd.ypos - 2)
                {
                    if (gameover == -1)
                    {
                        gameover++;
                        gameover--;
                    }
                    else
                    { 
                        gameover--;
                    }
                }
                if (gameover == 1)
                {
                    hoofd.schermkleur = ConsoleColor.DarkRed;
                }
                if (gameover == 0)
                {
                    hoofd.schermkleur = ConsoleColor.Green;
                }
                if (gameover == -1)
                {
                    hoofd.schermkleur = ConsoleColor.DarkMagenta;
                }
                //Character
                Console.SetCursorPosition(hoofd.xpos, hoofd.ypos);
                Console.ForegroundColor = hoofd.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(berryx, berryy);
                Console.ForegroundColor = ConsoleColor.Cyan;
                Console.Write("■");
                Console.CursorVisible = false;
                //Hurt
                Console.SetCursorPosition(hurt.xpos, hurt.ypos);
                Console.ForegroundColor = hurt.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(berryx, berryy);
                Console.ForegroundColor = ConsoleColor.Cyan;
                Console.Write("■");
                Console.CursorVisible = false;
                //Hurt 2
                Console.SetCursorPosition(hurt2.xpos, hurt2.ypos);
                Console.ForegroundColor = hurt2.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(hurtx2, hurty2);
                Console.CursorVisible = false;
                if (hurt2.xpos > hoofd.xpos)
                {
                    Task.Delay(500);
                    hurt2.xpos--;
                }
                if (hurt2.xpos < hoofd.xpos)
                {
                    Task.Delay(500);
                    hurt2.xpos++;
                }
                if (hurt2.ypos > hoofd.ypos)
                {
                    Task.Delay(500);
                    hurt2.ypos--;
                }
                if (hurt2.ypos < hoofd.ypos)
                {
                    Task.Delay(500);
                    hurt2.ypos++;
                }
                //side hurt 1
                Console.SetCursorPosition(sHurt.xpos, sHurt.ypos);
                Console.ForegroundColor = sHurt.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(sHurtx, sHurty);
                Console.CursorVisible = false;
                if (sHurt.xpos > hoofd.xpos)
                {
                    Task.Delay(500);
                    sHurt.xpos--;
                }
                if (sHurt.xpos < hoofd.xpos)
                {
                    Task.Delay(500);
                    sHurt.xpos++;
                }
                //side hurt 2
                Console.SetCursorPosition(sHurt2.xpos, sHurt2.ypos);
                Console.ForegroundColor = sHurt2.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(sHurtx3, sHurtx3);
                Console.CursorVisible = false;
                if (sHurt2.ypos > hoofd.ypos)
                {
                    Task.Delay(500);
                    sHurt2.ypos--;
                }
                if (sHurt2.ypos < hoofd.ypos)
                {
                    Task.Delay(500);
                    sHurt2.ypos++;
                }
                //side hurt 3
                Console.SetCursorPosition(sHurt3.xpos, sHurt3.ypos);
                Console.ForegroundColor = sHurt3.schermkleur;
                Console.Write("■");
                Console.SetCursorPosition(sHurtx3, sHurtx3);
                Console.CursorVisible = false;
                if (sHurt3.ypos > hoofd.ypos)
                {
                    Task.Delay(500);
                    sHurt3.ypos--;
                }
                if (sHurt3.ypos < hoofd.ypos)
                {
                    Task.Delay(500);
                    sHurt3.ypos++;
                }
                //movement
                tijd = DateTime.Now;
                buttonpressed = "no";
                while (true)
                {
                    tijd2 = DateTime.Now;
                    if (tijd2.Subtract(tijd).TotalMilliseconds > 500) { break; }
                    if (Console.KeyAvailable)
                    {
                        ConsoleKeyInfo toets = Console.ReadKey(true);
                        if (toets.Key.Equals(ConsoleKey.UpArrow) && movement != "DOWN" && buttonpressed == "no")
                        {
                            movement = "UP";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.DownArrow) && movement != "UP" && buttonpressed == "no")
                        {
                            movement = "DOWN";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.LeftArrow) && movement != "RIGHT" && buttonpressed == "no")
                        {
                            movement = "LEFT";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.RightArrow) && movement != "LEFT" && buttonpressed == "no")
                        {
                            movement = "RIGHT";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.S) && movement != "NONE" && buttonpressed == "no")
                        {
                            movement = "NONE";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.Escape) && movement != "PAUSE" && buttonpressed == "no")
                        {
                            movement = "PAUSE";
                            buttonpressed = "yes";
                        }
                        if (toets.Key.Equals(ConsoleKey.Escape) && movement == "PAUSE" && buttonpressed == "no")
                        {
                            Console.WriteLine("Game Over!\n Score: {0}", score);
                            Environment.Exit(0);
                        }
                    }
                }
                xposlijf.Add(hoofd.xpos);
                yposlijf.Add(hoofd.ypos);
                switch (movement)
                {
                    case "UP":
                        hoofd.ypos--;
                        hoofd.ypos--;
                        break;
                    case "DOWN":
                        hoofd.ypos++;
                        hoofd.ypos++;
                        break;
                    case "LEFT":
                        hoofd.xpos--;
                        hoofd.xpos--;
                        break;
                    case "RIGHT":
                        hoofd.xpos++;
                        hoofd.xpos++;
                        break;
                    case "NONE":
                        hoofd.xpos++;
                        hoofd.xpos--;
                        hoofd.ypos++;
                        hoofd.ypos--;
                        break;
                    case "PAUSE":
                        if (hurt2.xpos > hoofd.xpos)
                        {
                            Task.Delay(500);
                            hurt2.xpos++;
                        }
                        if (hurt2.xpos < hoofd.xpos)
                        {
                            Task.Delay(500);
                            hurt2.xpos--;
                        }
                        if (hurt2.ypos > hoofd.ypos)
                        {
                            Task.Delay(500);
                            hurt2.ypos++;
                        }
                        if (hurt2.ypos < hoofd.ypos)
                        {
                            Task.Delay(500);
                            hurt2.ypos--;
                        }
                        if (hurt.xpos > hoofd.xpos)
                        {
                            Task.Delay(500);
                            hurt.xpos++;
                        }
                        if (hurt.xpos < hoofd.xpos)
                        {
                            Task.Delay(500);
                            hurt.xpos--;
                        }
                        if (hurt.ypos > hoofd.ypos)
                        {
                            Task.Delay(500);
                            hurt.ypos++;
                        }
                        if (hurt.ypos < hoofd.ypos)
                        {
                            Task.Delay(500);
                            hurt.ypos--;
                        }
                        if (sHurt.xpos > hoofd.xpos)
                        {
                            Task.Delay(500);
                            sHurt.xpos++;
                        }
                        if (sHurt.xpos < hoofd.xpos)
                        {
                            Task.Delay(500);
                            sHurt.xpos--;
                        }
                        if (sHurt2.ypos > hoofd.ypos)
                        {
                            Task.Delay(500);
                            sHurt2.ypos++;
                        }
                        if (sHurt2.ypos < hoofd.ypos)
                        {
                            Task.Delay(500);
                            sHurt2.ypos--;
                        }
                        if (sHurt3.ypos > hoofd.ypos)
                        {
                            Task.Delay(500);
                            sHurt3.ypos++;
                        }
                        if (sHurt3.ypos < hoofd.ypos)
                        {
                            Task.Delay(500);
                            sHurt3.ypos--;
                        }
                        break;
                }
                if (xposlijf.Count() > score)
                {
                    xposlijf.RemoveAt(0);
                    yposlijf.RemoveAt(0);
                }
                if (hoofd.Score == 0)
                {
                    Console.Clear();
                }
            }
            Console.WriteLine("Game Over!\n Score: {0}", score);
            int tijdd = Convert.ToInt32(tijd);
            int tijdj2 = Convert.ToInt32(tijd2);
            hoofd.Score = (tijdj2 - tijdd) / 2;
            Console.SetCursorPosition(screenwidth / 5, screenheight / 2);
            Console.SetCursorPosition(screenwidth / 5, screenheight / 2 + 1);
            //Hurt 1
            hurt.xpos = hurtx;
            hurt.ypos = hurty;
            hurt.Score = (tijdj2 - tijdd) / 2;
        }
        class pixel
        {
            public int xpos { get; set; }
            public int ypos { get; set; }
            public int Score = 0;
            public ConsoleColor schermkleur { get; set; }
        }
    }
}