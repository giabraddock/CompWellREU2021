# CompWellREU2021

## Ultimate Project Goal
**To build a machine learning model that takes fitbit data (steps, heart rate, and sleep data) and mental health survey data from healthcare shift workers as features and returns binary labels indicating whether or not an individual is at risk for burnout.**

## Motivation of the Project
Healthcare workers, nurses and doctors, on shift schedules work long hours in stressful environments. This results in physical exhaustion and sleep difficulties. In fact, one in five shift workers experience Shift Work Sleep Disorder (SWSD). These factors along with the pressure of the job lead to high burnout rates in healthcare workers. In conjunction with burnout, workers face impaired physical health and poor mental health, which often leads to higher error rates in hospitals. If we are able to use readily available technology to predict when shift workers may be at high risk for burnout, we may be able to intervene before it is too late.

## Project Data
The AMED dataset was collected between Rice University and Mei University in Japan. Data is being continuously collected for new participants since September 2018. The current data is separated into 5 batches. Batch 3 and 4, for example, consist of 14 total participants, 10 nurses and 4 doctors, with fitbit and survey data. In theory, each participant should have 35 days of data (1 week of pre-intervention scores and 4 weeks of trail data); however, many participants have less data due to errors with the fitbit and human error. 

Fitbit data was collected from a fitbit charge 3 with heart rate, sleep, and step raw data. Survey data was collected every day of the study and includes relevant features such as caffeine intake, alcoholic drinks consumed, method of wake, in addition to wellbeing markers assessed twice a day. These wellbeing markers ask participants to scale their happiness, alertness, energy, physical health, and relaxation from 0-100 in the morning and evening.

The study design included several general and specified mental health questionnaires to be completed at the beginning and end of the survey. These include the PSQI, GHQ, JESS, STAI, etc. We will be focusing on the JBS (Japanese Burnout Scale) which assesses participants risk of burnout on three different scales (exhaustion, depersonalization, and personal accomplishment).

Ultimately, we had 16 participants with complete fitbit, survey, and JBS data. 10 of these participants were at highrisk for burnout and 6 were at lowrisk for burnout.

## Features

Current fitbit features to explore include Heart Rate Mean, Standard deviation, and Entropy; Sleep Duration, Efficiency, Regularity Index, Start and Stop Times, and Sleep Restlessness; and Steps, NonActive and Active Entropy.

Current survey features to explore include Cups of Caffeine, Alcoholic Drinks, Wake Method, Shift Type, Work Regularity, Hours Worked, Over Time, "All Nighters", Time to Fall Asleep, and Wellbeing markers.

In Addition to the raw data, we computed 3, 5, and 7 day aggregate mean and standard deviation by summing over these time windows of time series data (fitbit features and wellbeing) and computing the mean and standard deviation over these windows. This feature extraction accounted for pockets of missing data and resulted in more consistent trends for features.

At the end of feature extraction, we had 122 features to select from

## Methods

We used logistic regression and random forest, two machine learning models that allow us to preserve interpretability. Interpretability is very important in biological machine learning as ultimately, we do want to know the "why" behind these phenomenons. 

We ran the logistic regression with a 5-fold stratified cross validation technique to help minimize bias to the highrisk class. We also ran user-independent models.

We normalized features by user in the logistic regression models using min-max scaling, and we also tried regularization with L2 on logistic regression and random forest.

## Results

Because the goal of the project was to minimize user input and predict burnout, the most successful model wasn't entirely dependent on accuracy. In addition to wanting high accuracy scores, we looked for features mostly, or entirely, extracted from fitbit data and we wanted to maintain a high recall score. Recall measures false negatives, which in the context of this data, means a participant at risk for burnout is mis-classified as low risk for burnout. The consequences of this mis-classification are quite high, and therefore, recall was a very important metric in evaluating different models.

The model that was "most successful" ran on 8 fitbit features only. It performed with 85.88% accuracy and had an F1 score of 89% (recall at 91%). It used the random forest algorithm (parameters: 500 trees, 2 features per tree, no max depth, trained on observations equal to the length of training data).

## Analysis

Random forest allows us to analyze feature importance by giving an entropy addback score between 0-1 for each feature. The higher the score, the better a feature is at distinguishing between classes. 

These are the features used, ranked by decreasing importance 
7 Day aggregate Heart Rate Mean, Heart Rate Mean, Steps, 3 Day aggregate Steps, InActive Entropy, 5 Day Standard Deviation of Sleep Duration, 3 Day Average Sleep Efficiency, Sleep Efficiency.

## Next Steps

This is an ongoing study, so we will continue to tune the model and make improvements as more data comes in.




