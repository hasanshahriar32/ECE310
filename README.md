## Experiment No: 1

**Name of the Experiment:** Finding the root of the function f(x) =5xlog10(x) – 6 using Bisection Method. 

**Objective:** To find the root of the given function.

**Theory:** The Bisection Method is a numerical technique for finding the root of a function—a value of x where f(x) = 0. It is a bracketing method that requires two initial points enclosing a root. The method relies on the Intermediate Value Theorem, which states that if a continuous function f(x) on the interval [a,b] has f(a)⋅f(b) < 0, then at least one root exists in that interval.

**Apparatus:** 

- A computer
- Matlab Software

**MATLAB Code:** 

```matlab
%%%Bisection Method%%% 
clc; 
clear all; 
close all; 
f= @(x)5*x*log10(x)-6; 
a= input('Enter the value of a: '); 
b= input('Enter the value of b: '); 
tol_error=input('Enter the value of tolerable error: '); 
fa= f(a); 
fb= f(b); 
xr= (a+b)/2; 
fxr= f(xr); 
n=0; 
present_root=xr; 
next_root=0; 
  
if fa*fb>0 
    disp('The initial values do not bracket the root.'); 
else 
    fprintf('The bisection method will work\nRoot using bisection method 
is given below:\n'); 
    fprintf('step\t a\t\t\t b\t\t\t xr\t\t\t fa\t\t\t fb\t\t  f(xr)\n'); 
    fprintf('--------------------------------------------------------------------------
\n'); 
    while abs(next_root-present_root)>tol_error 
     fprintf('%d\t %f\t %f\t %f\t %f\t %f\t %f\n', n,a,b,xr,fa,fb,fxr);  
      
     if fa*fxr<0 
         b= xr; 
         fb= f(b); 
     else 
         a=xr; 
         fa= f(a); 
     end 
     present_root = xr; 
     xr = (a+b)/2; 
     fxr= f(xr); 
     next_root = xr; 
     n= n+1; 
    end 
end 
     fprintf('The root is: %f', xr); 
```

**Sample Input and Output:** 

<aside>Enter the value of a: 0.5

Enter the value of b: 3.5
Enter the value of tolerable error: 0.0001
The bisection method will work
Root using bisection method is given below:

11  2.739746  2.741211  2.740479  -0.003924 0.002463  -0.000731
12  2.740479  2.741211  2.740845  -0.000731 0.002463  0.000866
13  2.740479  2.740845  2.740662  -0.000731 0.000866  0.000068
The root is: 2.740570>>

</aside>
