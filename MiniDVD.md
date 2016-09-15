```java
import java.util.Scanner; 
// 实现新增、查看、删除、借出、归还、退出等功能； 

public class MiniDvd {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		int[] condition = new int[7];  // 0 表示借出  1表示可借 
		String[] names = new String[7];
		int[] date = new int[7];
		int[] times = new int[7]; 
		int index;
		String name="";  
		int choice;
		int a;
		// 变量初始化 
		condition[0] = 0;
		names[0] = "让子弹飞";
		date[0] = 1;
		times[0] = 15;
		do{
		System.out.println("欢迎使用迷你DVD管理器");
		System.out.println("-------------------------------");
		System.out.println("1.新增DVD");
		System.out.println("2.查看DVD");
		System.out.println("3.删除DVD");
		System.out.println("4.借出DVD");
		System.out.println("5.归还DVD");
		System.out.println("6.退出DVD"); 
		System.out.println("-------------------------------");
		
	 	System.out.print("请选择（输入功能前的序号):");
		choice = input.nextInt();
		switch(choice){
			case 1:
				System.out.println("--->新增DVD\n");
				boolean flag = false;
				
				for(int i=0;i<names.length;i++){
					if( names[i]==null){
						System.out.print("请输入需要新增DVD的名字：");
						names[i] = input.next();
						name = names[i];
						condition[i] = 1;
						times[i] = 0;
						flag = true;
						break;
					} 
				}
				if(flag==true){
					System.out.println("电影《"+name+"》添加成功！");
				} else{
					System.out.println("货架已满！");
				}
	
				break;
				
			case 2:
				System.out.println("--->查看DVD"+"\n");
				System.out.println("序号"+"\t"+"状态"+"\t"+"名称"+"\t"+"借出日期"+"\t"+"借出次数");
				for(int i=0;i<names.length;i++){
					if(names[i]!=null){
						System.out.println((i+1)+"\t"+(condition[i]==1?"可借":"已借出")+"\t"+names[i]+"\t"+(date[i]==0?"":(date[i]+"日"))+"\t"+times[i]);

					}
				}
				break;
				
			case 3:
				System.out.println("--->删除DVD\n");
				System.out.print("请输入您要删除的电影名字：");
				name = input.next();
				boolean flag3 = false;
				boolean flag4 = false;
				for(int i=0;i<names.length;i++){
					if(condition[i]==1 && names[i].equals(name)){
						names[i]=null;
						index = i;
						flag3 = true;
						for(index=i;index<names.length-1;index++){
							names[index] = names[index+1];
							condition[index] = condition[index+1];
							date[index] = date[index+1];
							times[index] = times[index+1];
						}
						names[names.length-1] = null;
				        break;
					} else if(condition[i]==0 && names[i].equals(name)){
						System.out.println("影片为借出状态，不允许删除！");
						flag4 = true;
						break;
					} 
				}
				if(flag3==true){
					System.out.println("电影《"+name+"》删除成功！");
				} else if(flag3==false && flag4==false ) {
					System.out.println("没有找到该影片，没法删除！");
					
				}
				break;
				
			case 4:
				System.out.println("--->借出DVD\n");
				System.out.println("请输入您想借的DVD名称：");
				name = input.next();
				boolean flag1 = false;
				for(int i=0;i<names.length;i++){
					if(names[i].equals(name)){
						index=i;
						System.out.println("请输入借出日期:");
						date[i] = input.nextInt();
						times[i]++;
						condition[i] = 0;
					    flag1 = true;
						break;
					} 
				}
				if(flag1==true){
					System.out.println("借出《"+name+"》成功！");
				} else {
					System.out.println("目前没有找到该影片！");
				}
				break;
				
			case 5:
				System.out.println("--->归还DVD"+"\n");
				System.out.println("请输入您要归还的DVD名称：");
				name = input.next();
				boolean flag2 = false;
				for(int i=0;i<names.length;i++){
					if(names[i].equals(name) && condition[i]==0){
						System.out.print("请输入归还日期:");
						int b = input.nextInt();
						System.out.println("归还"+name+"成功!");
						System.out.println("借出日期为："+date[i]+"日");
						System.out.println("归还日期为:"+b+"日");
						System.out.println("应付租金为(元):"+(b-date[i])+"元");
						condition[i] = 1;
						date[i] = 0;
						flag2 = true;
						break;
					} else if(condition[i]==1 && names[i].equals(name) ){
						System.out.println("该DVD没有被借出!无法进行归还操作");
					} 
				}
					if(flag2==true){
						System.out.println("影片《"+name+"》归还成功！");
					}
				break;
				
			case 6:
				System.out.println("--->退出DVD"+"\n");
				System.out.println("程序结束！再见！");
				break;
				
			default:
				System.out.println("--->输入错误");
				break;
		}
		System.out.println("-------------------------------");
		System.out.println("输入0返回");
		a = input.nextInt();
		} while(a==0);
	}
}
```
