# Interpretable Machine Learning

Author: Christoph Molnar

Link: https://christophm.github.io/interpretable-ml-book/interpretability.html

## Chapter 2 interpretability

There is no mathematical definition of interpretability. Two (non-mathematical) definitions are Interpretability are

**The degree to which a human can understand the cause of a decision;**

**Interpretability is the degree to which a human can consistently predict the model’s result;** [1]

```
Note: Personaly, I prefer the second definition, which requires the interpretation to be re-usable. 
```

----

### Taxonomy of Interpretability Methods

#### Intrinsic vs. post-hoc

*Intrinsic interpretability* refers to machine learning models that are considered interpretable due to its simple structure.

*Post-hoc interpretability* refers to the application of interpretation methods to interpret the predictions made by machine learning models.

Results of the interpretation method

- Feature summary statistic: For example, feature importance and **pairwise feature interaction strengths**, which consist of a number for each feature pair. 
- Feature summary visualization: For example, partial dependence plots are curves that show a feature and the average predicted outcome.
- Model internal (e.g. learned weights): The interpretation of intrinsically interpretatable models falls into this category.
- Data point: **This works well for images and texts, but is less usefull for tabular data with hundreds of features**.
- Intrisically interpretable model: Approximate black-box models with an interpretable model, which can be interpreted by looking at internal parameters or feature summary statistics.

#### Model-specific vs. model-agnostic

*Model-specific*: The methods are limited to specific model classes.

*Model-agnostic*: The methods that can be used on any machine learning models. Those methods usually work by analyzing input feature and output pairs.

#### Local vs. global

*Local interpretation methods*: They can only explain the predictions on individual points.

*Global interpretation methods*: Those methods can explain the entire model behavior.

```
Note: How to generate meaningful data points as meaningful interpretations for the predictions made on tabular data?
```

### Scope of Interpretability

#### Algorithm Transparency

Algorithm transparency is about how the algorithm learns a model from the data and what kind of relationshpis it can learn.

#### Global, Holistic Model Interpretability

Those methods focus on answering the question about how the trained model making predictions. They explain the behaviors of models by analyzing their internal parameters.

#### Global Model Interpretability on a Modular Level

The internal parameters of some models are too complicated for human to understand. But those models can be understanded on a modular level, such as a single parameter of a linear model. The limittation of those methods is that the weights of some features only make sense in the context of the other features in the model.

#### Local Interpretability for a Single Prediction

When we look into an invidual prediction, the bahevior of the complex model might become easier to understand. Locally, the prediction might only depend linearly or monotonously on some features.

#### Local Interpretability for a Group of Predictions

Rather than only explain the predictions made on individual points, those methods try to interpret the predictions made on a group of points.


[1] https://christophm.github.io/interpretable-ml-book/interpretability.html
