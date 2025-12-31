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
In this part, we introduce a high-level scoring method called *Analytic Hierarchy Process (AHP)*. This method allows the integration of multiple perspectives from different experts on various factors, and generates a consistent and comprehensive weight system for the scoring process. The following chart could clearly show the process of this method.

<p align = "center">
    <img src="./picture/17.png" width="80%">

As for the detailed process, let's take the above charts as an example, we have four factors/criterion which determines the most optimal sport: H, P, F and S. Each expert may have different perspective to the importance of these criterions.For each matrix, diagonal elements are 1 (self-comparison), and off-diagonal elements are assigned values such as 3, 5, 7, 9 to indicate increasing importance, with reciprocals (1/3, 1/5, 1/7, 1/9) for the opposite direction. These matrices are combined to form the final comparing matrix by taking the geometric average, shown as following formula.
$$a_{i,j}^{combined}=(\prod_{k=1}^m \; a_{i,j}^k )^{1/m}$$
where $m$ represents the number of experts and k represents the index of the current expert whose score is being considered。
