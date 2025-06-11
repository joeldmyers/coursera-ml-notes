## Classification

Only a small handful of possible outcomes. 

Regression is not good for this.

*Logistic Regression* is the algorithm for handling classification.

Spam/not spam

If only two categories, it's "binary classification"

"class" and "category" same thing.

can denote this with 0 and 1. 

<img width="860" alt="Bildschirmfoto 2025-06-09 um 8 23 50 PM" src="https://github.com/user-attachments/assets/99b85cbb-f8c3-4aa3-8dc2-8beab654ba26" />

<img width="868" alt="Bildschirmfoto 2025-06-09 um 8 29 14 PM" src="https://github.com/user-attachments/assets/b11a6ff5-24aa-4775-ad09-4221970eafb9" />

Even though it has "regression" in it, it's about classification.

## Logistic Regression

Single most widely used classification algorithm in the world.

<img width="864" alt="Bildschirmfoto 2025-06-09 um 8 35 58 PM" src="https://github.com/user-attachments/assets/552d6fda-5967-40af-b818-588d4b809a7c" />

Will create an s-shaped curve to figure out boundary.

Requires "sigmoid function", aka logistic function.

<img width="860" alt="Bildschirmfoto 2025-06-09 um 8 37 33 PM" src="https://github.com/user-attachments/assets/72dd61c5-467a-49fb-863d-35e78704506d" />

E is a constant, it's about 2.7 (I knew this but it's been a minute :))

<img width="836" alt="Bildschirmfoto 2025-06-09 um 8 46 53 PM" src="https://github.com/user-attachments/assets/8c1ae14e-14a9-4173-acb7-33a338a989a4" />

Inputs features, outputs 0 or 1.

It can give a probability: 
<img width="845" alt="Bildschirmfoto 2025-06-09 um 8 47 58 PM" src="https://github.com/user-attachments/assets/43c05125-c0a7-47db-b023-a8032ca0384c" />

From lab: 

<img width="914" alt="Bildschirmfoto 2025-06-10 um 7 50 49 PM" src="https://github.com/user-attachments/assets/f269de46-4d61-45dc-a5ef-e88ec1bacb1b" />

Note what it says about z, this z is what we're targeting, it seems.

Other way of writing this: 

<img width="470" alt="Bildschirmfoto 2025-06-10 um 7 55 24 PM" src="https://github.com/user-attachments/assets/ae2fc42a-c3e3-45b7-ad78-8d9e9f9fe77f" />

So the whole point of this then is to figure out z.

So if we do this, we say if this g(z) = 1 / (1 + e<sup>-z</sup>) is >= .5 we say it predicts 1, otherwise do zero.

So we can then sort of derive down to other stuff. like use basic algebra to then sort of focus on the original vector linear etc. formula we've already been using.

So we're trying to get to a **decision boundary**

<img width="836" alt="Bildschirmfoto 2025-06-10 um 8 03 43 PM" src="https://github.com/user-attachments/assets/6680bf68-66d1-43ca-bea1-36782b7e6fd0" />

So to do this, we can look at a line exactly where z = w -> [dot] x -> + b = 0. 

This is the decision boundary. This is the "neutral" line. Since this resolves into .5 since it's 1 / (1 + e ^ 0) which is .5

<img width="838" alt="Bildschirmfoto 2025-06-10 um 8 06 43 PM" src="https://github.com/user-attachments/assets/8588ce81-2256-458f-a626-5d1057b10ce1" />

So it's plottying the two parameters. It's then:

x<sub>2</sub> = -x<sub>1</sub> + 3

to the left of this line it would predict 0, to the right it would predict 1.

### Nonlinear

<img width="842" alt="Bildschirmfoto 2025-06-10 um 8 10 15 PM" src="https://github.com/user-attachments/assets/0adaf0af-93bb-49cb-ba92-972011eab7cb" />

<img width="844" alt="Bildschirmfoto 2025-06-10 um 8 11 07 PM" src="https://github.com/user-attachments/assets/9f9a776a-7fb4-4e2b-8dae-01bb6fa72e4a" />

Cost function gives you a way to see how well it fits data. 

Turns out squared error is bad for logistic regression.

Example training set: 

<img width="789" alt="Bildschirmfoto 2025-06-10 um 8 30 34 PM" src="https://github.com/user-attachments/assets/96a23960-cd7f-43a4-8902-94b5d1da47a4" />

<img width="858" alt="Bildschirmfoto 2025-06-10 um 8 31 42 PM" src="https://github.com/user-attachments/assets/dea207d9-6435-44e2-8fc1-9e2dc855bafa" />

This is non-convex, a lot of local minima that gradient descent can get "stuck" in. So it's bad.

We can call this one unit within sigma notation as "loss" 

Need to re-review this tomorrow, getting a little sleepy. 

<img width="874" alt="Bildschirmfoto 2025-06-10 um 8 41 42 PM" src="https://github.com/user-attachments/assets/6fac5040-1795-4461-a7d9-f772239b0802" />

But this penalizes it for marking as 1 when it should be zero.

https://www.coursera.org/learn/machine-learning/lecture/0hpr8/cost-function-for-logistic-regression

This way it is reliably convex.

So this is it put all together: 

<img width="844" alt="Bildschirmfoto 2025-06-10 um 8 43 02 PM" src="https://github.com/user-attachments/assets/c2ccfd0d-b6b3-4af6-a08f-2a1a13d6ca99" />
