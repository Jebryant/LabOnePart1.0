# LabOnePart1.0
    using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp1
{
    class Program
    {
       
           
            static void Main(string[] args)
            {
            //Prompt the user to enter 2 numbers
                Console.WriteLine("Welcome to My Application, \n " +
                    "Please input two different integers with the same amount of digits:");

                string num1 = Console.ReadLine();// Get input from user
                string num2 = Console.ReadLine(); // readline reads strings

                // Read the inputs from the user
                // Create new function and call method 
                Console.WriteLine(ReturnAnswer(num1, num2).ToString());// convert numbers into string for easy validation
                Console.ReadLine();
            }

            // call  function just created^ (string converison)
            public static bool ReturnAnswer(string num_x, string num_z)
            {
                // test to see if user inputted the same amount of digits
                if (num_x.Length != num_z.Length)
                {
                    // Print error message and  print false 
                    Console.WriteLine("The numbers that you have entered are not the same length \n" +
                        "Please input numbers that has the same legnth");
                    return false;

                }

                // create loop to check 
                for (int i = 0; i < num_x.Length - 1; i++)
                {
                    int value1 = (int)Char.GetNumericValue(num_x[i]) + (int)Char.GetNumericValue(num_z[i]);
                    int value2 = (int)Char.GetNumericValue(num_x[i + 1]) + (int)Char.GetNumericValue(num_z[i + 1]);

                    // If the expression do not match
                    if (value1 != value2)
                    {

                        return false;

                    }
                   
                }

               
                return true;
            }
        }
    }

