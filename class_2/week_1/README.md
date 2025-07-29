# Neural Networks

aka deep learning, aka decision trees.

## Overview:

_Week 1:_ Neural Networks / predictions (inference).

_Week 2:_ Train your own neural network.

_Week 3:_ Practical advice for building ML systems.

_Week 4:_ Decision trees. Less hype but very powerful.

Neural networks:

-1950s tried, then fell out of favor

- 1980s/90s: hand-written digit information.
- fell out of fashion and then was rehyped around 2005.

Rebranded "deep learning". This name helped.

First application was speech recognition.
Then got into computer vision. "Image net moment" in 2012.
Then NLP.
Now they're used in so many things...

This does a simplified mathematical model of a neuron. Takes in some numbers, then does calculation, then outputs a number
to another "neuron".

Origins were biologically motivated, but nowadays it's really not very related to neurons but rather just a point of inspiration.

Possible now because of "big data" and faster processors including GPUs.

## Demand prediction.

Input is price.

<img width="1068" height="526" alt="Bildschirmfoto 2025-07-28 um 8 53 15 PM" src="https://github.com/user-attachments/assets/21d1533b-e12d-4a9a-8f3b-42319aa66fc8" />

So this is sigmoid from class 1.

A neuron is a tiny computer that takes in one number or a few numbers, and outputs 1 or a few numbers. In case above, it's probability the tshirt will be a top seller.

So maybe instead of taking in one (price), take in: price, marketing, material, shipping cost.

One neuron for "affordability". price and shipping cost

One neuron for "awareness", marketing

One for perceived quality that is connected to price and material.

Form a layer:

<img width="1067" height="530" alt="Bildschirmfoto 2025-07-28 um 8 58 55 PM" src="https://github.com/user-attachments/assets/2483f45a-00f0-49cb-9ada-fe04eb1f0406" />

Single neuron on the right is another layer.

Last is called output layer.

Within this, these are called "activations".

In above, they manually decided what neurons are input to all neurons.

In practice this is too cumbersome. So what is done is to do every value from previous layer:

<img width="1073" height="531" alt="Bildschirmfoto 2025-07-28 um 8 59 50 PM" src="https://github.com/user-attachments/assets/6c112d50-a847-45dc-855a-2589ba6bdf8e" />

This is all a neural network is.

Layer in the middle is called a "hidden layer". This comes from the fact that we have a training set. We have a data set, but we don't get the values for the intermediate layer.

<img width="868" height="535" alt="Bildschirmfoto 2025-07-28 um 9 04 32 PM" src="https://github.com/user-attachments/assets/518681c1-7795-4dc2-a4ac-e4e87a4d4e49" />

One way to think of this is just logistic regression, but ones that learn their own features to make more accurate predictions.

This means instead of us manually doing feature engineering, we can let the neural network do the feature engineering.

Can have multiple hidden layers.

<img width="1070" height="510" alt="Bildschirmfoto 2025-07-28 um 9 08 05 PM" src="https://github.com/user-attachments/assets/9aa0c73a-945d-43ca-9be1-ef44bd06ff20" />

We have to decide how many layers and how many neurons per layer.

**multilayer perceptron** is just the above.
