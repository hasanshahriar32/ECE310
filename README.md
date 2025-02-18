# Discrete Mathematics and Numerical Methods Sessional

| Experiment Number | Experiment Name |
|-------------------|-----------------|
| [Experiment No: 1](#experiment-no-1) | Finding the root of the function f(x) =5xlog10(x) – 6 using Bisection Method |
| [Experiment No: 2](#experiment-no-2) | [Add Experiment Name] |
| [Experiment No: 3](#experiment-no-3) | [Add Experiment Name] |

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
```matlab
Enter the value of tolerable error: 0.0001 
The bisection method will work 
Root using bisection method is given below: 
step         
a          b        xr          fa        fb        fxr
---------------------------------------------------------------------------------------  
0.500000  3.500000  2.000000  -6.752575 3.521191  -2.989700 
2.000000  3.500000  2.750000  -2.989700 3.521191  0.040825 
2.000000  2.750000  2.375000  -2.989700 0.040825  -1.538995 
2.375000  2.750000  2.562500  -1.538995 0.040825  -0.763994 
2.562500  2.750000  2.656250  -0.763994 0.040825  -0.365178 
2.656250  2.750000  2.703125  -0.365178 0.040825  -0.163059 
2.703125  2.750000  2.726563  -0.163059 0.040825  -0.061336 
2.726563  2.750000  2.738281  -0.061336 0.040825  -0.010310 
2.738281  2.750000  2.744141  -0.010310 0.040825  0.015244 
2.738281  2.744141  2.741211  -0.010310 0.015244  0.002463 
10  2.738281  2.741211  2.739746  -0.010310 0.002463  -0.003924 
11  2.739746  2.741211  2.740479  -0.003924 0.002463  -0.000731 
12  2.740479  2.741211  2.740845  -0.000731 0.002463  0.000866 
13  2.740479  2.740845  2.740662  -0.000731 0.000866  0.000068 
The root is: 2.740570>>
```


## Experiment No: 2

**Name of the Experiment:** Finding the root of the function f(x) = x^3 - 4x - 9 = 0 using the False Position (Regula Falsi) Method.

**Objective:** To find the root of the given function f(x) = x^3 - 4x - 9 = 0 using the False Position method with a tolerance rate of 0.001.

**Theory:**

The False Position (Regula Falsi) Method is a numerical technique for finding the root of a continuous function. It is similar to the Bisection Method but more efficient in certain cases because it approximates the root by interpolating a straight line between two points, rather than halving the interval. The method assumes that the root lies between two points where the function has opposite signs and iteratively refines the estimate by computing the intersection of the function with the x-axis.

**Apparatus:**

- A computer
- Python (or Matlab) software for computation

**Matlab Code:**

```matlab
clc; clear; close all;
f=@(x) x^3-4*x-9;

 a= input('Enter the value of a:  ');
 b = input('Enter the value of b :  ');
 e = input('Enter the error tolrent e: ');

fa = f(a);
fb = f(b);
xr = (a*fb-b*fa)/(fb-fa);
fxr = f(xr);
n=0; present_root = xr; next_root = 0;

if fa* fb> 0 
    disp("initial values do not bracket the root");
else 
    disp('root using false position mehtod is as follos');
    fprintf('step \t a \t\t b \t\t xr \t\t fxr \n');
    while abs(next_root - present_root) > e
        fprintf('%d \t %f \t %f \t %f \t %f\n',n,a,b,xr,fxr);
        if fa*fxr<0
            b = xr;
            fb = f(b);
        else
            a = xr;
            fa = f(a);
        end
        present_root = xr;
        xr = (a*fb-b*fa)/(fb-fa);
        fxr = f(xr);
        next_root = xr;
        n= n+1;
    end
end

```

**Result:**

```matlab
Enter the value of a:  
1
Enter the value of b :  
5
Enter the error tolrent e: 
.001
root using false position mehtod is as follos
step 	 a 	    	 b 	       	 xr 		      fxr 
0 	 1.000000 	 5.000000 	 1.444444 	 -11.764060
1 	 1.444444 	 5.000000 	 1.832587 	 -10.175836
2 	 1.832587 	 5.000000 	 2.136150 	 -7.797057
3 	 2.136150 	 5.000000 	 2.351277 	 -5.406061
4 	 2.351277 	 5.000000 	 2.492483 	 -3.485446
5 	 2.492483 	 5.000000 	 2.580334 	 -2.141160
6 	 2.580334 	 5.000000 	 2.633124 	 -1.276150
7 	 2.633124 	 5.000000 	 2.664174 	 -0.746852
8 	 2.664174 	 5.000000 	 2.682206 	 -0.432416
9 	 2.682206 	 5.000000 	 2.692600 	 -0.248803
10 	 2.692600 	 5.000000 	 2.698564 	 -0.142642
11 	 2.698564 	 5.000000 	 2.701979 	 -0.081609
12 	 2.701979 	 5.000000 	 2.703931 	 -0.046636
13 	 2.703931 	 5.000000 	 2.705045 	 -0.026632
```

**Conclusion:**

The False Position method successfully approximates the root of the equation f(x) = x^3 - 4x - 9 = 0 to the desired tolerance of 0.001. The method converges more quickly than the Bisection Method for certain functions and provides an accurate root approximation after several iterations, making it a reliable and efficient technique for solving nonlinear equations.
