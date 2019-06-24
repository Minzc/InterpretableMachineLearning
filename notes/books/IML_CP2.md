# Interpretable Machine Learning

Author: Christoph Molnar

Link: https://christophm.github.io/interpretable-ml-book/interpretability.html

## Chapter 2 interpretability

There is no mathematical definition of interpretability. Two (non-mathematical) definitions are Interpretability are

**The degree to which a human can understand the cause of a decision;**

**Interpretability is the degree to which a human can consistently predict the model’s result;** [1]

Note: Personaly, I prefer the second definition, which requires the interpretation to be re-usable. 

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

[1] https://christophm.github.io/interpretable-ml-book/interpretability.html
