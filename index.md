/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package javaapplication1;
import java.util.Random;

/**
 *
 * @author 708739
 */
public class JavaApplication1 {

    
    
public static void main(String[] args) {
        jungle j1 = new jungle();
        j1.launch();
        System.out.println("Number of Lion winners is " + jungle.NumberOfLionWinners);
        System.out.println("Number of Tiger winners is " + jungle.NumberOfTigerWinners);
        
    }
}

// let's make a Super Class called FELINE
class Feline{
    public String name;
    public int Strength;

    public Feline(){
         Strength = SetStrength();
     }

    public int SetStrength(){
        Random rand = new Random(); 
        return rand.nextInt(100);
    }
}
 class lion extends Feline{

 }  

class tiger extends Feline{
  public tiger(){

  }
     }

class jungle {
    // these are Class Instance Variables:
    // because they are declared at the Class Level
    // here is where the TYPE is defined
    public static int NumberOfLionWinners = 0;
    public static int NumberOfTigerWinners = 0;
 

     lion LION1;
     tiger TIGER1;

     public void launch(){
         // HERE is where the OBJECT IS CREATED
            LION1 = new lion();
            TIGER1 = new tiger();
            for ( int competitionNumber = 0; competitionNumber<100; competitionNumber++ ){
                doCompetition(new lion(), new tiger());
            }

            doCompetition(LION1, TIGER1);

     }

     public void doCompetition(Feline lion, Feline tiger){

         if (lion.Strength > tiger.Strength){
             jungle.NumberOfLionWinners++;
         } else 
             {
             jungle.NumberOfTigerWinners++;
         } 
        
     }
}
