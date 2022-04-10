# My-Learning-List
## Introduction of Object Oriented Programming - 09/04/2022
[Article on educative](https://www.educative.io/blog/object-oriented-programming)

## SOLID Principle in OOP in C# - 09/04/2022
[S.O.L.I.D. Principles of Object-Oriented Programming in C#](https://www.educative.io/blog/solid-principles-oop-c-sharp)

# 11/04/2022
## Difference between Class and Object 
[Geeksforgeeks link](https://www.geeksforgeeks.org/difference-between-class-and-object/?ref=gcse)

## Use of Classes and Object Inside and Outside of Main Class.
yes in case of aggregation and composition
[Read more](https://stackoverflow.com/questions/44611995/can-we-create-an-object-outside-of-methods-but-inside-the-class-if-yes-then-wha)

##Can Class and Object exist or use Individually?
Class can be used without creating object if taht method of class is static.

## Static Keyword 
[Read ](https://www.studytonight.com/cpp/static-keyword.php)

## Virtual Keyword
Virtual Function is a function in base class, which is overrided in the derived class,
and which tells the compiler to perform Late Binding on this function.

Virtual Keyword is used to make a member function of the base class Virtual.
[Read more](https://www.studytonight.com/cpp/virtual-functions.php)

## Abstract Keyword
[Read article](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)

## Final Keyword
Sometimes you don’t want to allow derived class to override the base class’ virtual function. 
C++ 11 allows built-in facility to prevent overriding of virtual function using final specifier.

2nd use of final specifier: 
final specifier in C++ 11 can also be used to prevent inheritance of class / struct. 
If a class or struct is marked as final then it becomes non inheritable and it cannot be used as base class/struct. 
[Read more](https://www.geeksforgeeks.org/c-final-specifier/)

## Explicit Keyword
We are allowed only one implicit convertion in C++,
explicit keyword does not allow implicit convertion, if needed, u have to explicitly 
type cast and call the related constructor.
[Video link](https://www.youtube.com/watch?v=Rr1NX1lH3oEs)

## This Keyword
The ‘this’ pointer is passed as a hidden argument to all nonstatic member function calls and is available as 
a local variable within the body of all nonstatic functions.

Following are the situations where ‘this’ pointer is used:
1) When local variable’s name is same as member’s name
2) To return reference to the calling object
[Read more](https://www.geeksforgeeks.org/this-pointer-in-c/?ref=gcse)

But in the following cases it doesnot work( we use Initializer List):
1) For initialization of non-static const data members: 
2) For initialization of reference members: 
3) For initialization of member objects which do not have default constructor: 
{Question:  When we initialize a class object with obj(arg1) in main body , it works,
but when we try to do same thing in an another class member attributes like ClassB b(arg1),
it doesn/t work and we have to change it into ClassB b = ClassB(arg1. Why is that?)}
4) For initialization of base class members : 
5) When constructor’s parameter name is same as data member 
6) For Performance reasons: 

[Read more](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)

## new Keyword
It is used to allocate amount of memory and return a pointer to that address.It looks for free 
memory. It can be used to allocating memory for any data type(permitive & user defined). In case 
of following:
int* a = new int[40];
string* b = new(a) string;
The situation is slightly different, as far as I understood(might be wrong), it allocates the old memory 
to the new data we are assigning to it if it fits in it.
[Video link](https://youtu.be/NUZdUSqsCs4)

## const Keyword
=>With variables
Variable declared as const will act as a constant, it can not be changed,
it remains as it is till its lifetime.
=>With pointers
Here is the word cont , I think, actually creates cinfusions:

In first case:
int a = 90;
if you write 
const int* b = new int(8);
its content cannot be changed,
*b = 10; (error)
but you can change the address it is refrencing to:
b = (int*)&a;
cout<<b;
output would be 90 instead of 8.

int const * b = new int(8);//this means same as the above 

In second case:
int* const  b = new int(8);
now it is reverse to the previous situation, we can change content but not address:
b = (int*)&a;(error)
*b = 10;

=>class getters
In a class, getter fiunctions should be const
as 
int GetX() const {}.
The reason is that it is promising only to return any thing but would not change
the values (attributes value) of the class.

If you want to change the value inside getter function, for any debugging purpose or whatsoever,
you can use mutable. It allows to change content of variable even inside const methods.
 

## super Keyword
Normally in other languages like java, it is used to call a method of parent class. Like:

class Base{
	public:
		void print(){cout<<"I am Base class";}
};

class Derived:public Base{
	public:
	typedef Base super;
		void print(){
		    cout<<"I am Derived class";
		  //  super::print();
		}
};

int main(){
    
    Derived B;
    B.super::print();
}

Output:
I am Base class
