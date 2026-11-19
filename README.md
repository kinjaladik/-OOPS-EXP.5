# -OOPS-EXP.5
C++ program to implement time polymorphism : function overloading and operator overloading for a matrix or complex number class 

#include <iostream>
#include <string>
using namespace std;

class Complex {
private:

    int real, imag;

public:

    // Default constructor
    Complex() {
        real = 0;
        imag = 0;
    }
    // Parameterized constructor
    Complex(int r, int i) {
        real = r;
        imag = i;
    }
    // 1. Function Overloading: display() without arguments
    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
    // 2. Function Overloading: display() with a message string
    void display(string msg) {
        cout << msg << real << " + " << imag << "i" << endl;
    }
    // 3. Operator Overloading: Overloading the '+' operator
    Complex operator+(Complex c) {
        Complex temp;
        temp.real = real + c.real;
        temp.imag = imag + c.imag;
        return temp;
    }};

int main() {

    Complex c1(3, 4);
    Complex c2(2, 5);
    Complex c3;

    cout << "First Complex Number: ";
    c1.display();
    cout << "Second Complex Number: ";
    c2.display();
    c3 = c1 + c2;
    c3.display("Sum of Complex Numbers: ");

    return 0;
}
