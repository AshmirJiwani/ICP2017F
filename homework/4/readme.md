Homework 4 answers  
1)  
```bash
function convertTempFor(InVec,str)
    ANS = zeros(1,length(InVec));
    if strcmp(str,'C2F')
       for i = 1:length(InVec)
          ANS(i) = InVec(i).*1.8 + 32;
       end
    elseif strcmp(str,'F2C')
       for i = 1:length(InVec)
          ANS(i) = (InVec(i)-32).*(5/9);
       end
    end
     disp(ANS);
end
```
```bash
function convertTempWhile(InVec,str)
    ANS = zeros(1,length(InVec));
    if strcmp(str,'C2F')
       i = 1;
       while i <= length(InVec)
           ANS(i) = InVec(i).*1.8 + 32;
           i = i + 1;
       end
    elseif strcmp(str,'F2C')
       i = 1;
       while i <= length(InVec)
          ANS(i) = (InVec(i)-32).*(5/9);
       end
    end
     disp(ANS);
end
```
```bash
function convertTempVec(InVec,str)
    if strcmp(str,'C2F')
           ANS = zeros(1,length(InVec));
           ANS = (InVec).*1.8 + 32;
           disp(ANS);
    elseif strcmp(str,'F2C')
           ANS = zeros(1,length(InVec));
           ANS = ((InVec)-32).*(5/9);
           disp(ANS);
    end
end
```
```bash
>> convertTempFor([-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40],'C2F')
    -4     5    14    23    32    41    50    59    68    77    86    95   104

>> convertTempWhile([-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40],'C2F')
    -4     5    14    23    32    41    50    59    68    77    86    95   104

>> convertTempVec([-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40],'C2F')
    -4     5    14    23    32    41    50    59    68    77    86    95   104
```
3)  
```bash
List = { {'M','A','T','L','A','B'}, {' '}, {'i','s'}, {' '}, {'a'}, {' '}, {'s','t','r','a','n','g','e'}, {', '}, {'b','u','t',' '}, {'p','o','p','u','l','a','r'}, {' '}, {'p','r','o','g','r','a','m','m','i','n','g',' ','l','a','n','g','u','a','g','e'} };
str = '';
for i= 1:length(List) 
    for a = 1:length(List{i})
        str = [str,List{i}{a}];
    end 
end
disp(str);
```
```bash
>> extractLetter
MATLAB is a strange, but popular programming language
```
6)  
```bash
function getLargestPrime(n)
    for i = n:-1:2
        if(isprime(i) == 1)
            disp(i);
            break
        end
    end
end
```
```bash
>> getLargestPrime(123)
   113

```
7)  
A)  
```bash
function fib()

    n = input('Please enter a non-negative integer or type stop: ','s');
    if strcmp(n,'stop')
        return
    else
        n = str2double(n);
        if isreal(n)
            if n>=0 && round(n)==n
                disp(['fib(',num2str(n),') = ',num2str(getFib(n))]);
                disp(['average runtime: ', num2str(timeit( @()getFib(n) )), 'seconds']);
                fib()
                return
            end
        end
        disp('The input argument is not a non-negative integer!');
        fib()
    end
    
    function fib = getFib(n_int)
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fib = getFib(n_int-1) + getFib(n_int-2);
        end
    end

end
```
```bash
>> fib
Please enter a non-negative integer or type stop: 10
fib(10) = 55
average runtime: 1.0085e-05seconds
Please enter a non-negative integer or type stop: 15
fib(15) = 610
average runtime: 8.9509e-05seconds
Please enter a non-negative integer or type stop: 20
fib(20) = 6765
average runtime: 0.00097334seconds
Please enter a non-negative integer or type stop: 25
fib(25) = 75025
average runtime: 0.010419seconds
Please enter a non-negative integer or type stop: 30
fib(30) = 832040
average runtime: 0.097022seconds
Please enter a non-negative integer or type stop: 35
fib(35) = 9227465
average runtime: 1.1576seconds
Please enter a non-negative integer or type stop: stop
```
B & C)  
```bash
function fibLoop()

    n = input('Please enter a non-negative integer or type stop: ','s');
    if strcmp(n,'stop')
        return
    else
        n = str2double(n);
        if isreal(n)
            if n>=0 && round(n)==n
                disp(['fib(',num2str(n),') = ',num2str(getFib(n))]);
                disp(['average runtime: ', num2str(timeit( @()getFib(n) )), 'seconds']);
                fibLoop()
                return
            end
        end
        disp('The input argument is not a non-negative integer!');
        fibLoop()
    end
    
    function fib = getFib(n_int) %n_int=3
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fib = 1;
            fibOld1 = 0;
            %fibOld2 = 1; 
            temp=0;
            for a = 1:n_int-1 %(for a = 1:2)
                temp=fib;
                fib = fib+ fibOld1; %(fib(3) = fib(2) + fib(1))
                fibOld1=temp;
            end
        end
    end

end
```
```bash
>> fibLoop
Please enter a non-negative integer or type stop: 10
fib(10) = 55
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11) 
average runtime: 2.4426e-06seconds
Please enter a non-negative integer or type stop: 15
fib(15) = 610
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11)
  In fibLoop (line 12) 
average runtime: 1.3222e-06seconds
Please enter a non-negative integer or type stop: 20
fib(20) = 6765
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11)
  In fibLoop (line 12)
  In fibLoop (line 12) 
average runtime: 1.4208e-06seconds
Please enter a non-negative integer or type stop: 25
fib(25) = 75025
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12) 
average runtime: 1.4918e-06seconds
Please enter a non-negative integer or type stop: 30
fib(30) = 832040
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12) 
average runtime: 1.8064e-06seconds
Please enter a non-negative integer or type stop: 35
fib(35) = 9227465
Warning: The measured time for F may be inaccurate because it is
running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In fibLoop (line 11)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12)
  In fibLoop (line 12) 
average runtime: 3.0957e-06seconds
Please enter a non-negative integer or type stop: stop
```
8)  
A)
```bash
function Output = timeFib(n)
if ~ischar(n) && isreal(n) && n>=0 && round(n)==n
    Output.n = n;
    Output.fib = getFib(n);
    Output.runtime = timeit( @()getFib(n) );
else
    disp('The input argument is not a non-negative interger!');
end

    function fib = getFib(n_int)
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fib = getFib(n_int-1) + getFib(n_int-2);
        end
    end

end
```
```bash
function Output = timeFibLoop(n)
if ~ischar(n) && isreal(n) && n>=0 && round(n)==n
    Output.n = n;
    Output.fib = getFib(n);
    Output.runtime = timeit( @()getFib(n) );
else
    disp('The input argument is not a non-negative integer');
end

    function fib = getFib(n_int) 
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fib = 1;
            fibOld1 = 0; 
            temp=0;
            for a = 1:n_int-1 
                temp=fib;
                fib = fib+ fibOld1; 
                fibOld1=temp;
            end
        end
    end
end
```
```bash
>> timeFib(20)
ans = 
  struct with fields:

          n: 20
        fib: 6765
    runtime: 6.9213e-04
>> timeFib('amir')
Error using timeFib (line 7)
The input argument is not a non-negative interger! 
>> timeFibLoop(20)
Warning: The measured time for F may be inaccurate because it is running too fast. Try measuring something that takes longer. 
> In timeit (line 158)
  In timeFibLoop (line 5) 
ans = 
  struct with fields:

          n: 20
        fib: 6765
    runtime: 3.0195e-06
>> timeFibLoop('amir')
Error using timeFibLoop (line 7)
The input argument is not a non-negative integer 
>> 
```
