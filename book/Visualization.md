# Visualization
There is a very classic statement: if something could illustrate by the charts, you have better to use them instead of sentences. Since most of readers will find it difficult to follow the formula or the text, they will pay more attention to your charts or visualization. Also, text is not always powerful enough to show some slight or detailed change of models.
Since visualization is used throughout the report, I would share in the order of report.
Let's see a whole content from *Team #12821* for [2022 problem A](./problem/2022_HiMCM_Problem_A.pdf)
>**1 Introduction**
1.1 Background 
1.2 Restatement of Questions
1.3 Assumptions and Justifications
**2 Population model**
2.1 Variable
2.2 Baseline Model 
2.2.1 Model Setup
2.2.2 Allee effect
2.2.3 Critical and Maximum Sustainable Population
2.2.4 Parameter Calibration and Model Results
2.3 With Virus 
2.3.1 Model Setup
2.3.2 Parameter Calibration and Model Results
2.4 Seasonality
2.4.1 The Lifespan With Seasonal Change
2.4.2 The Fertility With Seasonal Change
2.4.3 Parameter Calibration and Model Results
**3 Sensitivity Analysis**
3.1 Baseline
3.2 Virus
3.3 Seasonality
3.4 Discussion
**4 Pollination Prediction**
4.1 Variables
4.2 Model
4.3 Values of Parameters
4.4 Number of hives for different crops 
4.5 Factors influencing foraging ability
4.5.1 Temperature
4.5.2 Air pollution
4.5.3 Use of pesticide
**5 Conclusion**
5.1 Strengths
5.2 Limitation
**Reference**

#### Introduction
This section has limited opportunities for visualization. The only thing we could do is to present our workflow, as shown below.
<img src="./picture/7.png">

<p align="center">
    <img src="./picture/8.png" width="80%">

Many of people underestimate the value of this sort of visualization. A clear workflow chart not only helps readers understand how your model is constructed and the relationship between each modules but also makes it easier for your team to manage progress during competition. Here are few suggestions when creating this graph. I recommend using an online editor such as draw.io since it was downloaded with editable png files which is very convenient when revision is required. Besides, the size of the texts is crucial. If labels are too small to read without zooming, the chart will lose its purpose and occupies the valuable place in your report. 

#### Data Analysis and Calibration
Some of the teams may present their model first since they want to capture the reader's attention by their innovated models. As a result, the data analysis and calibration part will be placed after whole model explanation part. This structure doesn't fully follow with the natural reasoning process of data-driven modelling. 

Imagine you are building a prediction model for a complex dataset. Here is a [sample table](./table/1.csv). The first step is always data washing. We may use the filters in the excel to check whether there are missing values. Alternatively, the python is effective when processing large dataset, since some csv files may contain too many rows which cannot be fully displayed in the excel. The common method is to fill missing values by the mode or the mean value. The next step is to identify some patterns between each feature. If you open the table above and examine it, you will notice that people who are transported tend to have a true value in column "CryoSleep". This kind of pattern will help you to choose model or verify the performance of the model. Would you think the next is to choose the model? You can but the model will not perform well since some of the features would be 'similar' which means their vector in n-dimension space are very close to each other. As the result, the model will perform unstably since the noise from similar features may be amplified. This issue could be addressed by feature engineering, which includes removing redundant features and constructing new features from the existing table.

So, you see. This is the overall workflow as well as the normal process of data modeling. 

#### Model Explanation
**Model Workflow** 
As shown in the following graph, the process of the model is demonstrated by the similar technique used previously. By observing the flowchart, all the complicated working is represented by the rectangles hiding the complexities/detailed information of model and shows the clear workflow with all relevant inputs and outputs.
<p align="center">
    <img src="./picture/9.png" width="70%">

**Data Change**

