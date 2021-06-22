# ML-Regression
![ML](https://miro.medium.com/max/1000/1*VRbrA-5P0bs5qNseo-eU-A.jpeg )
Apply Linear regression model using python .
Regression analysis is one of the most important fields in statistics and machine learning .<br/>

Dataset source : https://www.kaggle.com/annetxu/health-insurance-cost-prediction<br/>

This project aims to analysis Impact of health insurance on user wallet and predict
medicine insurance cost , since there are factors that insurers consider when pricing
out their policies. Some of these criteria are outside your control, while others are
things you can remedy with simple lifestyle choices. are some factors that affect
how much health insurance premiums cost:
DATA OVERVIEW:<br/>
ATTRIBUTES :<br/>
•	age: age of primary beneficiary<br/>
•	sex: insurance contractor gender, female, male<br/>
•	bmi: Body mass index<br/>
•	children: Number of children covered by health insurance / Number of dependents<br/>
•	smoker: Smoking<br/>
•	region: the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.<br/>
•	charges: Individual medical costs billed by health insurance<br/>

**Using machine learning algorithms will benefit both insurance company and patient , where insurance company can use these algorithm for fast high
quality predictions , while for customer , they can have a better understanding of what will be taken from their budget and the cost difference, according to different factors.**

# Methodology
I tried to train the data using 4 models as following: 
-Linear regression : 
 - Linear regression without removing outliers :
the initial parameters of the model:
The coefficient values represents the mean change in the response given a
one unit change in the predictor ( age, bmi, sex , smoker, region , number of
children)
y = b0 + b1x1 + b2x2 + b3x3 + b4x4 + b5x5+b6x6
Intercept (b0): -14581.4050
coefficient: b1 = 258.528 , b2=48.359, b3=377.973, b4=439.127, b5=
23888.950 , b6=293.918
 - Linear regression after remove outliers :
- Logistic regression :Convert response variable as any value > 9596 will has class 1 (above cost
average) , while any value <= 9596 will has class 0 ( on or under cost average).
- Ensemble -bagging-:
fit several independent models-decision tree- and “average” their predictions in order to obtain a model with a lower variance.
by using ‘BaggingRegressor’ which is an ensemble meta-estimator that fits base classifiers each on random subsets of the original dataset and then aggregate their individual predictions to form a final prediction. We created 20 base estimators(decision tree )

# Analysis and conclusion
We know that unlike classification, accuracy in regression model is slightly harder to illustrate. It is impossible for you to predict the exact value but rather how close
your prediction is against the real value.so it make sense that the logistic regression model accuracy higher than simple linear regression, however ensemble accuracy
is good enough for our problem- if you interest about the true charges(continues value)- as well as it is higher than logistic . For the accuracy side, as it is shown
that ensemble is the best in performance (more accurate).

![Img2](https://user-images.githubusercontent.com/59575205/123013222-7edaf500-d3cc-11eb-8421-305e2f785269.png)
Now let me discuss the insights about the outliers , I trained the linear model without removing these outliers and train another linear model after removing
these outlier to see the performance and then  decide how to handle these outliers . The performance of the model after removing outliers
was very bad it is like a guessing model !! These outliers may occur since all the factors affect outcome is satisfied in those rows, let us explain this by plot shown
below :
![Img3](https://user-images.githubusercontent.com/59575205/123013426-df6a3200-d3cc-11eb-9e33-a6c0c482e2d5.png)
Take an example of these selected three point , you can see that the customer is smoker and his/her age is old this may cause the cost to be high as outlier! You
may ask okay what about other points of smoker and old? The answer is that there is other factors such as bmi , region or number of children that
may contributed to making the cost too high!


**What could be done to improve your models?**
The data is small , so increasing the number of data will improve the results .As
well as features , the features correlation with response variable is almost weak so
may adding new features will improve model performance.
