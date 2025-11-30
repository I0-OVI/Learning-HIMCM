# Data Collection and Analysis
### Reliable Resource
Kaggle is a very useful platform. Many projects would provide complete and clean dataset, which saves a lot of searching time. Alternatively, academic papers often list the source of the data in the reference section. However, in most of time, we are not fortunate enough to find this sort of dataset. 

How to address this? 
**CHATGPT** Press the button of online search and he will quickly produce candidate values and relevant reference. **BUT BE CAREFUL DO NOT USE THEM DIRECTLY**, in some cases, AI assistant would have illusion when lack of resource. What we should do is to open the link referred by the large language model and verify the validation of data. If the model requires many real-world parameters, we should have a part called data calibration in report. This section confirms the chosen values are reasonable and consistent with common sense. Alternatively, values should be marked with bracts like [1] in the text and properly cited in the reference section with their source.

**Case study**
[2022 Problem A](./problem/2022_HiMCM_Problem_A.pdf)
In this problem, teams are asked to predict population of one honey bee colony based on different factors such as lifespans, egg laying rates, fertilized/unfertilized egg ratios
First of all, I asked chatGPT for some data.

>Foraging bees typically make 7–13 flights per day, with an average of about 10 flights under favorable conditions, and each trip lasting roughly 30–45 minutes. A healthy colony in peak season commonly contains around 50,000 bees. These values provide a realistic baseline for modeling hive activity and foraging dynamics. However, because only a fraction of the colony actively forages at any given time and environmental factors such as flower availability, season, and weather strongly influence behavior, these parameters should be treated as approximate averages. Using them as input, the model can generate plausible estimates while acknowledging natural variability and the need for data calibration and sensitivity analysis.

Let's compare with *team #12821*'s data calibration.
>Each bee forage for food with 10 flights per day [17], so the average time of each flight is 0.1 days, $h=0.4$,$p=0.35$ [12], and $f$ is 20% [24]. The bee population N of a typical hive we selected is 60,000 since most of the blossoms occur in spring.
We calculate the value of $k$ by implementing the $H_{resource}$ and number of hives which is 51, into our model [12]. The value of $k$ we obtained is $4.17 × 10^{−5}$. Then, we utilize these parameters to calculate the number of hives needed for various types of crops in 81000 square meters.

In order to observe the difference, the following table could clearly illustrate the difference.
|Parameters                         |Values from chatGPT| Values from team calibration              | 
|-----------------------------------|---------------------------|-----------------------------------|
|Flights per bee per day            |8–12                       |10                                 |
|Duration per flight                |0.02–0.03 days (~30–45 min)|0.1 days (~2.4 h)                  |
|Hive population $N$                |40,000–50,000              |60,000                             |
|Nectar to honey production rate $h$|0.3–0.35                   |0.4                                |
|$\frac{\text{Amount of honeybee-produced-honey}}{\text{All the honey produced}}\; p$|0.25–0.3|0.35 |
|Population of foragers             |15–25%                     |20%                                |


### Data Generation