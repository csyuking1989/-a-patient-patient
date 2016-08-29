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
#### 2. Keywords: for循环 if判断 
```c
import java.util.*; 
public class Game { 
	public static void main(String[] args){
		int a=1;
		int i=1;
		int b;
		int c=5;
		Scanner input= new Scanner(System.in);
	for(i=1;i<=5;i++){ 
		System.out.println("请输入第"+a+"次的数字:");
		b = input.nextInt();
		a++; 
		if(Math.abs(b-c)>2){ 
			System.out.println("太大啦");
		} else if(Math.abs(b-c)<=2 & Math.abs(b-c)>0) {
			System.out.println("快接近拉，继续努力！");
		} else if(Math.abs(b-c)==0) {
			System.out.println("中奖啦，恭喜!"); 
			break;
		} else { 
			System.out.println("出错！");
		} 
			
		} 
	        System.out.println("游戏结束！"); 
	        
	}
		
	}
```
