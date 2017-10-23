1) The dot essentially makes each term mutliply,divide,subtract, or add by the other term in the same sequence. So it lets a=[a,b] b=[a,b] answer=[a*a,b*b] instead of once single dot product number.

2)  >> A=[1,0,3]

A =

     1     0     3

>> B=[2,3,7]

B =

     2     3     7

>> dot(A,B)

ans =

    23
    
      
3)


4)


5) CHANGE THE GREATER THAN SIGN TO A LESS THAN SIGN

>> x = a/b<10.0

x =

  logical

   0
   
6) The SECOND representattion would be a lot more efficient for two reasons. One- it is shorter code and faster. Two- since you are making the name and the grade two seperate components, there is no need to individually/one at a time input each seperate person's information.

7) a=input('choose an a value');
b=input('choose a b value');
c=input('choose a c value');
quad=(a*(x^2)+(b)*x+c);
  
answer=root(quad);

disp(['The roots of your function are',num2str(answer)])

8) a=('input a');
b=('input b');
c=('input c');
f = @(a,b,c) x^2+cx+1;
 Q=integral(b,a);
