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

