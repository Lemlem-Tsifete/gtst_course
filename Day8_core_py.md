# Indexing and slicing
in Slicing `:` it is possible to access a #section of items from the list using the slicing operator 
my _list [start: stop: step ]
quiz
name[::-1] invert the list indexing
name[::-2] invert the list but jump by 2 

 ## Input function 
 to convert the str to numeric in input function int(input("Enter the fruit name"))
 `eval` is like `int`
 **arguments
 this help us to get the input from the command lines
 shell: python gtst.py arg1, arg2, arg3 
 eg 
import sys # package
name = sys.argv[1]
print(f"hello: {name}")** its work before the code run 

## Bitwise operation

print(bin(5)) convert to 5 to binary number 
print(int('101', 2)) convert to binary number 

**if you work on Cryptography on hacking this is must ! to now**

bitwise operators

compliments(not) (`~`)  it work like convert first value to binary and it will reverse each bit then converts to decimal.
print(~-5) -# -5 + 1 = -(-4) = 4
and (`&`) - convert the number to binary like
`print(10 & 7) 10 - 1010 &&&& 0111` it give 2 
xor (`^`)(kerit) - if they are same = 0 , if they are different = 1 
Left shift(`<<`) shifting  bits to the left
10 << 2   10 - 1010.0000
Right shift(`>>`) shifting  bits to the right

python loops 

There are 2 types of loops in python:
- for loop-  we know the termination point 
- while loop - we don't know the termination point only use the specific condition we can use `break` keywork to terminate the loop 

## Function 

block of code performs a specific task 

`def function_name(agruments):` - this is definition of the function keyword 

`return` - not display but give the result to the function and not use bracket 
`pow(4, 2 )` keyword it give a power for the number 

## Recursion
disadvantage 
1. sometimes the logic behind recursion is hard to follow through.
2. Recursive call are expensive(inefficient) as they take up a lot of memory and time
3. recursive function are hard to debug 

## lambda function /anonymous function

the function don't have a name in simple way 
`lambda n: n%2==0, nums`

#### Function taker

filter , map , and reduce takes a function as an argument 

filter(function, list)
map used to do some operations on sequences special on operation like to add subtract like this kind of operation 


