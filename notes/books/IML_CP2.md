# Interpretable Machine Learning

Author: Christoph Molnar

Link: https://christophm.github.io/interpretable-ml-book/interpretability.html

## Chapter 2 interpretability

There is no mathematical definition of interpretability. Two (non-mathematical) definitions are Interpretability are

**The degree to which a human can understand the cause of a decision;**

**Interpretability is the degree to which a human can consistently predict the model’s result;** [1]

```
Note: Personally, I prefer the second definition, which requires the interpretation to be re-usable. 
```

----

### 1. Taxonomy of Interpretability Methods

#### Intrinsic vs. post-hoc

*Intrinsic interpretability* refers to machine learning models that are considered interpretable due to its simple structure.

*Post-hoc interpretability* refers to the application of interpretation methods to interpret the predictions made by machine learning models.

Results of the interpretation method

- Feature summary statistic: For example, feature importance and **pairwise feature interaction strengths**, which consist of a number for each feature pair. 
- Feature summary visualization: For example, partial dependence plots are curves that show a feature and the average predicted outcome.
- Model internal (e.g. learned weights): The interpretation of intrinsically interpretable models falls into this category.
- Data point: **This works well for images and texts, but is less useful for tabular data with hundreds of features**.
- Intrinsically interpretable model: Approximate black-box models with an interpretable model, which can be interpreted by looking at internal parameters or feature summary statistics.

#### Model-specific vs. model-agnostic

*Model-specific*: The methods are limited to specific model classes.

*Model-agnostic*: The methods that can be used on any machine learning models. Those methods usually work by analyzing the input feature and output pairs.

#### Local vs. global

*Local interpretation methods*: They can only explain the predictions on individual points.

*Global interpretation methods*: Those methods can explain the entire model behavior.

```
Note: How to generate meaningful data points as meaningful interpretations
for the predictions made on tabular data?
```

### 2. Scope of Interpretability

#### Algorithm Transparency

Algorithm transparency is about how the algorithm learns a model from the data and what kind of relationships it can learn.

#### Global, Holistic Model Interpretability

Those methods focus on answering the question about how the trained model making predictions. They explain the behaviors of models by analyzing their internal parameters.

#### Global Model Interpretability on a Modular Level

The internal parameters of some models are too complicated for humans to understand. But those models can be understood on a modular level, such as a single parameter of a linear model. The limitation of those methods is that the weights of some features only make sense in the context of the other features in the model.

#### Local Interpretability for a Single Prediction

When we look into an individual prediction, the behavior of the complex model might become easier to understand. Locally, the prediction might only depend linearly or monotonously on some features.

#### Local Interpretability for a Group of Predictions

Rather than only explain the predictions made on individual points, those methods try to explain the behaviors of the models in a small local region. For example, the piecewise linear models behave consistently in each of its locally linear regions.

### 3. Evaluation of Interpretability

Doshi-Velez and Kim (2017) proposed three main levels for the evaluation of interpretability, application level, human level, and function level.

From the first to the last, the cost of the evaluation increases. The first evaluation level involves the experts to test the interpretations. Differently, the second level evaluation asks laypersons to evaluate the interpretations. The last level does not require humans. 

### 4. Properties of Explanation

***Accuracy*: How well does an explanation predict unseen data. This property is important for global interpretation methods. 

**Fidelity**: How well does the explanation approximate the prediction of the black-box model.

**Consistency**: How much does an explanation differ between models that have been trained on the same task the produce similar predictions? 

**Stability**: How similar are the explanations for similar instances? Stability compares the explanations between similar instances. High stability means that slight variances in the features of an instance do not substantially change the explanation.

**Comprehensibility**: How well do humans understand the explanations? Ideas for measuring comprehensibility include measuring the size of the explanation or testing how well people can predict the behavior of the machine learning model based on the interpretations. 

**Certainty**: Does the explanation reflect the certainty of the machine learning model. Most machine learning models give predictions with their confidences that those predictions are correct. 

**Degree of Importance**: How well does the explanation reflect the importance of features. For example, if a decision rule is generated as an interpretation, is it clear which of the conditions of the rules are the more important?

**Novelty**: Does the explanation reflect whether a data instance to be explained comes from a new region far removed from the distribution of training data. Novelty reflects the confidence of the interpretation methods on their computed interpretations.

**Representativeness**: How many instances are covered by an interpretation? Some interpretations can cover the whole dataset. While some can only cover individual points.

[1] https://christophm.github.io/interpretable-ml-book/interpretability.html
