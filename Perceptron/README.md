## What is a Perceptron

A Perceptron is one of the simplest machine learning algorithms and is considered the basic building block of neural networks. It is a binary classifier, meaning it predicts one of two classes (for example: 0 or 1).

The perceptron takes several input features, multiplies each feature by a weight, sums them together, and then applies a decision rule to determine the output.

Mathematically:

![alt text](image.png)​

The perceptron learns by adjusting the weights whenever it makes a wrong prediction.

## Key Properties of Perceptron:

Works for binary classification problems

Creates a linear decision boundary

Learns weights using an iterative update rule

Only works well if the data is linearly separable

## Decision Boundary

The perceptron separates classes using a straight line (in 2D) or hyperplane (in higher dimensions).

Example decision boundary:
w1​x1​+w2​x2​+b=0

Points on one side of the line belong to one class, while points on the other side belong to the other class.

What We Did in This Notebook

In this notebook, we built a Perceptron-based classifier to predict student placement using two features:

CGPA

Resume Score

Steps performed:

Loaded the dataset using Pandas

Visualized the data using Seaborn scatter plot

Selected input features (cgpa, resume_score) and the target label (placed)

Trained a Perceptron model using scikit-learn

Extracted the learned weights and bias

Visualized the decision boundary using plot_decision_regions

The model learns a line that separates students who were placed vs not placed based on their CGPA and resume score.

## Perceptron Training – Simple Notes

1. What Happens During Training

When we train a machine learning model, the model learns by adjusting weights.

Two important things exist during training:

1. Weights
2. Learning rate

## 2. Weights

Weights tell the model how important each feature is.

Example:

If we have two features:

x1 = study hours
x2 = sleep hours

Model:

z = w1*x1 + w2*x2 + b

Where

w1, w2 → weights
b → bias

## During training:

weights keep changing

The model changes them to reduce prediction errors.

3. Learning Rate

Learning rate controls how big the weight update step is.

Example:

lr = 0.1

It means the model adjusts weights slowly and carefully.

Think of learning rate like step size when walking toward a goal.

## 4. Weight Update Rule (Perceptron)

The perceptron updates weights using this rule:

new weight = old weight + learning_rate _ (actual - predicted) _ input

In code:

weights = weights + lr*(y - y_hat)*X

Where

y → actual label
y_hat → predicted label
X → input features
lr → learning rate 5. Step Function

Perceptron uses a step function to make predictions.

if z > 0 → class 1
else → class 0

Where

z = w1*x1 + w2*x2 + b 6. Training Process

Training works like this:

1. Pick a data point
2. Calculate prediction
3. Compare with actual label
4. If wrong → update weights
5. Repeat many times

After many iterations, the model learns good weights.

7. What Stays Constant?

During training:

Learning rate → usually constant
Weights → keep changing

Goal:

Find weights that correctly classify the data 8. Final Result

The perceptron learns a decision boundary (line):

w1*x1 + w2*x2 + b = 0

This line separates the two classes.

Example visualization:

Class 0 | Decision Boundary | Class 1
● ● ● ● | line | ▲ ▲ ▲ ▲
● ● ● ● | | ▲ ▲ ▲ ▲
