# Optimization-1-Numerical-Exercises
Welcome to "Optimization" This is the OLAT course corresponding to the Optimization 1 master course given by Prof. Dr. Michael Hinze with exercises given by Sema Coskun.

1. Descent algorithm implementation for rosenbrock function

Numerical Exercise 1: Implement the descent algorithm with dk = −rf (xk) and fixed
steplength tk = 0.00125 for the Rosenbrock function f : R2 ! R
f (x) := 100(x2 − x12)2 + (1 − x1)2.
Try at least 5 different starting points of your choice. As a termination condition use
krf (xk)k < 10−5

and don’t iterate more than 105 times. Visualize the iteration process.


2. Descent algorithm implementation for rosenbrock function with Armijo Steplegth

Numerical Exercise 2: Implement the descent algorithm for the Rosenbrock function
(as in Numerical exercise 1), with
a) dk = −rf (xk) and Armijo steplength tk ,
b) dk = −r2 f (xk)−1rf (xk) and Armijo steplength tk ,
c) dk = −r2 f (xk)−1rf (xk) and fixed steplength tk = 1 .
Start with x0 = (−1.2,1)> and use the termination condition
krf (xk)k ≤ εkrf (x0)k, with ε = 10−3.
As output, display the number of iterations, the norm of the gradient and the function
value of f . Visualize the iteration process in each case and compare the different cases.


3. (Minimal triangulated graphs)

Numerical Exercise 3: Compute the minimal triangular graph over Ω := (0, 1)2 , i.e find a function q : Ω¯ ! R , which is
piecewise linear and continuous on a given triangulation of Ω , and which satisfies the boundary conditions q|@Ω = 1/2 − |x2 − 1/2| , 
and whose graph has minimal surface area among all piecewise linear and continuous functions defined on the same triangulation and
satisfying the same boundary conditions.

Output: Surface area and a figure showing the triangulated graph.

Proceed as follows: Subdivide Ω into triangles (everything consists of triangles (Plato))
with corners Q1(x11, x21), .. .,Qm(x1m, x2m) . Consider functions q , which are continuous on
Ω¯ and linear on each triangle. Construct a function A : Rn ! R which defines the surface
area of the graph of q (what is n ?).

Solution algorithm: Steepest descent with Armijo step size rule:

  a) Choose x0 2 Rn , and β,γ 2 (0,1) ,
  b) for k = 0, 1,2, .. . do
    (i) rf (xk) = 0 ! STOP with x∗ = xk .
    (ii) sk := −rf (xk) ,
    (iii) σk := maxfσ > 0;σ 2 f1,β,β2, .. .gg : f (xk) − f (xk + σsk) ≥ −γσrf (xk)tsk
    (iv) xk+1 = xk + σksk
    
    Choose β = 12 , γ 2 [10−3,10−2] and stop if in b) (ii) kskk ≤ 10−8 is satisfied.
