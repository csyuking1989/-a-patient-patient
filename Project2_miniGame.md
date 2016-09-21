```java
// 这是一个user类  
import java.util.Scanner;   

public class User {
	Scanner input = new Scanner(System.in);
	private String name;
	private double score;
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public double getScore() {
		return score;
	}
	public void setScore(double score) {
		this.score = score;
	}

	public int showFist(){
		System.out.print("你出拳:1.剪刀 2.石头 3.布 (请选择相应数字):");
		int a = input.nextInt();
		if(a==1){
			System.out.println("你出拳：剪刀");
		}else if(a==2){
			System.out.println("你出拳:石头");
		} else if(a==3){
			System.out.println("你出拳：布");
		} else {
			System.out.println("你输入信息有误，请输入准确信息");
		}
		 return a;
	}
}

```

```java
// 这是一个Computer类 
public class Computer {
	private double score;
	private String name;
	
	
	public double getScore() {
		return score;
	}

	public void setScore(double score) {
		this.score = score;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int showFist(){
		int a ;
		a =(int)( Math.random()*3)+1;
		if(a==1){
			System.out.println("电脑出拳:剪刀");
		} else if(a==2){
			System.out.println("电脑出拳:石头");
		} else{
			System.out.println("电脑出拳:布");
		}
		
		return a;
	}
	

}

```

```java
// 这是一个Game类
import java.util.Scanner;


public class Game {
	int count;// 对战次数 
	int countWin=0;
	int countLose=0;
	int a;
	private User user;
	private Computer computer;
	String answer;
	String name;
	
	Scanner input = new Scanner(System.in);
	public void initial(){
		System.out.println("***************欢迎进入人机猜拳游戏***************");
		System.out.println("**********游戏开始**********\n");
		System.out.println("出拳规则：1.剪刀 2.石头 3.布");
		System.out.print("请选择对方角色(1.刘备 2.孙权3.曹操):");
		count = 0;
		a = input.nextInt();
		if(a==1){
			System.out.println("你选择了刘备对战");
		} else if(a==2){
			System.out.println("你选择了孙权对战");
		} else if(a==3){
			System.out.println("你选择了曹操对战");
		} else {
			System.out.println("你输入正确信息");
		}
	}
	public void startWar(){
		System.out.print("要开始吗?(y/n)");
		String answer = input.next();
		System.out.print("请给自己取个名字吧:");
		name = input.next();
		while(answer.equals("y")){
			user = new User();
			computer = new Computer();
			int b0 = user.showFist();
			int b1 = computer.showFist();
			count++;
			if(b0==b1){
				System.out.println("平手");
			} else if(b0==1 && b1==2){
				System.out.println("你输啦");
				countLose++;
			} else if(b0==1 && b1==3) {
				System.out.println("你赢啦");
				countWin++;
			}else if(b0==2 && b1==1){
				System.out.println("你赢啦");
				countWin++;
			} else if(b0==2 && b1==3){
				System.out.println("你输啦");
				countLose++;
			} else if(b0==3 && b1==1){
				System.out.println("你输啦");
				countLose++;
			} else {
				System.out.println("你赢啦");
				countWin++;
			}
			System.out.print("还要继续玩吗?(y/n)");
			answer = input.next();
		}	
	}
	public void showResult(){
		user = new User();
		computer = new Computer();
		if(a==1){
			computer.setName("刘备");
		} else if(a==2){
			computer.setName("孙权");
		}else if(a==3){
			computer.setName("曹操");
	    }
		user.setName(name);
		System.out.println(a);
		System.out.println(computer.getName()+"VS"+user.getName());
		System.out.println("对战次数:"+count);
		if(countWin==countLose){
			System.out.println("你们战平！");
		} else if(countWin>countLose){
			System.out.println("你赢了："+countWin+"次,"+"输了:"+countLose+"次;"+"\n结果是你赢了");
		} else if(countWin<countLose){
			System.out.println("你赢了："+countWin+"次,"+"输了:"+countLose+"次;"+"\n结果是你输了");
		}
		
		
	}
}

```

```java
// 调用类

public class GameTest {
	public static void main(String[] args) {
		Game game = new Game();
		game.initial();
		game.startWar();
		game.showResult();
	}
}

```
