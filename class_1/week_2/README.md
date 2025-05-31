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

Behind the scenes, numpy is able to use parallel compute.

So `f = np.dot(w, x) + b`

Doing dot product: 

<img width="765" alt="Bildschirmfoto 2025-05-31 um 2 57 55 PM" src="https://github.com/user-attachments/assets/48748df9-c0d5-4421-aeca-85e1f65b376e" />

with numpy we can just do 

```
a = np.array([1, 2, 3, 4])
b = np.array([-1, 4, 3, 2])
result = np.dot(a,b)
```

this is better performance-wise than a for loop:

<img width="1016" alt="Bildschirmfoto 2025-05-31 um 3 00 18 PM" src="https://github.com/user-attachments/assets/661b9a43-250f-4562-8ae9-184589fcd562" />

Convention is to use m x n, m is rows, n is columns.

Numpy's basic data structure is an indexable, n-dimensional array containing elements of the same type (dtype).

So in these training models, training data contains m examples by n features.

We can make these m x n arrays the same way as above, just array of arrays: 

```a = np.array([[5], [4], [3]]);```

<img width="855" alt="Bildschirmfoto 2025-05-31 um 3 20 50 PM" src="https://github.com/user-attachments/assets/46c0ee18-4c04-4eca-a596-780bc2101676" />

How we would compute the cost in Python:

<img width="1006" alt="Bildschirmfoto 2025-05-31 um 3 24 51 PM" src="https://github.com/user-attachments/assets/fbbbdcb5-3aa3-4333-b520-a991ef8e96c8" />

So we compute the gradient, essentially writing the partial derivative calculations in Python: 

<img width="1015" alt="Bildschirmfoto 2025-05-31 um 3 27 36 PM" src="https://github.com/user-attachments/assets/0e25a047-05b9-40fc-b0e7-8adf4aeb3259" />

With multiple variables: 

<img width="919" alt="Bildschirmfoto 2025-05-31 um 3 28 51 PM" src="https://github.com/user-attachments/assets/68840017-7599-4641-aa9a-db9cc4fb47fe" />

I guess this algorithm takes in a number of iterations which I guess one has to set practically; there's no set way to set this apparently.