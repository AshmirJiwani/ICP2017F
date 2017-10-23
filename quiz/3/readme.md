Quiz 3 
1) A * operator multiplies vectors/matrices by each other but the dimensions of the the matrices/vactors cannot be the exact same while the .* is a element-wise multiplier which multiples the indexes of matrices by each other.  
A = [1,2,3];  
B = [4,5,6];   
A*B would result in error because the dimensions do not match while A.*B would multiply the elements by each other and make a new vector such as: 4,10,18  
2) The simplest way to get the result of the dot product of two vectors is to use the element wise multiplier: A.*B  
3) A)
   function x = testString(string)
	string = input('Please enter a string: ')
	if(string == 'MATLAB')
		x = true;
	else
		x = false;
	end

   B) The other way of comparing strings is using the function isequal(). The difference between these two operators is that the == operator compares each char of the first string with each char of the second string, while the isequal() operator compares the ASCII values of the two strings with each other. The following code with result as the value of z being the value of true since x and y are the same exact string.   

  x = 'MATLAB'
	y = 'MATLAB'
	z = true;
	if(x == y)
	z = true;
	if(isequal(x,y))
	z = true;
	else
	z = false;
	end

4) The | and || operators are the boolean OR operators. The difference between | and || is that the || is a short circuit which provides code efficiency while the | operator is used to operate on logical vectors and scalars.  
5)The simplest change to the logical expression x = a/b)10.0 would be x = a\b>10.0  
6) The first respresentation would be more effecient since the data would be easier/quicker to find and compute.  
7) function x = getRoot()
   a = 1;
   b = 1;
   c = 1;
   x = sqrt(a*x.^2 + b*x + c)
8)
   a = 1;
   b = 1;
   c = 1;
   function g(c) = @(c) integral(x.^2 + c*x + 1,a,b)
9)   function y = getFac(x)  
	x = input('Please enter an integer:')  
	if(x > 0)  
	
	y = x*(x-1)*  
	
