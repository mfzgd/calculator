#include<stdio.h>
#include<iostream>
#include<math.h>
#include<stdlib.h>
using namespace std;
class Base{
protected:
    double a;
    double b;
public:
	virtual	void print(){}
    Base( double a=0,double b=0)
    {
	   this->a=a;
	   this->b=b;
    }
};

class Add:public Base{
public:
	void print(){double c=a+b;printf("%.1lf",c);system("pause");}
    Add( double a,double b):Base(a,b){}
};

class Reduce:public Base{
public:
	void print(){double c=a-b;printf("%.1lf",c);system("pause");}
    Reduce( double a,double b):Base(a,b){}
};
class Ride:public Base{
public:
	void print(){double c=a*b;printf("%.1lf",c);system("pause");}
    Ride( double a,double b):Base(a,b){}
};

class Div:public Base{
public:
	void print(){double c=a/b;printf("%.1lf",c);system("pause");}
    Div( double a,double b):Base(a,b){}
};
class Squ:public Base{
public:
	void print(){double c=a*a;printf("%.1lf",c);system("pause");}
    Squ( double a):Base(a){}
};

class Root:public Base{
public:
	void print(){double c=sqrt(a);printf("%.1lf",c);system("pause");}
    Root( double a):Base(a){}
};

class Sin:public Base{
public:
	void print(){double c=sin((a/180)*3.14);printf("%.1lf",c);system("pause");}
    Sin( double a):Base(a){}
};
class Cos:public Base{
public:
	void print(){double c=cos((a/180)*3.14);printf("%.1lf",c);system("pause");}
    Cos( double a):Base(a){}
};

class Tan:public Base{
public:
	void print(){double c=tan((a/180)*3.14);printf("%.1lf",c);system("pause");}
    Tan( double a):Base(a){}
};

class Rejz:public Base{
	double c;
public:
	void print(){printf("%.3lf",c);system("pause");}
    Rejz( double a):Base(a){
	  double c1=0;
	  int b1=a;
	  double b2=a-b1;
	  double i=10,j=1;
	  while(1){
			if(b1%2==1)
			{
				c1+=1*j;
			}
		b1=b1/2;
		if(b1==0)
		{
		   break;
		}
		j=j*10;
	 }
	 while(1){
		b2=b2*2;
		if(b2>=1)
			{
				c1+=1/i;
			}
		if(i==1000)
		{
		  break;
		}
		i=i*10;
	  }
		c=c1;
    }
};

int main(){
     double a=0,b=0;
	 char x;
	 while(1)
		 {
		system("cls"); // 清屏
		printf("* * * * * * 功能表 * * * * **\n");
		printf("*         a. 加法           *\n");
		printf("*         b. 减法           *\n");
		printf("*         c. 乘法           *\n");
		printf("*         d. 除法           *\n");
		printf("*         e. 平方           *\n");
		printf("*         f. 开方           *\n");
		printf("*         g. sin            *\n");
		printf("*         h. cos            *\n");
     	printf("*         i. tan            *\n");
    	printf("*         j. 转二进制       *\n");
		printf("*         k. 退出           *\n");
		printf("* 请输入所选功能前字母(a~k) *     \n");
		printf("* * * * * * * * * * * * * * *\n");
		x=getchar();
		system("cls");
	    if(x=='k') {
			printf("已退出！\n");
			break;
		}
		else switch(x){
		     case 'a': {printf("      请输入数据'x y'来得到x+y     \n");cin>>a>>b;Add a1(a,b);a1.print();};break;
		     case 'b': {printf("      请输入数据'x y'来得到x-y     \n");cin>>a>>b;Reduce a1(a,b);a1.print();};break;
		     case 'c': {printf("      请输入数据'x y'来得到x*y     \n");cin>>a>>b;Ride a1(a,b);a1.print();};break;
		     case 'd': {printf("      请输入数据'x y'来得到x/y     \n");cin>>a>>b;Div a1(a,b);a1.print();};break;
		     case 'e': {printf("      请输入数据'x'来得到x的平方     \n");cin>>a;Squ a1(a);a1.print();}; break;
		     case 'f': {printf("      请输入数据'x'来得到x的开方     \n");cin>>a;Root a1(a);a1.print();}; break;
		     case 'g': {printf("      请输入数据'x'来得到sin(x°)     \n");cin>>a;Sin a1(a);a1.print();}; break;
		     case 'h': {printf("      请输入数据'x'来得到cos(x°)     \n");cin>>a;Cos a1(a);a1.print();}; break;
		     case 'i': {printf("      请输入数据'x'来得到tan(x°)     \n");cin>>a;Tan a1(a);a1.print();}; break;
		     case 'j': {printf("      请输入数据'x'来得到x的二进制     \n");cin>>a;Rejz a1(a);a1.print();}; break;
		}
	}
	return 0;
}
