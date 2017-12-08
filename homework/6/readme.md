Homework 6 Answers:  
1)
2)
```bash
function totalLogProb = getTotalLogProb(Param)
    global data nsample 
    logProb = zeros(nsample,1);
        for isample = 1:nsample
            logProb(isample) = log(normpdf(data(isample),Param(1),Param(2)));
        end
    totalLogProb = -sum(logProb);
end
```
```bash
load('Drand.mat')
global data nsample
data = Drand; 
mu = 0;
sigma = 1;
Param = [mu sigma];
nsample = length(data);
getTotalLogProb(Param);
fminsearch(@getTotalLogProb, Param)
```
```bash
>> hw6prob2
ans =
   -0.0820    1.0043
```
