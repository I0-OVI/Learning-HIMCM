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
|Parameters                         |Values from ChatGPT| Values from Team calibration              | 
|-----------------------------------|---------------------------|-----------------------------------|
|Flights per bee per day            |8–12                       |10                                 |
|Duration per flight                |0.02–0.03 days (~30–45 min)|0.1 days (~2.4 h)                  |
|Hive population $N$                |40,000–50,000              |60,000                             |
|Nectar to honey production rate $h$|0.3–0.35                   |0.4                                |
|$\frac{\text{Amount of honeybee-produced-honey}}{\text{All the honey produced}}\; p$|0.25–0.3|0.35 |
|Population of foragers             |15–25%                     |20%                                |

From the table above, *duration per flight*, *hive population* and *the nectar to honey production rate* is out of the range provided by chatGPT. So, it is clear that the value evaluated by chatGPT for most of time is broadly reasonable but we still have to check with published datasets or experimental research to ensure reliability and the realism of data.

### Data Generation
For some instances, the data is a little bit sensitive or there are few studies on current topics so that we could not get the whole dataset from website or even from the large language model. To address this issue, we could generate some data from the pattern we have observed. 
Here is an example from my team (*Team #25981207*) in [2025 IMMC E](./problem/2025_IMMC_Problem_E.pdf) 
>Wind Energy 
The power output by wind turbines is represented by:
$$P=\frac{1}{2}\cdot \rho A v^3 $$
Assuming an average wind speed of around 10 $ms^{-1}$ and efficiency of 40% for
modern wind turbines, a small windmill (100 − 200 $m^2$) can produce *7-8 kW*
continuously. A wind farm may contain tens or up to one hundred small windmills.

This problem asked us to create a power scheduling for a data center including both of electricity and computational power. This part illustrates how we estimate the power of wind turbines by starting from the general physical formula and then applying reasonable real-world assumptions supported by online resources. 

In later stages, we often need to generate synthetic data to thoroughly test the model. Random functions can be used to create a large amount of testing data, but it is important to define realistic ranges to ensure the generated data corresponds to actual conditions. For some of the test data, we should deliberately design the extreme or boundary values as this values could reveal the weaknesses or limits of current model. So, this may help us to identify pathway to optimize the model or find more suitable method for current problem.