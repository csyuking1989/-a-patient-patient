#### 1. Keywords: Scanner 
```Java 
import java.util.Scanner;

public class ScanPrintInfo {
  public static void main (String[] args){
    Scanner input = new Scanner(System.in);
    System.out.println("please enter the score:");
    float score = input.nextFloat();
    System.out.println("please enter the name:");
    String name = input.next();
    System.out.println("please enter the age:");
    int age = input.nextInt();
    
    System.out.println("The best score is" + score);
    System.out.println("The winner is" + name);
    System.out.println("The winner's age is"+ age);
    } 
}
``` 
