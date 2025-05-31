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

For each iteration, it essentially calculates the partial derivatives and takes a small step down. It appends the cost function for debugging / observation purposes.

## Feature Scaling

We want to "scale down" features so they're not like huge. Like, house size is from 300-2000 feet, and number of bedrooms is from 0-5. So they're not really scaled well.

Example: House size 2000, number of bedrooms is 5, price is 500,000. 

This will make things difficult. 

We fix this by "scaling" the data so that all parameters have a range of 0 to 1.

<img width="1202" alt="Bildschirmfoto 2025-05-31 um 3 46 53 PM" src="https://github.com/user-attachments/assets/afb674ea-4373-46df-aa89-c8fbcf3c5c52" />

One way to do this is to divide by the max of the range.

We can also do *mean normalization* - center the data around zero.

So this would be x<sub>1</sub> = (x<sub>1</sub> - μ<sub>1</sub>) / (max - min) where μ is the mean.

A third way of doing this is to calculate a z-score normalization. This uses standard deviations.

<img width="1186" alt="Bildschirmfoto 2025-05-31 um 4 04 26 PM" src="https://github.com/user-attachments/assets/262c7579-3126-4675-a98f-1c74d5292636" />

Generally we want to get around -1 to +1. But it doesn't have to be exact. -3 to +3 or -.3 to +.3. 0 to 3 is ok.

How do you know if it's actually working?

Graph the output. 

<img width="1193" alt="Bildschirmfoto 2025-05-31 um 4 13 41 PM" src="https://github.com/user-attachments/assets/11de95ed-7b86-4c9a-ac5c-345e6987d1be" />

x is number of iterations. y is the cost. 

This is also called the learning curve.

If it's working properly, it should always be *decreasing* after every iteration.

If it's *increasing* it may be that alpha is too large or there's a bug.

The number of iterations needed may vary a ton - maybe 30, maybe 1,000, maybe 100,000. So the learning curve is important for helping learn.

We can also do an "automatic convergence test"

let ε be 10<sup>-3</3> so if J(w->, b) decreases by <= ε in one iteration, say we're done.

<img width="1204" alt="Bildschirmfoto 2025-05-31 um 4 29 27 PM" src="https://github.com/user-attachments/assets/46cbbcb9-6455-47e2-905b-90e5d85e8c02" />

Maybe for alpha, try .001, then .01, .1, and 1.

