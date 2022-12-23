[complex no.txt](https://github.com/temgiregayatri2458/S.E-oop-assignment/files/10291996/complex.no.txt)
# S.E-oop-assignment
/*Implement a class Complex which represents the Complex Number data type. Implement 
the following
1. Constructor (including a default constructor which creates the complex number 0+0i).
2. Overloaded operator+ to add two complex numbers.
3. Overloaded operator* to multiply two complex numbers.4. Overloaded << and >> to 
print and read Complex Numbers.*/




#include<iostream>
using namespace std;
class complex
{
	float img,real;
	public:
		complex()
		{
			real=0;
			img=0;
		}
		complex operator+(complex);
		complex operator*(complex);
		friend istream& operator>>(istream&,complex &);
		friend ostream& operator<<(ostream&,complex &);
};
complex complex::operator+(complex x)
{
	complex z;
	z.real=real+x.real;
	z.img=img+x.img;
	return z;
}
complex complex::operator*(complex x)
{
	complex z;
	z.real=(real*x.img)-(img*x.real);
	z.img=(img*x.real)+(real*x.img);
	return z;
}
istream& operator>>(istream& in,complex &x)
{
	cout<<"\nEnter the real part = ";
	in>>x.real;
	cout<<"\nEnter the img part = ";
	in>>x.img;
	return in;
}
ostream& operator<<(ostream&out,complex & x)
{
	out<<x.real;
	if(x.img>=0)
		out<<"+"<<x.real<<"i";
	else
		out<<x.real<<"i";
	return out;
}

int main()
{
	complex c1,c2,c3,c4,c5;
	
	cout<<"\nENter the first complex number = ";
	cin>>c2;
	cout<<"\nEnter the second complex number = ";
	cin>>c3;
	c4=c2+c2;
	c5=c2*c3;
	cout<<"\nDefault complex number is = ";
	cout<<c1;
	cout<<"\nFirst complex number = ";
	cout<<c2;
	cout<<"\nSecond complex number = ";
	cout<<c3;
	cout<<"\nAddition of complex number = ";
	cout<<c4;
	cout<<"\nMultiplication of complex number = ";
	cout<<c5;
	return 0;
}
