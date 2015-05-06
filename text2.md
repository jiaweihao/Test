#include?<stdlib.h>
#include?<stdio.h>
#include?<time.h>
int?question_get();
int type;
void main(void)
{
int?answer,n;
srand((unsigned)time(NULL));
printf("\n1.加法运算\n2.减法运算\n3乘法运算\n4除法运算\n5退出运算\n");
printf("\t\t\t请选择(1-5):");
scanf("%d",&type);
while(1)
{
int temp;
int flag;
answer=?question_get();
printf("请回答：\n");
scanf("%d",&temp);
while(temp!=answer)
{
printf("\n答案错误,重做\n");
scanf("%d",&temp);
}
printf("\n答案正确,很好\n");
printf("继续请按1，退出请按0\n");
scanf("%d",&flag);
while(flag!=0&&flag!=1)
{
printf("按其它键无效\n");
scanf("%d",&flag);
}
if( flag==0)
break;
goto?loop;
}
}
int?question_get()
{
int a,b,c;
loop: if(?type==1)
{
a=rand()%99;
b=99-a;
b=rand()%b;
printf("%d?+%d?=?",a,b);
return(a+b);
}
else?if(type==2)
{
b=rand()%99;
c=99-b;
c=rand()%c;
printf("%d?-%d=?",?b+c,b);
return(c);
}
else if(type==3)
{
a=rand()%10;
b=50-a;
b=rand()%b;
printf("%d?*%d?=??",a,b);
return(a*b);
}
else?if(type==4)
{
b=rand()%50;
c=100/b;
while(1)
{
c=rand()%c;
if(c!=0)
break;
}
printf("%d/%d=??",b*c,b);
return(c);
}
else if(type==5)
{
printf("\t\t\t退出系统\n");/*结束程序*/
system("pause");
exit(0);
}
else if(type==0||type>5)
{
printf("\t\t\t输入错误，请输入1-5内的数字\n");
printf("\t\t\t请选择(1-5):");
scanf("%d",&type);
goto loop;
}
}
