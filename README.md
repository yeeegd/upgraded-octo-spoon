#include<iomanip>
#include<iostream>
#include<fstream>
using namespace std;
#include<stdlib.h>
class Employ//基类-雇员类
{
protected:
          int num;//工号 
    char name[10];
    char sex;
    int age;
    int wage;
public:
virtual void set()=0;
virtual void print()=0;
virtual void reserved()=0;

};

class Manager:public Employ//经理类
{
public:
    void set();
    void print();
void reserved();
};

class Salesman:public Employ//销售员类
{
protected:
int salesvolume;
int snum;
public:
    void set();
    void print();
void reserved();
void printinfor();
int getsales()
{return salesvolume;}
int getsnum()
{return snum;}
};


class MarketMan:public Manager//销售经理类
{
protected:
int salesvolume;
public: 
    void set();
    void print();
void reserved();
    int resetwage();
int getnum()
{return num;}
char*getname()
{return name;}
int getamount(Salesman s[],int n)
{
salesvolume=0;
for(int i=0;i<n;i++)
{if(s[i].getsnum()==num)
salesvolume+=s[i].getsales();}
return salesvolume;
}
};
