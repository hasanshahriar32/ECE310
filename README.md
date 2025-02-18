# Discrete Mathematics and Numerical Methods Sessional

| Experiment Number | Experiment Name |
|-------------------|-----------------|
| [Experiment No: 1](#experiment-no-1) | Finding the root of the function f(x) =5xlog10(x) – 6 using Bisection Method |
| [Experiment No: 2](#experiment-no-2) | [Add Experiment Name] |
| [Experiment No: 3](#experiment-no-3) | [Add Experiment Name] |

## Experiment No: 1

**Name of the Experiment:** Finding the root of the function f(x) =4*exp(-x)*sin(x)-1 using Bisection Method.

**Objective:** To find the root of the given function.

**Theory:** The Bisection Method is a numerical technique for finding the root of a function—a value of x where f(x) = 0. It is a bracketing method that requires two initial points enclosing a root. The method relies on the Intermediate Value Theorem, which states that if a continuous function f(x) on the interval [a,b] has f(a)⋅f(b) < 0, then at least one root exists in that interval.

**Apparatus:**

- A computer
- Matlab Software

**MATLAB Code:**

```matlab
clc; clear; close all;

 a= input('Enter the value of a:  ');
 b = input('Enter the value of b :  ');
 e = input('Enter the error tolrent e: ');
 f=@(x) 4*exp(-x)*sin(x)-1;

fa = f(a);
fb = f(b);
xr= (a+b)/2;
fxr = f(xr);
n=0; present_root = xr; next_root = 0;

if fa* fb> 0 
    disp("initial values do not bracket the root");
else 
    disp('root using bisection mehtod is as follos');
    fprintf('step \t a \t\t b \t\t xr \t\t fxr \n');
    while abs(next_root - present_root) > e
        fprintf('%d \t %f \t %f \t %f \t %f\n',n,a,b,xr,fxr);
        if fa*fxr<0
            b = xr;
        else
            a = xr;
    
        end
        present_root = xr;
        xr = (a+b)/2;
        fxr = f(xr);
        next_root = xr;
        n= n+1;
    end
end

```

**Sample Input and Output:**

```matlab
Enter the value of a:  
1
Enter the value of b :  
3
Enter the error tolrent e: 
.0001
root using bisection mehtod is as follos
step   a        b           xr        fxr 
0   1.000000   3.000000   2.000000   -0.507760
1   1.000000   2.000000   1.500000   -0.109715
2   1.000000   1.500000   1.250000   0.087555
3   1.250000   1.500000   1.375000   -0.007966
4   1.250000   1.375000   1.312500   0.040871
5   1.312500   1.375000   1.343750   0.016682
6   1.343750   1.375000   1.359375   0.004411
7   1.359375   1.375000   1.367188   -0.001765
8   1.359375   1.367188   1.363281   0.001326
9   1.363281   1.367188   1.365234   -0.000218
10   1.363281   1.365234   1.364258   0.000554
11   1.364258   1.365234   1.364746   0.000168
12   1.364746   1.365234   1.364990   -0.000025
13   1.364746   1.364990   1.364868   0.000071
>> 
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
step   a        b           xr         fxr 
0   1.000000   5.000000   1.444444   -11.764060
1   1.444444   5.000000   1.832587   -10.175836
2   1.832587   5.000000   2.136150   -7.797057
3   2.136150   5.000000   2.351277   -5.406061
4   2.351277   5.000000   2.492483   -3.485446
5   2.492483   5.000000   2.580334   -2.141160
6   2.580334   5.000000   2.633124   -1.276150
7   2.633124   5.000000   2.664174   -0.746852
8   2.664174   5.000000   2.682206   -0.432416
9   2.682206   5.000000   2.692600   -0.248803
10   2.692600   5.000000   2.698564   -0.142642
11   2.698564   5.000000   2.701979   -0.081609
12   2.701979   5.000000   2.703931   -0.046636
13   2.703931   5.000000   2.705045   -0.026632
```

**Conclusion:**

The False Position method successfully approximates the root of the equation f(x) = x^3 - 4x - 9 = 0 to the desired tolerance of 0.001. The method converges more quickly than the Bisection Method for certain functions and provides an accurate root approximation after several iterations, making it a reliable and efficient technique for solving nonlinear equations.

## Experiment No: 3

**Name of the Experiment:** Finding the root of the function (cos(x)+3)/2 using the Iteration Method.

**Objective:** To find the root of the equation (cos(x)+3)/2 using the Iteration Method with a tolerance rate of 0.00001.

**Theory:**

The Iteration Method is a numerical technique for solving equations of the form x=g(x), where g(x) is an iterative function. The idea behind this method is to begin with an initial guess x0 and repeatedly compute the next value using the iteration.

The method is used to approximate the root of the equation by iterating until the difference between successive values is smaller than the desired tolerance, indicating convergence.

**Apparatus:**

- A computer
- Python (or Matlab) software for computation

**Matlab Code**

```matlab
clc; clear;

phi = input('enter phi(x): ','s');
phi = str2func(phi);

xr = input('initial value (x0): ');
tol_err = input('enter the tolerent err: ');
n=0; next_root = phi(xr); present_root = xr;
fprintf("step \t xr \t xr+1 \n");
    
while abs(next_root - present_root)>tol_err
    fprintf('%d \t %f \t %f \n', n, present_root, next_root);
    
    present_root = next_root;
    next_root = phi(present_root);
    n=n+1;

    if n>50
        fprintf('iteration method fails to converge\n')
        break;
    end
end
fprintf('%d \t %f \t %f \n', n, present_root, next_root);
```

**Result**

```matlab
enter phi(x): 
@(x)  (cos(x)+3)/2
initial value (x0): 
1
enter the tolerent err: 
.0001
step   xr   xr+1 
0   1.000000   1.770151 
1   1.770151   1.400982 
2   1.400982   1.584500 
3   1.584500   1.493148 
4   1.493148   1.538785 
5   1.538785   1.516003 
6   1.516003   1.527383 
7   1.527383   1.521700 
8   1.521700   1.524538 
9   1.524538   1.523121 
10   1.523121   1.523829 
11   1.523829   1.523475 
12   1.523475   1.523652 
13   1.523652   1.523564 
>> 
```

**Conclusion:**

The Iteration Method successfully approximates the root of the equation x=cos⁡(x)+32x = \frac{\cos(x) + 3}{2} to the desired tolerance of 0.00001. This method converges when the iterative function g(x)g(x) is well-behaved and the initial guess is chosen appropriately. The final approximation of the root is found by iterating until the change between successive approximations is sufficiently small.
