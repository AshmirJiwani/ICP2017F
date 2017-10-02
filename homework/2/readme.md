Homework 2 Answers  
1)  
```bash
>> a = 1
a = 
1
>> b = 'x' 
b =
    'x'
>> c = true
c =
  logical
   1
>> whos a b c
  Name      Size            Bytes  Class      Attributes

  a         1x1                 8  double               
  b         1x1                 2  char                 
  c         1x1                 1  logical              
>> a == c
ans =
  logical
   1
>> a + c
ans =
     2
>> d = [1 2 3 4]
d =
     1     2     3     4
>> e = ['a' 'b' 'c' 'd']
e =
    'abcd'
>> f = ['abcd']
f =
    'abcd'
>> g = {‘a’ ‘b’ ‘c’ ‘d’}
 g = {‘a’ ‘b’ ‘c’ ‘d’}
      ↑
Error: The input character is not valid in
MATLAB statements or expressions.
>> h = { a b c d}
h =
  1×4 cell array
    {[1]}    {'x'}    {[1]}    {1×4 double}
>> whos d e f g h
  Name      Size            Bytes  Class     Attributes

  d         1x4                32  double              
  e         1x4                 8  char                
  f         1x4                 8  char                
  h         1x4               491  cell   

```
2)   
```bash
>> int16(intmin)
ans =
  int16
   -32768
>> int16(intmax)
ans =
  int16
   32767
>> int32(intmin)
ans =
  int32
   -2147483648
>> int32(intmax)
ans =
  int32
   2147483647

```
3)  
```bash
>> 1\2
ans =
     2
```
The backslash function divides the second number by the first number. 
```bash
>> 1/2
ans =
    0.5000
```
The forward-slash function divides the frist number by the second number.
```bash
>> int8(1/2)
ans =
  int8
   1
```
The int8 function finds the integer value from -128 to 127 so it rounds 0.5 to 1
```bash
>> int8(1/3)
ans =
  int8
   0
```
The int8 function finds the integer value from -128 to 127 so it rounds 0.333 to 0
```bash
>> -5^2
ans =
   -25
```
The exponent multiplies the 5's together then adds a negative sign in front of the product
```bash
>> (-5) ^ 2
ans =
    25
```
The parenthesis allows the two -5's to be multiplied to with each other
```bash
>> 10-6/2
ans =
     7
```
Order of operations first divides the 6 by the 2 then subtracts the quotient from 10
```bash
>> 5*4/2*3
ans =
    30
```
This function works the operations from left to right.   
4a)  
```bash
>> a = [1,0;2,1]
a =
     1     0
     2     1
>> b = [-1,2;0,1]
b =
    -1     2
     0     1
>> c = [3;2]
c =
     3
     2
>> d = [5]
d =
     5
```
  
4b)  
1.  
```bash
>> a + b
ans =
     0     2
     2     2
```
MATLAB is adding matrices A and B together  
2.  
```bash
>> a .* b
ans =
    -1     0
     0     1
```
MATLAB multiplies the matrcies as a point-wise product  
3.  
```bash
>> a * b
ans =
    -1     2
    -2     5
```
MATLAB multiplies matrices A and B together  
4.  
```bash
>> a * c
ans =
     3
     8
```
MATLAB multiplies matrices A and C together  
5.  
```bash
>> a + c
ans =
     4     3
     4     3
```
MATLAB adds matrices A and C together  
6.  
```bash
>> a + d
ans =
     6     5
     7     6
```
MATLAB adds matrices A and D together  
7.  
```bash
>> a .* d
ans =
     5     0
    10     5
```
MATLAB multiplies matrices A and D together as a point-wise product  
8.  
```bash
>> a * d
ans =
     5     0
    10     5
```
MATLAB multiplies matrices A and D together  
5)  
Method 1: diag() function  
```bash
a =
     2     2     2
>> diag(a)
ans =
     2     0     0
     0     2     0
     0     0     2
```
Method 2: eye() Function  
```bash
>> A = 2 * eye(3)
A =
     2     0     0
     0     2     0
     0     0     2
```
Method 3: zeros function
```bash
>> zeros(3) + diag(a)
ans =
     2     0     0
     0     2     0
     0     0     2
```
6)   
Line 1-  
```bash 
1a = 2;
```
Error occurs because a variable cannot be define where a number stands before a letter.  
Line 4-  
```bash 
y = X + 4; 
```
Error occurs because X is not a variable, while x is.  
Line 5-  
```bash
pi = 4 () atan(1);
```
Error occurs because the function isnt a function is MATLAB.  
Line 8- 
```bash 
disp(tan(pi));
```
You must set tan(pi) to a new variable and then display the new variable.  
Line 10- 
```bash 
_ = ((c-78564)/c + 32));
```
A variable must be define for this line.  
Line 12- 
```bash 
disp(['The year is ' year]); 
```
Cannot display number with a string so you must use the num2str function to change 2017 to display as a string.  
Line 13- 
```bash 
stuff = {'a' 'b' 4 21 'c'};
```
Must change all indexes in this mastrix to string values.  
Line 14- 
```bash 
beginning = stuff(0);
```
Error occurs because 0 is not the first index. The first index of a matrix is always 1.  
Line 16- 
```bash 
discount = 12%;
```
The variable discount must be changed to a string.  
Line 17- 
```bash 
AMOUNT = 120.-;
```
AMOUNT needs to be set as an integer value.  
Line 18- 
```bash 
amount = 120$;
```
amount needs to be stored as a string.  
Line 19- 
```bash 
and = duck;
```
variable and needs to set as "duck".  
Line 20- 
```bash 
class = 'INF1100, gr 2";
```
Need to use either "" or '' together. A combination of both results in error.  
Line 24- 
```bash 
Persian = ['Persian';' is ' 'a',' human ' 'language'];
```
Need to remove semicolon and use braces instead of bracket so that values will seen as full strings when called upon.  
Line 26- 
```bash 
disp([Persian 'is not the same as' Spanish(:)]);
```
Need to call upon indexes of the arrays.  
Corrected code:  
```bash
a = 2;
b = 1;
x = 2;
y = x + 4;
pi = 4 * atan(1);
disp(pi);
pi == '3.14159';
p = tan(pi);
disp(p);
c = (4)^(3)^(2)^(3);
d1 = ((c-78564)/(c + 32));
year = 2017;
disp(['The year is ' num2str(year) '.']); 
stuff = {'a' 'b' '4' '21' 'c'};
Beginning = stuff(1);
End = stuff(5);
discount = '12 %%';
AMOUNT = 120;
amount = '120$';
and = 'duck';
class = 'INF1100, gr 2';
continue_ = x > 0;
fox = false;
wolf = fox == true;
Persian = {'Persian' ' is ' 'a' ' human ' 'language'};
Spanish = {'Spanish ' 'is ' ' another' 'language'};
f = [Persian{1} ' ' 'is not the same as' ' ' Spanish{1}];
disp(f);
```
7)  
```bash
>> mkdir mynewdir
>> cd mynewdir
>> edit mynewdir/myscript.m
On script:
x = -2*pi:pi/20:2*pi;
y = abs(sin(x));
plot(x,y);
>> myscript
```
8)  
```bash
cd ..
>> myscript
Undefined function or variable 'myscript'.
```
This error occurs because the script called myscript is not in the current working directory I am on. MATLAB does not know where to track the script in order to run it.  
