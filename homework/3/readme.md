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
