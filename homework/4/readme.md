Homework 4 answers  
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
6)  
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
