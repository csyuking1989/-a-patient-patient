#### 1. Key Word：int float char printf scanf 
```c 
# include <stdio.h>
void main() {
int age; 
float height;
char sex='m';
printf(" learning software programming\n");
printf("what's your age:");
scanf("%d",&age); // %d 对应int
printf("what's your height:"); 
scanf("%f",&height); // %f 带小数点六位数 
printf("sex %c", sex); // %c 表示一个字符  %s 表示一串字符
getchar();
getchar();
```
#### 2. 图书价格涨价12.5元，输入原价格，输出目前价格
```c
# include <stdio.h> 
void main() {
float book_price;
printf("please enter the original book price:");
scanf("%f",&book_price);
book_price+=12.5;
printf("the latest book price = %f\n",book_price); // \n 表示换行 
getchar();
getchar();
}
```
#### 3. Key words: / 与 % 区别  
```c
void main() {
int a = 10;
int b = 3;
printf("%d",a/b); // /表示除下来整数部分  %表示余数 
getchar();
} 
```

#### 4. Key words: if... else... 语句
```c
void main() {
int score;
printf("please enter the score:");
scanf("%d",&score);
if (score % 2 != 1) {
    printf("偶数");
}else{
    print ("奇数");
}
getchar();
getchar();
} 
```
#### 5. 继续练习if函数 
```c
void main() {
int a,b,sum;
printf("please enter two numbers:");
scanf("%d %d", &a,&b);
sum = a+b;
if (sum>100) {
    printf("\n 两数的和大于100\n");
}
getchar();
getchar();
}
``` 
#### 6. Keywords: && 表示且
```c
void main () {
int a,b;
printf("分别输入上机和笔试的成绩：");
scanf("%d %d", &a,&b);
if(a>=60 && b>=60){
   printf("pass");
} else {
   printf("no pass"); 
} 
getchar();
getchar();
} 
```
#### 7. Keywords: || 表示或
```c
float a,b,c;
printf("分别输入a b c 三种商品的价格：");
scanf("%f %f %f",&a, &b, &c);
if (a>50 || b>50 || c>50 || a+b+c>100) {
   printf("%f",(a+b+c)*0.85);
} else {
  printf("%f", a+b+c);
} 
getchar();
getchar();
}
```
