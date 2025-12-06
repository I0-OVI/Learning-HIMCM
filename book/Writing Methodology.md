# Writing Methodology
1. Introduction
2. Model Explanation
3. Visualization
4. Sensitivity Analysis


### Introduction
**1.1 Background**
This part should *brief restate the problem* that posed by HIMCM. It should explain why problem is important and model is required. Also, you could give a brief conclusion of your model.
**1.2 Problem Restatement**
It seems to be similar to the Background part. But this part is asked you to fully list the *questions or tasks required by the problem*. It may include one question and a summary of related model.
**1.3 Assumption and Justification**
This section illustrate your assumptions while building the model. This because the model is theoretical which could not consider all the factor in the real world. 
Take an example: There is a problem about evacuation of firefighters in a building. If you want to simulate the behavior of them using a ABM (Agent-Based Model), you may ignore the destroy of construction of the building when rescuing. So, we have to write this in the assumption section and give a reason for why we ignore it. 

**Case Study**
[2024 Problem A](./problem/2024_HiMCM_Problem_A.pdf)
I take the above part from the outstanding paper (*Team #15926*)
This problem asked teams to choose several type of sports which will be added to next Olympic games. We have to build the model based on these factors:*Popularity and Accessibility*, *Gender Equity*, *Sustainability*, *Relevance and Innovation* and *Safety and Fair Play*. Let's start from **Background**.
>The Olympic Games have long served as the world's most powerful symbol of athletic
values and diversity. But as the dynamics of global sports and audience interest is
constantly changing, the International Olympic Committee (IOC) had been
continuously revising its evaluation process used to decide suitable sports, disciplines
and events (SDEs), so that tournaments can match with the role. In the 2024 Paris
Games, breaking made its debut, but the LA28 Games Plan also showed it would not
be included in the upcoming Olympics. This obviously reflects how evaluation criteria
changes rapidly, thus a sensible evaluation method that is able to accommodate the
changes is crucial to a successful Olympics.

This part is mainly about why the designed model is necessary to determine the SDEs to next Olympic games. Taking some real examples could make their model more realism. They have mentioned about the new SDEs appearing in the Paris Olympic and the influence of adding the specific SDE. 
### Model Explanation
There are various ways to illustrate models but we have to illustrate with clear logics. More importantly, you have to justify *why* choose this model. It does not come from the chat boxes from GPT but from the data pattern and your understanding of different models. You have to know the trade-offs of your model and explain its advantages, acknowledge its limitations, and show how you optimize these weaknesses later to build a more robust solution.

**Case Study**
[2022 Problem A](./problem/2022_HiMCM_Problem_A.pdf)
I take one of the outstanding paper's content of model explanation(*Team # 12821*).
```
2 Population model
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
```
In this problem, teams are asked to predict population of one honey bee colony based on different factors such as lifespans, egg laying rates, fertilized/unfertilized egg ratios. This represents standard workflow: starting with a primary model and then adding factors to model to meet the requirements. 
In section *2.2.2*, this team highlighted an essential principle: the **Allee effect**. This principle forms the theoretical foundation of their formulae and algorithms, so it has to be explained clearly and briefly in report. When our model relies on a scientific principle, we must introduce it and explain the relevance.

### Visualization
Since most of readers may find it **difficult** to follow the long formulae and text, visualization like charts and tables are crucial. Clear charts with concise explanation could significantly enhance understanding.
Taking one chart from outstanding paper as an example:
<img scr="./picture/1.png" width="60%">
|Version1|Version2|
|--------|--------|
|The curves for a large system (N=90,000) and a small system (N=1,000) converge over time. Despite different initial rates, they reach the same outcome after sufficient days. This indicates that long-term results are independent of system scale.|This graph compares process evolution for a large system (N=90,000) and a small one (N=1,000) over days. The large system changes slowly and smoothly, while the small one reacts quickly. System size clearly impacts the speed and path of the process.|

I wrote two versions of explanation above. Version 2 is the one usually written by beginners which focuses only on trend of chart and ignores stronger conclusion. In contrast, Version 1 highlights the convergence. What we should express is not just the values or trends, but the insights that directly support our conclusion.

This is for single model and if there are many models, we have to state the relationship between these models, such as providing input and output, or simple and enhanced model before we introduce the single models.

Maybe it is not obvious and there is another example.
<img scr="./picture/2.png" width="60%">
|Version1|Version2|
|--------|--------|
|By analyzing the niche overlap of each pet in the radar chart, several interesting pairing patterns can be observed. Cats and dogs show large overlapping areas in purchase cost and hygiene requirements, indicating that they are relatively compatible in terms of living conditions. Although hamsters and parrots are both small pets, their needs differ considerably—hamsters have low requirements for climate and space, while parrots demand much more in these aspects. The chart clearly shows that if a household can meet the needs of a dog, it can generally also meet the needs of a cat, providing useful guidance for families considering keeping both pets.| This radar chart displays the distribution of data for five types of pets across seven dimensions. From the data, dogs have the highest value (0.4) in community support and reach 0.3 in purchase cost. Cats perform prominently in both purchase and hygiene dimensions. Parrots show notably high values in the noise indicator, while hamsters have the lowest requirement for space. The indicators in the chart reflect the characteristic differences among species, and clear fluctuations exist across dimensions. Based on niche theory, the overlapping areas between species represent their degree of similarity, and we further explore the calculation of this similarity in the following sections.|

From above, version 2 focuses mainly on describing the data shown in the chart without drawing any conclusion. In comparison, version 1 emphasizes comparing different types of pets and deduce the reason behind this pattern.

From the two examples above, it is clear that charts should be used with a clear purpose which helps guide the reader and enhances understanding.

### Sensitivity Analysis
First of all, we have to distinguish sensitivity analysis and model application. Model application means we have many scenarios and we apply our model to calculate an output values that problem asked for. Sensitivity analysis aims to adjust the input by adding or minus 10% to original input to test whether our model will have a significant change to the output. If the change is small, the model is considered to be robust.
It is hard to explain what happens in this section. So I would give some examples.
As shown in the graph below, **bar error charts** are a commonly used method to illustrate the robustness of model. The narrower the error bars, the more robust the model. The line in the middle represents the mean value or baseline.
<img scr="./picture/3.png" width="60%">
Alternatively, we can use **tables** to show how the output changes after adjusting the inputs. I take a chart from *team #16159* in [2024 Problem A](./problem/2024_HiMCM_Problem_A.pdf).
<img scr="./picture/4.png" width="60%">
This problem asked teams to choose several type of sports which will be added to next Olympic games. In the figure above, only 3 sports swap rankings which is Handball, Football and sport climbing. The their original scores are very close, so slight changes in input would alter their orders. Let's see how this team explain this change.

>Even though our scores were changed slightly, the overall ranking remained largely the same. A ranking that is very sensitive to weighting changes would be volatile and unreliable for decision-making. Since our results are consistent even under different weightings, our model withstands change well and is shown to be robust, so it can be applied for use in Olympics decision-making.

They thought this is a small change which would not affect the final result. However, if the structure of ranking has shifted significantly, for example, rank 1 for E-cycling, rank 2 for Karate, rank 3 for Athletics, rank 4 for Basketball, this indicates that our model was sensitive to the change in input. In such a case, the model would need improvement to reduce sensitivity and ensure reliable results.