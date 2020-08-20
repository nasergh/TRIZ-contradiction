# TRIZ-contradiction
1. **Comparing different feature importance of XGBOOST**

To understand which one of the feature importance of XGBOOST is better for detecting feature importance, we used Function 5 because it has 8 variables and the more complex relation between the variables. A1 to A8 are the important variables. We also use different sample size to see which of the importance feature of XGBOOST is more robust and accurate to explain function 5 important features.

In the figures **Fig. 1** to **Fig. 5** we check the robustness of different values or contribution of variables extracted from the model and we use bar chart of these contributions with the different sample size to see the behavior of these values with different sample size. We are looking for contribution that when we increasing the sample size, the contribution also increases. Indeed, as we give more data to the model, the model must give higher value of contribution to the important features. Also, we check that for A1 to A8 we need to see a downward trend in the value of features importance. Because A1 has the highest importance in actual function and A7 and A8 have the lowest degree of importance and we can understand this, from the function formula at first, output of the function is depending on A1 value and with only A1 we can change the output and it&#39;s not combined with other variables, second is A2 because it exist in 2 part of function, A2.A3 and A2.A4, and this two part only depending on one variable that why we can understand second most important variable is A2, third is A3 because it&#39;s exist in A2.A3 and A3.A5.A6, fourth is A4 because we find A2 and A3 then A4 will be remain on A2.A4, fifth is A5 because it&#39;s exist in two part of function A3.A5.A6+A4.A5.A7.A8, sixth is A6 because it&#39;s remain on A3.A5.A6, and seventh and eighth is A7,A8 but they seem to be same important in the function because they do not exist in another part of the function. We can see these situations in total gain and total cover figures, and that is not the case in weight, gain, and cover figures.

![](RackMultipart20200820-4-bs2205_html_b2c48fee46f9a1ea.jpg)

**Fig. 1.** Weight of each variable of XGBOOST with different sample size of function 5

In Fig. 1 we can see that with weight values when we increase the sample size, weight values also increase but it&#39;s not increasing systematically with the size of the sample. From A1 to A3 we can see values increased and from A3 to A8 it&#39;s decreased, but we looking for the feature contribution that has downtrend from A1 to A8 and that&#39;s not happened here.

![](RackMultipart20200820-4-bs2205_html_c3bc566132a768dd.jpg)

**Fig. 2.** Cover of each variable of XGBOOST with different sample size of function 5

In **Fig. 2** , we can it has positive correlation between the sample size and cover values because when we increase the number of sample, Cover value also increased, but it&#39;s not show us downtrend from A1 to A7 or A8, and we have pick value in A5, another things we can here is the cover values does not clearly discriminate the variables A1 to A8 from variables A9 to A20 when number of samples is small.

![](RackMultipart20200820-4-bs2205_html_c5f7dc60f271c8a0.jpg)

**Fig. 3.** Gain of each variable of XGBOOST with different sample size of function 5

In Fig. 3, we can see that sample size and gain value have positive correlation (i.e when we increase the sample size, gain also increased) and also the gain has a downtrend from A1 to A8 But the limitation of the gain measure is that, it gives good discrimination between the important variables of the function and the other variable, only from a fairly large sample size.

![](RackMultipart20200820-4-bs2205_html_ae0f5b02cd53d1b6.jpg)

**Fig. 4.** Total cover of each variable of XGBOOST with different sample size of function 5

In Fig. 4, shows that total cover and sample size have a positive correlation for the important variables A1 to A8 and also, we can see a clear discrimination between the important variables of the function with others even with small sample size (100). and there is a downtrend from A1 value to A8 value of total cover that why total cover seem to be good for feature selection.

![](RackMultipart20200820-4-bs2205_html_e68d527fcbd8f53c.jpg)

**Fig. 5.** Total gain of each variable of XGBOOST with different sample size of function 5

In Fig. 5, we can see a clear discrimination between the important variables of the function with others even with small sample size (100). and we also can see a positive correlation between total gain and sample size for the important variables A1 to A8, and also there is a downtrend from A1 to A8 value that shows that A1 is highest important variable and A8 is lowest one.

As we described, total gain and total cover can explain our feature important more accurately than the others, but still we don&#39;t know which one is better. For this purpose, we need to see these two from another point of view. For that we use line chart of these two values in Fig. 6 and Fig. 7 with different sample size to see which one can give the feature important (A1 to A8 for this function) with the smaller number of samples.

![](RackMultipart20200820-4-bs2205_html_a7b90651700be248.jpg)

**Fig. 6.** Total Cover of each variable of XGBOOST with different sample size of function 5

![](RackMultipart20200820-4-bs2205_html_567b501e4bb16c8d.jpg)

**Fig. 7.** Total gain of each variable of XGBOOST with different sample size of function 5

In Fig. 6, variables A1 to A8 come to highest ranking in 700 samplings but in Fig. 7 they already come up with 500 samplings. It shows that in this example, total gain requires 200 less samples than total cover for detecting the right important features. Moreover, when looking at the value of each variable with different sample size it can be seen that the robustness of total gain is much better than the total cover because the order of A1 to A8 from 500 sample to 2000 sample is not changing. But in total cover, A6, A7 and A8 ranking is still changing with different sample size within the 500 to 2000 range. From now because total gain shows the feature important better than others, we use total gain of XGBOOST to extract the feature important from the model.

  1. **Comparing XGBOOST with SVM**

For comparing the result of XGBOOST with SVM we use total gain of XGBOOST and weight of SVM as &quot;parameter importance&quot; measure. For the comparison we use two types of figures, the line chart of features importance as we used it in the previous section, and we use box plot to show the behavior of parameter importance values with different sample size to see the minimum, maximum, and standard deviation of parameter importance around the median to see the range of values.

### **Case of function 5**

provides this comparison of Function 5 to see with how many number of samples, variables A1 to A8 will become to the important features

![](RackMultipart20200820-4-bs2205_html_82d126152a4744fd.jpg)

**Fig. 8.** SVM weights with different sample size of function 5

![](RackMultipart20200820-4-bs2205_html_9a0bf344ea976eb4.jpg)

**Fig. 9.** SVM weights range with different sample size from 100 to 2000 of function 5

![](RackMultipart20200820-4-bs2205_html_fd31768548d4cbb7.jpg)

**Fig. 10.** XGBOOST total gain with different sample size of function 5

![](RackMultipart20200820-4-bs2205_html_86af87edca9ecef6.jpg)

**Fig. 11.** XGBOOST total gain with different sample size from 100 to 2000 of function 5

with Comparing the Fig. 8 and Fig. 10, we can see that XGBOOST detect the important variables from 500 samples or experiments and important feature comes to top ranking of values, while SVM is require 800 sample to give the same result.

In Fig. 11 the values of unimportant features (A9 to A20) are very close together because the standard deviation is very low while in Fig. 9, some expected unimportant variables like A12, A18, etc. have a big standard deviation, it shows that SVM can&#39;t detect useless variable and remove them from the model.

### **Case of function 1**

results of Function 1 are shown below. Let&#39;s remind that the algorithm must find A1 and A2 as important features.

![](RackMultipart20200820-4-bs2205_html_d408dd1724288825.jpg)

**Fig. 12.** SVM weights with different sample size from 100 to 1000 of function 1

![](RackMultipart20200820-4-bs2205_html_83ea17512e58624a.jpg)

**Fig. 13.** XGBOOST total gain with different sample size from 100 to 1000 of function 1

As you can see in these two figures, both algorithms can detect the important features very well, but for unimportant features (A3 to A20), XGBOOST does a better job because values of feature importance in XGBOOST is more stable with different sample size and minimum, maximum of values are near to zero.

### **Case of function 2.**

The results of function 2 are provided bellow, as we know A1, A2, and A3 are the important features of function 2, as you can see both can detect the feature important very well, but XGBOOST value for unimportant variables are near to zero and it seems more robust to noise.

![](RackMultipart20200820-4-bs2205_html_6cf71e962e87732d.jpg)

**Fig. 14.** SVM weights with different sample size from 100 to 1000 of function 2

![](RackMultipart20200820-4-bs2205_html_86dfc044e61c802d.jpg)

**Fig. 15.** XGBOOST total gain with different sample size from 100 to 1000 of function 2

### **Case of function 3**

For the Function 3, A1, A2, A3, A5, and A7 are the important variables. from the function we know that A5 is most important feature and other are have similar effect on output of the function, the results of the measures are provided on the Fig. 16 and Fig. 17. both algorithms can detect A5 as most important variable but result of XGBOOST is more robust to the noise and also with different sample size unimportant variables stay at zero point and variables A1, A2, A3 and A7 have a same standard deviation, maximum and minimum in compare to the SVM.

![](RackMultipart20200820-4-bs2205_html_4b7136182404c87f.jpg)

**Fig. 16.** SVM weights with different sample size from 100 to 1000 of function 3

![](RackMultipart20200820-4-bs2205_html_c6b93a1a87e41ff2.jpg)

**Fig. 17.** XGBOOST total gain with different sample size from 100 to 1000 of function 3

### **Case of function 4**

Now let&#39;s check the function 4, it&#39;s the one with the highest imbalanced data in our research examples, this function is a challenge because number of data for each class is highly imbalanced. in the best scenario of sampling there will be 4 samples of class #1 and other data are belong to the class #0. and variables A1 to A10 important variables and all of them are &#39;and&#39; together and it seems that it&#39;s hard for models to find this relation with a few numbers of samples.

![](RackMultipart20200820-4-bs2205_html_a8c7b56757b20052.jpg)

**Fig. 18.** SVM weights with different sample size from 100 to 1000 of function 4 ![](RackMultipart20200820-4-bs2205_html_2ad532846f4c5612.jpg)

**Fig. 19.** XGBOOST total gain with different sample size from 100 to 1000 of function 4

As you can see in Fig. 18 and Fig. 19 both algorithms can&#39;t detect the most important variables very well, because with high number of samples it&#39;s easy to discriminate the important and unimportant variables, but with how many number of sample we can trust to the result is a question, Our solution for this problem is to use a measure to check the performance of the model and then choose the important variables of the model when we have good performance on test data and we will discuss about this in the next section.
