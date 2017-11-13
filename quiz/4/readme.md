PROBLEM 1

A

function [F]= getFacWhile(N)
    A=factorial(N);
    while N~=0;
        disp(A);
        break
    end
    
    PROBLEM
    
    
B

function [F]= getFacFor(N)
    if N>0 || N<0
        for A=factorial(N)
        disp(A);
        end
        else
            disp(error);
        end
  
C

function [F]= getFacFor(N)
    A=factorial(nt2int);
    N = randn(n,1);
    if N>0 || N<0
        disp(A);
        end
if N==0
    disp(error);
end

