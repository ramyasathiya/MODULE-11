## Ex.No:5
## Ex.Name: Object Delegation in C++ (using float data)
## Date: 3/11/25
## Aim:
To write a C++ program to demonstrate object delegation (one object delegating tasks to another) using float data.

## Algorithm:
Start the program.

Define a class Delegate with:

A private float data member.

A constructor to initialize the data.

A function show() to display the value.

Define another class MainClass that contains an object of class Delegate.

In MainClass constructor, delegate initialization to the Delegate class.

In main():
Read a float value from the user.
Create a MainClass object.
Call the function to display the value.

Stop the program.

## Program:
```
#include <iostream>
using namespace std;

// Simple class
class A {
public:
	float a;

};

// Complex class
class B :public A{
    public:
    void disp(float a){
        cout<<a<<endl;
    }
	
	
};

// Driver code
int main()
{
	double a;
	cin>>a;
	B x;
	x.disp(a);
	return 0;
}
```
## Output:


<img width="884" height="414" alt="image" src="https://github.com/user-attachments/assets/aa6e0387-3d6c-464f-8a0b-bd9ed7717f2c" />


## Result:
The Program Executed Successfully.
