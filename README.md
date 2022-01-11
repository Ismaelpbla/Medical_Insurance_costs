
# Medical Insurance Costs project

This is a learning project from Codecademy. Where are going to analize the medical insurance costs of 1338 inputs.

I am going to use Exploratory Data Analysis to investigate wich ones of the variables have the most incidence in the medical charges.
After this exploration I found that  variable smoker has the most incidence both alone and with other variables like bmi. 



## Authors

- [@Ismaelpbla](https://www.github.com/Ismaelpbla)


## DATA

To do our first data analysis project we will use the data provided by codecademy:insurance.csv

First we are going to do a first view of the data contained in this csv file

| id  |age  | sex   |bmi   |children   |smoker   |region   |charges   |
|---|---|---|---|---|---|---|---|
| 0  |19   | female  |27.900   |0   |yes   |southwest   |16884.92400   |
|  1 |  18 |   male|33.770   |1   |no   |southwest   |1725.55230   |
|   2|   28|   male|33.00   |3   |no   |southwest   |4449.46200   |


The information provided in the table indicates:
- age: the age of the person paying for insurance
- sex: the sex of the person paying for insurance
- bmi: the person's body fat index
- children: number of dependent children
- smoker: whether or not the person is a smoker
- region: the region of the U.S. to which the person belongs
- charges: Amount the insurer charges the individual

## METHODS

We will use the exploratory statistical data analysis (EDA) method. Making a first analysis of each of the variables, and subsequently seeing the relationship between them.

- Analysis of quantitative variables: Kde method and Boxplots.
- Analysis of qualitative variables: Countplot method and Histograms.
- Relationship between quantitative and qualitative variables: Method Lmplot, Violin plots
## ANALYSIS

The quantitative variables of this project are: bmi and charges. The kde method was applied to them and the following results were obtained
#### Figure A
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/kdeplot.png)

As can be seen in the figure, the distribution of bmi is completely normal while that of charges presents an asymmetry, due to the presence of outliers as can be seen in the boxplots.

The qualitative variables of the project are: sex, smoker, region, age and children.

The first three have been projected using bar charts with the countplots method.
#### Figure B
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/30f03294866592c7d06d106013ca365eaeb948c2/Figures/countplot.png)

In this case it can be seen that in our database there are more people from the southeast region, that the proportion of men and women is similar and that the proportion of smokers is significantly higher than that of non-smokers.

The other qualitative variable: age has been projected through a histogram.
#### Figure C
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/6388dcca73616fe1ff045287ebc8cfdc906b9513/Figures/histogram.png)

In these figures it can be seen that the age ranges are very diverse but that above all the young population around 20 years of age stands out. On the other hand, there is a large number of people without children, although the number of people who have 1, 2 or even 3 children is not negligible. The percentage of people with 4 or more children is very small.

### Relationship between variables

As we have seen when projecting the charges variable, there are people who pay a higher rate for their insurance than others. If we look in detail at the outliers of this variable:
#### Figure D
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges_outliers.png)

In the figure D you can see, first on the left a zoom of the right part of the figure A. The following graph is the result of eliminating all values lower than 30000 to show only the extreme values of charges. Finally these values have been projected on a boxplot.

As can be seen in the figure the distribution of the charges outliers have a normal distribution. Thus we could treat them as a separate group, a group of people who pay more for their insurance (Group B). The question is why, let's see by comparing the different qualitative variables in the two groups.
#### Figure E
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/countplot2.png)


In this figure (Figure E) you can see differences in the distribution of the qualitative variables in the two groups we have defined:
- The age distribution is similar but it seems that there are two age groups between 40 and 50 years and over 60 years which is more frequent in Group B than in A.
- In group A there is greater parity (similar number of men and women), which is not the case in the group B where there are more men than women.
- One of the variables in which the greatest difference is observed is that of smoker. The number of smokers in group A is very small compared to the number of non-smokers, while in group B the opposite is true.
- In the first group the number of people from different regions is fairly well distributed. In the second case there is a larger number of people from the southeast.
- In the case of children, the distribution is similar in both groups, although in group B there are more people with 2 children than with 1.

If we make a comparison with violinplots we will obtain more information if possible:
#### Figure F
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/violin_plot2.png)

- No significant differences are observed when comparing the gender distribution in both groups.
- Again, there is a notable difference between the number of smokers in one group and in the other. In group B it should also be noted that non-smokers do not present values very far from the mean and median. While smokers do. This means that non-smokers, regardless of the other variables, tend to pay the same, while smokers have greater variability in what they pay.
- It is curious how in group B a bimodal distribution can be observed for people living in the southwest region, something that is not seen in the rest of the regions.
- The distribution of the number of children with respect to the charges is more or less normal except in the case of people without children in group A. In this case we see a clear bimodal arrangement.

Finally, we will see how the two quantitative variables: bmi and charges, are related. To do this we will project two graphs, one for group A and one for group B:
#### Figure G
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges%20vs%20bmi%20standar.png)
#### Figure H
![alt text](https://raw.githubusercontent.com/Ismaelpbla/Medical_Insurance_costs/main/Figures/charges%20vs%20bmi%20outliers.png)

In the figure above we have projected the bmi and charges values for group A, in the figure below we have projected the same for group B.
However the information we get from these figures is not entirely relevant, until we project a third variable: smoker. When we do this we see two things:
- That in group A there are two concentrations of points some (smokers) pay significantly more than the others (non-smokers). In both, the more body fat (bmi) you have, the more you are going to pay, since there is a positive correlation in both lines. However, the line that defines the relationship between charges and bmi has a greater slope in the group of smokers than in the group of non-smokers.
- That group B is mostly composed of smokers and has a positive relationship between bmi and charges. Note that although there are few non-smokers and the population is therefore not significant, the slope of the line is similar to that obtained in the previous group.


## CONCLUSIONS

The analysis of the data leads us to several conclusions. The first, and most obvious, is that not everyone pays the same for their insurance. But not only do we know that from the data, we also know that there are a number of people who pay significantly more than the rest. And in fact we have seen that in figure A and figure D.

The question that this raises is why does this group of people pay more than the rest? For this, and through the comparisons of the different variables between the group that pays more (Group B) and the group that pays less (Group A) (figures E and F)
it can be seen how, despite the observable differences in all the variables, the one that stands out the most is the smoker variable. In fact, this variable is practically opposite in one group and in the other, i.e., while in one group the majority are non-smokers, in the other they are smokers.


This does not end here, but we can also see how the fact of being a smoker or not also has a significant influence on what you pay, especially if your body mass index (bmi) is high (figure g).

Why is there a group of people who pay significantly more than others? The answer is that, although other variables such as the number of children or age increase the price of insurance, it is the smoker variable that most influences the price.
In fact, as can be seen in Figure H, most of the people in the group that pays the most are smokers.

The influence of the smoker variable is such that when other variables such as bmi are added, it can be seen that a smoker will pay up to twice as much as a non-smoker with the same bmi.
