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