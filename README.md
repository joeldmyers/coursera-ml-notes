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

Built on iPython.

`pip install jupyterlab`

and then run `jupyter notebook`

Notebooks will have ipynb. 