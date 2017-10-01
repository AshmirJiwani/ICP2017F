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
