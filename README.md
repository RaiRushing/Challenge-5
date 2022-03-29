# Challenge-5
Class project
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package challenge5;

import java.util.Scanner;

/**
 *
 * @author doria
 */
public class Challenge5 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Scanner keyboard = new Scanner(System.in); 
        String repeat = "Yes";
//        char JavaCharArray[];
        do{
        //ASk user for a word and store it in before
        System.out.println("FEED ME A WORD (containing the letter x)!!");
        String before = keyboard.nextLine();  //replace this wit a variable that was user input
        System.out.println("Before recursion: " + before);
        String after =  transform(before);       
        System.out.println("After recursion: " + after);
        System.out.println("Anymore words???");
        repeat = keyboard.nextLine();
            //keyboard.nextLine();
        }while (repeat.equalsIgnoreCase("yes"));
        
    }
    
    public static String transform(String word) 
    {
       
//        for (int i = 0; i <word.length(); i++)
//        {
//            array[i] = char.At(word);
//            if (array[i] = "x")
//            {
//                array[i] = "y";
//            }
//        }
     
        if (word.length() == 0)
        {
            //no more calls to transform
            //return something
            return word;
        }
        else if(word.charAt(0) == 'x')
        {
            //replace x with y
            word = word.replace("x", "y");
            
            //take the letter + call transform again with a shorter word
            return word + transform(word.substring(1));           
          
            
        }
        else
        {
            //leave the letter alone
            //take the letter + call transform again with a shorter word
            return word.charAt(0)+transform(word.substring(1));
        }
        
    }
    
}
