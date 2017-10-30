QUESTION 1

Editor
function [F] = gaussian(mu,sigma,x)
F=(1/(sigma*sqrt(2*pi)))*exp(-.5*(((x-mu)/sigma)^2));
end

COMMAND WINDOW
>> gaussian(0,2,1)
ans =
    0.1760

QUESTION 2 

EDITOR
function [T] = eggs(M,c,p,K,To,Tw,Ty)
    T = ((M^(2/3))*c*(p^(1/3))/(K*(pi^2)*((4*pi/3)^(2/3)))*log(.76*((To-Tw)/(Ty-Tw))));
end

%M=mass of egg
%c=specific heat capacity
%p=density
%K=thermal conductivity
%To=original temperature
%Tw=temperature of boiling water

COMMAND WINDOW
>> eggs(67,3.7,1.038,5.4e-3,4,100,70)
ans =
  396.5763
>> eggs(67,3.7,1.038,5.4e-3,20,100,70)
ans =
  315.2179
  
 QUESTION 3 
 
EDITOR
 function results=getPolar(inputCartesianStruct)
    inputCartesianStruct.x = []
    inputCartesianStruct.y = []
    cart = isfield(inputCartesianStruct, {'x','y'})
    if cart == 1
        results.r = sqrt(inputCartesianStruct.x^2+inputCartesianStruct.y^2);
        results.phi = atan(inputCartesianStruct.x./inputCartesianStruct.y);
    else
        disp('Your dimensions are not correct.')
end
 

function results=getCart(inputPolarStruct)
    inputPolarStruct.r = []
    inputPolarStruct.phi = []
    cart = isfield(inputPolarStruct, {'r','phi'})
    if cart == 1
        results.x = inputPolarStruct.r*cos(inputPolarStruct.phi);
        results.y = inputPolarStruct.r*sin(inputPolarStruct.phi);
    else
        disp('Your dimensions are not correct.')
end

 
 QUESTION 4
 
 function [filesize,names]=dirsize(filename)
s=dir
t=size(s)
disp(s)
sizeofdir=sum([s.bytes]);
u=['The size of directory is: ',num2str(sizeofdir), 'bytes'];
disp(u);
end

 
 QUESTION 5
 
  function n = getFib(n_int)
if n_int==1||n_int==0
    n=n_int;
else
    n=fibonacci(n_int-2)+fibonacci(n_int-1);
end

function x = fib(n)
if n == -1 
    disp('end')
else
    
    fibo = isreal(n);
    if fibo == 1
        if n < 0
            disp('This isn't a non negative number.')
            x=fib(n);
        end
    
       n = round(n);
       x =getFib(n);
   
    elseif fibo==0
    disp('This isn't a real number.')
     x = fib(n);
    end
end
 
 
 QUESTION 6
 
EDITOR
 function [T] = area(x1,y1,x2,y2,x3,y3)
T=1/2*abs(x2*y3-x3*y2-x1*y3+x3*y1+x1*y2-x2*y1)
a = [x1,y1];
b = [x2,y2];
c = [x3,y3];

x = [a(1), b(1), c(1)]; 
y = [a(2), b(2), c(2)]; 

area_triangle = polyarea(x,y);
disp(['The area of this triangle is:', num2str(area_triangle)]);
    end
    
    COMMAND WINDOW
    >> area(2,3,5,7,4,9)
The area of this triangle is: 5
ans =
     5
 
 QUESTION 7 
 
 EDITOR
 function p = isPrime(x)
x=input('Enter an integer: ');
n=length(divisors(x));
if  n==2
    disp(['isPrime(',num2str(x),')']);
    disp('True');
else 
    disp(['isPrime(',num2str(x),')']);
    disp('False');
end

COMMAND WINDOW
>> primetwo
Enter an integer: 34
isPrime(34)
False
>> primetwo
Enter an integer: 55
isPrime(55)
False
>> primetwo
Enter an integer: 12
isPrime(12)
False
>> primetwo
Enter an integer: 5
isPrime(5)
True

QUESTION 8 

function y = evalFunc(a,b,c,x);
y = (a.*x^2)+(b.*x)+(c);
case 0
a=0
b=0
c=0
case 1
a=varargin(1)
case 2 
b=varargin(2)
case 3
c=varargin(3)
otherwise 
error(‘too many arguments’);
end
function h=genfunc(a,b,c,X);
y=evalFunc(a,b,c,X);
h = y;
end
