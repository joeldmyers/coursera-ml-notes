# coursera-ml-notes

Following along with https://www.coursera.org/specializations/machine-learning-introduction

## What is machine learning?

A field of study that gives computers the ability to learn without being explicitly programmed.

Arthur Samuel - checkers playing game (1959). 

Class will cover:
 - supervised learning 
 - unsupervised learning
 - recommender systems
 - reinforcement learning

Supervised learning is most used.

First two courses will focus on supervised learning.

## Supervised Learning

99% of economic value created today is from supervised learning.

This refers to algorithms that learn x to y, or input-to-output mappings.

Key characteristic is that you give learning algorithm examples that include the right answers - correct label y for a given input x. By seeing correct pairs of input x and desired output y, where it then learns to infer y from new x'es.

Example: 

Input: email. 
Output: is spam or not?

Input: audio
Output: text transcript

Input: English
Output: Spanish

Online advertising: 

Input: Ad, user info
Output: will click (0/1)

Image / Radar Info -> position of other cars

Image of phone -> defect (0/1): visual inspection. reduce or prevent defects in products.

In these, we first train model with inputs x and outputs y that are known. 

### Regression Algorithms

Gives example of housing prices based on size of house. Create a line of best fit that then allows for prediction of unknown price based on house size. (linear regression).

If we use a polynomial vs linear it has big impacts. So how do we choose the most appropriate line or curve for the data?

There is a second type of supervised learning problem, which is classification.

### Classification Algorithms

Ex: breast cancer detection. Is tumor malignant or benign.

Maybe data set has tumors of various sizes. They are labeled as benign or malignant.

Can do prediction of size vs binary (malignant or benign). It could be put on a graph but only two possible outcomes.

Because only two possible outputs, Can denote on a line. Circle/O for benign, cross for malignant.

Can do more than two categories.

"class" or "category" are interchangeable.

In summary, classification algorithms predict categories. E.g., picture cat or dog?

Can also have more than one input. For cancer example, can use age and tumor size. 

ML algorithm could find some boundary that separates malignant from benign. 

Supervised learning learns from "right answers".

Regression / classification are two main types.

## Unsupervised Learning

It's *unlabeled* data rather than with supervised learning, which has *labeled* data. 

You ask it to find "something interesting" in unlabeled data. **Clustering**.

News: group related stories together.

DNA: microarray. 

Grouping customers into market segments.

### More formal definition of unsupervised learning

Data comes only with inputs x but no output labels y.

Algorithms have to find *structure*.

Clustering: groups similar data points together.

Other is called *anomaly detection*. Important for fraud detection.

*Dimensionality reduction*: compress a very large data set into a small, more manageable data set.

## Jupyter Notebooks

I watched this to supplement this: https://www.youtube.com/watch?v=5pf0_bpNbkw

Built on iPython.

`pip install jupyterlab`

and then run `jupyter notebook`

Notebooks will have ipynb. 

Can do Jupyter Lab instead of Jupyter Notebook

Can run in cloud: 
- Google Colab: https://colab.research.google.com/
- Kaggle: https://www.kaggle.com/code

### Keyboard shortcuts

Shift + Enter -> Run cell. Takes you to next cell. 

Control + Enter -> Run cell and stay in cell.

When working in cell and want to go to other cell, hit escape. use j and k keys. 

Add and remove cells: 

a is add cell above.
b is add cell below.

dd -> delete.

change between md and code: type m for markdown. y for code.

## Random notes from this: 

https://www.youtube.com/watch?v=_xIwjmCH6D4 

1. Python basics
2. Why Machines Learn: Anil Ananthaswamy
3. Andrew Ng ML specialization
4. Andrew Ng Deep learning specialization
5. CS25 Transformer Architecture
6. Andrej Karpathy YT all videos
7. Understanding Deep Learning Simon prince (for theory research top dense work)
8. Numpy/panda/matplotlib/pytorch/tensorflow/jax/sckit learn -> kaggle begginer projects
9.  Reading Research paper
10. show ur work & projects (linkedin/blog post/research paper submit)

## Linear regression models

Size and price.

This simple linear regression is considered a "supervised learning model". 

Classification is finite set of outputs.

Can also do data table. 

*Some Terminology*

Data set used to call a model is called a **training set**.

x is input variable feature
y is output variable feature
m is number of training examples.

so (x,y) is for example (2104,400) 

so this is (x<sup>(i)</sup>, y<sup>(i)</sup>)

Not exponentiation. Parentheses important. Wonder why they didn't do subscript but whatever.


### Linear regression with one variable

`f` is function. used to be called hypothesis. Used to take in x and generate output ŷ (y hat). 

In ML, convention is that ŷ is the estimate.

x is called input feature.

ŷ is prediction (estimated y).

if it's y it's the actual true value. ŷ is estimate that may or may not be accurate true value.

f<sub>w,b</sub>(x) = wx + b

This linear regression approach is simplistic but a good place to start.

Side note, scalar is single value, vector is ordered array of numbers.

W is for weight, b is for bias.

NumPy is a popular library for scientific computing
Matplotlib is a popular library for plotting data

## Cost function

Tells us how well the model is doing.

w and b are *parameters* of a model. They can also be referred to as *coefficients* or *weights*. 

Cost function takes ŷ - y: this difference measures the error. 

 J(w,b) = (1/2m) * $\sum_{i=1}^{m} (ŷ^{(i)}- y^{(i)})^2$

 This is the sum of the squares of the "error" or difference between hypothesized y value (ŷ) and actual y value (y) for each ith iteration.

 m is the number of training examples. 

 So we do the average. But divided by 2. It just makes calculations easier.

 This is called the squared error cost function.

 There are different cost functions. But squared error cost function is the most common.