/*Реализовать структуру или класс для работы с комплексными числами
и программу с примером работы этой структуры. В структуре должны быть
перегружены арифметика для комплексных и вещественных чисел, сравнения
и определены методы для получения / изменения вещественной и мнимой части,
взятия модуля и сопряжения.
*/

#include <iostream>
#include <cmath>

using namespace std;

class Complex
{
private:
	double re_, im_; // вещественная и мнимая части

public:
	
	Complex()
	{
		re_ = 0;
		im_ = 0;
	};

		Complex(const Complex &c)
	{
		re_ = c.re_;
		im_ = c.im_;
	}

	Complex(double re)
	{
		re_ = re;
		im_ = 0;
	}

	Complex(double re, double im)
	{
		re_ = re;
		im_ = im;
	}

	
	~Complex()
	{
	}

	
	Complex& operator = (Complex &c)
	{
		re_ = c.re_;
		im_ = c.im_;

		return (*this);
	}

	
	Complex& operator = (double re)
	{
		re_ = re;
		im_ = 0;
		return (*this);
	}


	
	Complex operator + (const Complex &c)
	{
		return Complex(re_ + c.re_, im_ + c.im_);
	}

		Complex operator + (double re)
	{
		return Complex(re_ + re, im_);
	}

	
	Complex& operator += (Complex &c)
	{
		re_ += c.re_;
		im_ += c.im_;
		return *this;
	}

	
	Complex& operator += (double re)
	{
		re_ += re;
		return *this;
	}

	
	Complex operator - (const Complex &c)
	{
		return Complex(re_ - c.re_, im_ - c.im_);
	}

	
	Complex operator - (double re)
	{
		return Complex(re_ - re, im_);
	}

	
	Complex& operator -= (Complex &c)
	{
		re_ -= c.re_;
		im_ -= c.im_;
		return *this;
	}

	
	Complex& operator -= (double re)
	{
		re_ -= re;
		return *this;
	}

	
	Complex operator * (const Complex &c)
	{
		return Complex(re_ * c.re_ - im_ * c.im_, re_ * c.im_ + im_ * c.re_);
	}

	
	Complex operator * (double re)
	{
		return Complex(re_ * re, im_ * re);
	}

	
	Complex& operator *= (Complex &c)
	{
		re_ = re_ * c.re_ - im_ * c.im_;
		im_ = re_ * c.im_ + im_ * c.re_;
		return *this;
	}

	
	Complex& operator *= (double re)
	{
		re_ *= re;
		im_ *= re;
		return *this;
	}

	
	Complex operator / (const Complex &c)
	{
		Complex temp;

		double r = c.re_ * c.re_ + c.im_ * c.im_;
		temp.re_ = (re_ * c.re_ + im_ * c.im_) / r;
		temp.im_ = (im_ * c.re_ - re_ * c.im_) / r;

		return temp;
	}

	Complex operator / (double re)
	{
		return Complex(re_ / re, im_ / re);
	}

	
	Complex& operator /= (Complex &c)
	{
		double r = c.re_ * c.re_ + c.im_ * c.im_;
		re_ = (re_ * c.re_ + im_ * c.im_) / r;
		im_ = (im_ * c.re_ - re_ * c.im_) / r;
		return *this;
	}

	Complex& operator /= (double re)
	{
		re_ /= re;
		im_ /= re;
		return *this;
	}

	bool operator == (Complex &c)
	{
		return ((re_ == c.re_) && (im_ == c.im_));
	}

	
bool operator == (double re)
	{
		return ((re_ == re) && (im_ == 0));
	}

		bool operator != (Complex &c)
	{
		return !this->operator==(c);
	}

		bool operator != (double re)
	{
		return !this->operator==(re);
	}


	double getRealPart()
	{
		return re_;
	}


	void setRealPart(double re)
	{
		re_ = re;
	}


	double getImaginaryPart()
	{
		return im_;
	}


	void setImaginaryPart(double im)
	{
		im_ = im;
	}


	double getAbs()
	{
		return sqrt(re_ * re_ + im_ * im_);
	}


	Complex getConjugate()
	{
		return Complex(re_, -1*im_);
	}


	friend ostream & operator<< (ostream &, const Complex &);
	friend istream & operator>> (istream &, Complex &);

};


ostream& operator<< (ostream &out, const Complex &c)
{
	out << "(" << c.re_ << ", " << c.im_ << ")";



return out;
}


istream& operator>> (istream &in, Complex &c)
{
	in >> c.re_ >> c.im_;
	return in;
}

int main()
{
	Complex c;
	cin >> c;
	c *= 2;
	cout << c.getConjugate() << endl;
	cout << c.getAbs() << endl;
	Complex c1(5.0, 12.5);
	cout << c1 + c << endl;
    return 0;
}
