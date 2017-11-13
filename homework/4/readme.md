---NUMBER ONE

PART A) WHILE LOOP

EDITOR

function [F] = ConvertTempWhile(InVec,statement)
    InVec = [-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40];
    while statement =='C2F'
    F=InVec*(9/5)+32; 
        end
    while statement =='F2C'
     F=(InVec-32)*(5/9);
    end
while statement ~= 'F2C' | 'C2F'
    disp('This is an error')
end
    
COMMAND WINDOW

>> ConvertTempWhile(InVec,'C2F')

ans =

   -4     5    14    23    32    41    50    59    68    77    86    95   104


>> ConvertTempWhile(InVec,'F2C')

ans =

  -28.8889  -26.1111  -23.3333  -20.5556  -17.7778  -15.0000  -12.2222   -9.4444   -6.6667   -3.8889   -1.1111    1.6667    4.4444


>> ConvertTempWhile(InVec,'wer')
This is an error


PART B) FOR LOOP

EDITOR

function [F] = ConvertTempFor(InVec,statement)
if statement =='C2F'
    for InVec = [-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40];
    F=InVec*(9/5)+32;  
    end
if statement =='F2C'
    for InVec = [-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40];
     F=(InVec-32)*(5/9);
    end
else
    disp('This is an error')
end
end

COMMAND WINDOW

>> ConvertTempFor(InVec,'C2F')

ans =

    -4     5    14    23    32    41    50    59    68    77    86    95   104


>> ConvertTempFor(InVec,'F2C')

ans =

  -28.8889  -26.1111  -23.3333  -20.5556  -17.7778  -15.0000  -12.2222   -9.4444   -6.6667   -3.8889   -1.1111    1.6667    4.4444


>> ConvertTempFor(InVec,'fsk')
This is an error

PART C) VECTORIZATION

EDITOR

function [F] = ConvertTempVec(InVec,statement)
    InVec = [-20, -15, -10, -5, 0, 5, 10, 15, 20, 25, 30, 35, 40];
if statement =='C2F'
F=InVec*(9/5)+32; 
elseif statement =='F2C'
F=(InVec-32)*(5/9);
else
disp('This is an error')
end
end

COMMAND WINDOW

>> ConvertTempVec(InVec,'C2F')

ans =

    -4     5    14    23    32    41    50    59    68    77    86    95   104


>> ConvertTempVec(InVec,'F2C')

ans =

  -28.8889  -26.1111  -23.3333  -20.5556  -17.7778  -15.0000  -12.2222   -9.4444   -6.6667   -3.8889   -1.1111    1.6667    4.4444


>> ConvertTempVec(InVec,'orp')
This is an error

---NUMBER TWO

FOR LOOP

>> tic, ConvertTempFor(InVec,'C2F'), toc

ans =

    -4     5    14    23    32    41    50    59    68    77    86    95   104

Elapsed time is 0.001190 seconds.

WHILE LOOP

>> tic, ConvertTempWhile(InVec,'C2F'), toc

ans =

    -4     5    14    23    32    41    50    59    68    77    86    95   104

Elapsed time is 0.000893 seconds.

VECTORIZATION

tic, ConvertTempVec(InVec,'C2F'), toc

ans =

    -4     5    14    23    32    41    50    59    68    77    86    95   104

Elapsed time is 0.000689 seconds.

EXPLANATION: Vectorization is faster than a while loop which is faster than a for loop. The vectorization lets the code run and perform its operations for all elements at one time instead of looping,which takes longer.

---QUESTION 3 

function [L]= extractLetter(letters)
    if (isa(letters,'cell'))
        length=size(letters)
        code=[];
        for i=1:length(2)
            code=[code,letters{i}];
            disp([code])
        end
    end
end


---QUESTION 4

This code takes the given value of 2, takes just its square root, and then squares it. This proccess is done 60 times total.

The result of this code actually ends up being 1 and not 2. This is because when r>1 then the sqrt(r)>1 and r>sqrt(r). The value of r is decreasing but is still larger than one, r will not be greater than one after so many times of being square rooted.

---QUESTION 5

This code takes the given value of 1 and basically recursively checks if 1.0 ~= 1.0 + eps 
is true or false. This example code also uses one of MATLAB’s built in function’s, eps, which lets the general equation use the given value and then divides it by 2 until
one gets the lowest value is reached which in this case is equal to
eps(1)= 1.1102e-16

1.0 ~= 1.0 + eps is shown as being false or equal to each other because the a value between 1.0 and eps(1) had to  have been true(1.0 = 1.0  + eps), this one aspect pretty much determined the rest of the question and made it true. The true basically carried for the entire code. 

---QUESTION 6

function L = getLargestPrime(x)
    for i=1:x
        if isprime(i)
            L=i;
        end
    end
end

---QUESTION 7 

PART A

function fib()
 
 m = input('Please enter a non negative integer number or please type stop:  ','s');
    if strcmp(m,'stop')
        return
    else
        m = str2double(m);
        if isreal(m)
            if m>=0 && round(m)==m
                disp([char(9),'averageruntime:', num2str(timeit(@()getFib(m)))]);     
                fib()
                return
            end
        end
        disp('The input argument is not a non negative integer');
        fib()
    end
    
    function fib = getFib(m_int)
        if m_int == 0
            fib = 0;
        elseif m_int == 1
            fib = 1;
        else
            fib = getFib(m_int-1) + getFib(m_int-2);
        end
    end
 
end

PART B
function fibLoop()
 
n = input('Please enter a non-negative integer or please type stop: ','s');
    if strcmp(n,'stop')
        return
    else
        n = str2double(n);
        if isreal(n)
            if n>=0 && round(n)==n
                disp([char(9),'averageruntime:', num2str(timeit(@()getFib(n)))]);
                fib()
                return
            end
        end
        disp('The input argument is not a non-negative integer!');
        fib()
    end
    
    function fib = getFib(n_int)
        fibseq = zeros(n_int+1,1);
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fibseq(1) = 0;
            fibseq(2) = 1;
            for i = 3:n_int+1
                fibseq(i) = fibseq(i-1) + fibseq(i-2);
            end 
            fib = fibseq(end);
        end
    end
 
end

PART C

Loops are faster because when they run they basically do as much as possible at once while recursives need to pull each iteration seperately.

---QUESTION 8 

8. 

PART A
function Output() = timeFib()
  n = input('Please enter a non-negative integer or please type stop: ','s');
    if strcmp(n,'stop')
        return
    else
        n = str2double(n);
        if isreal(n)
            if n>=0 && round(n)==n
                dummyGetFib = getFib(n);
                dummyRuntime = timeit(@()getFib(n));
                %disp([char(9),'averageruntime:', num2str(timeit(@()getFib(n)))]);
                Output.n = n;
                Output.fib = dummyGetFib;
                Output.runtime = dummyRuntime;
                return
            end

for i = 1:35
        OutputTimeFib = timeFib(i);        '
        end
        disp('The input argument is not a non negative integer');
        fib()
    end
    
    function fib = getFib(n_int)
        fibseq = zeros(n_int+1,1);
        if n_int == 0
            fib = 0;
        elseif n_int == 1
            fib = 1;
        else
            fibseq(1) = 0;
            fibseq(2) = 1;
            for i = 3:n_int+1
                fibseq(i) = fibseq(i-1) + fibseq(i-2);
            end 
            fib = fibseq(end);
        end
    end
 
end



B.
        OutputTimeFibLoop = timeFibloop(i);
end




