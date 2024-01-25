# Tang这是一个超级代码
#include <iostream>
#include <cmath>
#define pi 3.1415926

using namespace std;
class Shape  //基类
{
public:
    Shape(){}
    virtual double getArea() = 0;
    virtual void show() = 0;
};

class Rectangle : public Shape   //矩形                                                                  ///////juxing
{
private:
    double _a;
    double _b;
public:
    Rectangle(double a = 0,double b = 0) : _a(a),_b(b)
    { _a = a;
      _b = b;
    }
    double getArea();
    void show();
};

class Square : public Shape   //正方形                                                                  //zhengfangxing
{
private:
    double _c;
public:
    Square(double c = 0) : _c(c)
    { _c = c;}
    double getArea();
    void show();
};

class Trapezoid : public Shape  //梯形                                     //////tixing
{
private:
    double _d;
    double _e;
    double _f;
public:
    Trapezoid(double d = 0,double e = 0,double f = 0) : _d(d),_e(e),_f(f)
    { _d = d;
      _e = e;
      _f = f;
    }
    double getArea();
    void show();
};

class Circle : public Shape   //圆形                                        //////yuanxing
{
private:
    double _r;
public:
    Circle(double r = 0) : _r(r)
    { _r = r;}
    double getArea();
    void show();
};

double Rectangle :: getArea(){
    double s;
    s = _a * _b;
    return s;
}
void Rectangle :: show()
{ cout << "矩形的面积为=  " << Rectangle::getArea() << endl;}

double Square :: getArea(){
    double s;
    s = _c * _c;
    return s;
}
void Square :: show()
{ cout << "正方形面积=  " << Square::getArea() << endl;}

double Trapezoid :: getArea(){
    double s;
    s = (_d + _e) * _f / 2;
    return s;
}
void Trapezoid :: show()
{ cout << "梯形面积为=  " << Trapezoid::getArea() << endl;}

double Triange ::getArea() {
    double p;
    double s;
    p = (_g + _h + _i) / 2;
    s = sqrt (p * (p - _g) * (p - _h) * (p - _i));
    return s;
}
void Triange :: show()
{ cout << "三角形面积=  " << Triange::getArea() << endl;}

double Circle ::getArea() {
    double s;
    s = pi * _r * _r;
    return s;
}
void Circle ::show()
{ cout << "圆形面积为=  " << Circle::getArea() << endl;}

int main(){
    Rectangle a(4, 7);//定义派生类对象
    Square c(3);
    Trapezoid d(2, 5, 5);
    Triange e(3, 4, 6);
    Circle b(2);

    Shape *pt[5] = {&a, &b, &c, &d, &e}; //定义基类指针数组，是=使每一个元素都只想一个派生类对象
    double areas = 0.0;
    /*Shape**p;
     for(p = pt ;p < pt + 5;++p)
     {
     (*p)->getArea();
     areas +=(*p)->getArea();}*/
    for(int i = 0;i < 5;i++)
    {
        /*pt[i]->getArea();*/
        pt[i]->show();
        cout<<endl;
        areas = areas + pt[i]->getArea();
    }
    cout << "这些图形面积总和为：" << areas << endl;
}
