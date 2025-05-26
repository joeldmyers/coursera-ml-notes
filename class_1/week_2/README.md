## Multivariate inputs. 

so we will use x<sub>1</sub>, x<sub>2</sub>, etc.

So x<sub>j</sub> where j is the total number of features.

So then we are going to have an array of arrays of data.

To indicate it's an array/vector rather than scalar we can do:

$\vec{v}$

Previously it was f<sub>w,b</sub>(x) = wx + b

now it's

f<sub>w,b</sub>(x) = w<sub>1</sub>x<sub>1</sub> + w<sub>2</sub>x<sub>2</sub> + w<sub>3</sub>x<sub>3</sub> + ... + b

<img width="706" alt="Bildschirmfoto 2025-05-26 um 1 58 34 PM" src="https://github.com/user-attachments/assets/488be466-d045-4136-8724-cad7ac3aa1ca" />

We can then describe these parameters as a vector, $\vec{w}$, to indicate all the individual parameters.

This is a row vector.

We can do the same for x, $\vec{x}$

So then we can do: 

f<sub>$\vec{w}$,b</sub>($\vec{x}$) = $\vec{w}$ ⋅ $\vec{x}$ + b

So this is dot product. Which is same as the longer one above but more compact.

The name of this is called **multiple linear regression**.

To implement this, we can do *vectorization*.

Note: these are 1-indexed. 

Numpy is linear algebra library.

Can do a dot product so it's more computationally efficient: 

<img width="939" alt="Bildschirmfoto 2025-05-26 um 2 10 32 PM" src="https://github.com/user-attachments/assets/479dd3d9-b274-4725-ab8d-67a77643ed0b" />

This runs much faster than having to sum it up using for loop etc.

Vectorization has two benefits: 

- shorter code
- code runs much faster.