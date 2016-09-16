```java
 // 人类做为父类
 class Person {
	 String name;
	 public Person(){
		 System.out.println("execute Person()");
	 }
	 public Person(String name){
		 this.name = name;
		 System.out.println("execute Person(name)");
	 }

}

 // 学生类做为Person的子类
class Student extends Person{
	String school;
	public Student(){
		System.out.println("execute Student()");
	}
	public Student(String name,String school){
		super(name);  // 显示调用父类有参构造方法，将不执行无参构造方法 
		this.school = school;
		System.out.println("execute Student(name,shcool)");
	}
}

// 研究生类作为Student的之类
class PostGraduate extends Student{
	String guide;
	
	public PostGraduate(){
		System.out.println("execute PostGraduate()");
	}
	public PostGraduate(String name,String school,String guide){
		super(name,school);
		this.guide = guide;
		
		System.out.println("execuate Postgraduate(name,school,guide)");
	}
}

class Test {
	public static void main(String[] args){
		PostGraduate b = new PostGraduate();
		System.out.println();
		PostGraduate pgdt = new PostGraduate("刘致同","北京大学","王老师");
   }
}

```
