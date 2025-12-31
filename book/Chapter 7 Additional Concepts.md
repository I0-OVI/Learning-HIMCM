# Additional Concepts




#### Confusion Matrix
Accuracy alone is often insufficient to evaluate a classification model, especially when the dataset is imbalanced or when different types of errors have different consequences. To better understand how predictions differ from ground truth, we introduce the confusion matrix. The confusion matrix is a common tool used to compare a model’s predictions with the actual outcomes, shown as follow.
|                        |Positive (Prediction)| Negative     |
|------------------------|---------------------|--------------|
|**Positive (Reference)**|True Positive        |False Negative|
|**Negative**            |False Positive       |True Positive |

It is easy to understand the table. Take *False Negative(FN)* as an example, this occurs when the actual condition is positive, but the model incorrectly predicts it as negative. When improving a model, a common optimization goal is to maximize accuracy. However, depending on the scenario, other metrics such as **Recall** and **Precision** can also be used to guide optimization.
It is hard to use language to express the real meaning of them. I show them in math formulae:
$$ Precision=\frac{TP}{TP+FP}\;\; Recall=\frac{TP}{TP+FN} $$
**Precision** represents how many results are predicted to be positive where the labels are positive. And **recall** refers to how many results are predicted to be positive for all the positive labeled samples. Here, there must be some confusion. In precision, "labels are positive" means the prediction result is positive. In recall, "positive labeled samples" means the reference result is positive. The distinction can be confusing at first, but it becomes clear when you refer to the confusion matrix above.


#### Common model
**Analytic Hierarchy Process (AHP)**
In this part, we introduce a high-level scoring method called *Analytic Hierarchy Process (AHP)*. This method allows the integration of multiple perspectives from different experts on various factors, and generates a consistent and comprehensive weight system for the scoring process.