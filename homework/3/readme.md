Question 1)  
```bash
function y = probdensfunc(m,s,x) 
m = 0;
s = 2;
x = 1;
y = (1/(sqrt(2*pi)*s))*exp((-1/2)*(((x-m)/s).^2))
end
```
```bash
>> probdensfunc
y =
    0.1760
ans =
    0.1760
```
```bash
>> normpdf(1,0,2)
ans =
    0.1760
```
Question 2) The function when a large egg is taken out from a fridge:  
```bash
function t = cookedegg(m,M,p,c,K,Tw,To,Ty)
m = 47;
M = 67;
p = 1.038;
c = 3.7;
K = .0054;
Tw = 100;
Ty = 70;
To = 4;
t = (((M.^(2/3))*c*p.^(1/3))/(K*(pi.^2)*(4*pi/3).^(2/3)))*log(0.76*((To-Tw)/(Ty-Tw)))
end
```
```bash
>> cookedegg
t =
  396.5763
ans =
  396.5763
```
When an egg is cooked from room temperature:  
```bash
function t = cookedegg(m,M,p,c,K,Tw,To,Ty)
m = 47;
M = 67;
p = 1.038;
c = 3.7;
K = .0054;
Tw = 100;
Ty = 70;
To = 20;
t = (((M.^(2/3))*c*p.^(1/3))/(K*(pi.^2)*(4*pi/3).^(2/3)))*log(0.76*((To-Tw)/(Ty-Tw)))
end
```
```bash
>> cookedegg
t =
  315.2179
ans =
  315.2179
```
Question 3)  
Converting Cartesian Coordinates to Polar Coordinates:  
```bash
function PolarStruct = getPolar(CartStruct)
CartStruct.x = input('What value of x would you like? ');
CartStruct.y = input('What value of y would you like? ');
PolarStruct.r = sqrt(CartStruct.x^2 + CartStruct.y^2);
PolarStruct.phi = radtodeg(acos(CartStruct.x/PolarStruct.r));
% input an x and y otherwise there will be an error
end
```
```bash
>> getPolar
What value of x would you like? 1
What value of y would you like? 2
ans = 
  struct with fields:

      r: 2.2361
    phi: 63.4349
```
Converting Polar Coordinates to Cartesian Coordinates:  
```bash
function CartStruct = getCart(PolarStruct)
PolarStruct.r = input('What value of r would you like? ');
PolarStruct.phi = input('What value of phi would you like? ');
CartStruct.x = (PolarStruct.r)*cos(degtorad(PolarStruct.phi));
CartStruct.y = (PolarStruct.r)*sin(degtorad(PolarStruct.phi));
% input an r and phi otherwise there will be an error
end
```
```bash
>> getCart
What value of r would you like? 2.2361
What value of phi would you like? 63.4349
ans = 
  struct with fields:

    x: 1.0000
    y: 2.0000
```
Question 4)  
```bash
function bytes = getSize(mydir)
bytes = sum([mydir.bytes]);
end
```
```bash
mydir = input('Input directory name: ', 's');
if 7==exist(mydir,'dir');
    mydir = dir;
    Tot_size = getSize(mydir);
    disp(['The total size of the directory is ',num2str(Tot_size), + ' bytes']);
else
    disp('The file does not exist.');
end
```
```bash
>> Untitled4
Input directory name: Downloads
The total size of the directory is 2354545013 bytes
```
Question 6)  
```bash
function Area = getTriangleArea(vertices)
x1 = vertices(1);
y1 = vertices(2);
x2 = vertices(3);
y2 = vertices(4);
x3 = vertices(5);
y3 = vertices(6);
abs_value = abs((x2*y3)-(x3*y2)-(x1*y3)+(x3*y1)+(x1*y2)-(x2*y1)); 
Area = (0.5)*abs_value;
end
```
```bash
vertices = input('Enter 3 vertices counter-clockwise: ');
a = getTriangleArea(vertices);
disp(a);
```
```bash
>> Untitled5
Enter 3 vertices counter-clockwise: [12,0,6,6,0,0]
    36
```
