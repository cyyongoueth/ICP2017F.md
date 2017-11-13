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

PROBLEM 2

function [F]=timeFacFuncs(x,'getFacWhile','getFacFor','getFacVec')
if x==getFacWhile
    A=tic, timeFacFuncs(x,'getFacWhile'), toc;
    disp('average runtime for getFacWhile: ',num2str(A));
elseif x==getFacFor
    B=tic, timeFacFuncs(x,'getFacFor'), toc;
    disp('average runtime for getFacFor: ',num2str(B));
else x==getFacVec
      C= tic, timeFacFuncs(x,'getFacFor'), toc;
      disp('average runtime for getFacVec: ',num2str(C));
end
