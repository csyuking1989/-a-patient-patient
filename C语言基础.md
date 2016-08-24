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
