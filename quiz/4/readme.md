Quiz 3)  
1)  
```bash
function getFacWhile(n)
  orginalN = n;
  fac = n;
  while n > 1
    n = n-1;
    fac = fac*n;
  end
  disp(fac);
end
```
```bash
function getFacfor(n)
  fac = 1;
  for a = n:-1:1
    fac = fac * a;
  end
  disp(fac);
end
```
```bash
function getFacVec(n)
  fac = 1;
  ANS = zeros(1,n);
  i = 1:n
  ANS(i) = i;
  fac = prod(ANS);
  disp(fac);
end
```
2)  
disp(['average runtime for getFacWhile(', num2str(1700000), '): ', num2str(timeit( @()getFacWhile(1700000) )), ' seconds']);
disp(['average runtime for getFacfor(', num2str(1700000), '): ', num2str(timeit( @()getFacfor(1700000) )), ' seconds']);
disp(['average runtime for getFacVec(', num2str(1700000), '): ', num2str(timeit( @()getFacVec(1700000) )), ' seconds']);
