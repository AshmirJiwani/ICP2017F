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
Question 2)  
