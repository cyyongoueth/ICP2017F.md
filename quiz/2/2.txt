1.Assembly,yes

2.Fortran, 1950's

3.Assembly, third, third, third, fourth

4.70's 80's 90's

5.B

6. Simyula

7.Fortran

8.>> a=int8(3+4i)

a =

  int8

   3 +   4i

>> b=int8(-5)

b =

  int8

   -5

>> cx=int8(-10i)

cx =

  int8

     0 -    10i

>> d=int8(3-4i)

d =

  int8

    3 -    4i

>> c={a,b;cx,d}

c =

  2×2 cell array

    [  3 +   4i]    [       -5]
    [0 -    10i]    [3 -    4i]
    
    

9. 

>> c{2}

ans =

  int8

     0 -    10i


10. It follows column wise so if you want a row you can put a semi colon to create it.

11. 8 bytes

12. It would only take the highest int32 number. So if MATLAB cant proccess it, then matlab's answer will give you the highest or lowest integer that it can proccess.
It would run but it would be a semantic error.
