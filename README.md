# CompWellREU2021

## Ultimate Project Goal
**To build a machine learning model that takes fitbit data (steps, heart rate, and sleep data) and mental health survey data from healthcare shift workers as features and returns binary labels indicating whether or not an individual is at risk for burnout.**

## Motivation of the Project
Healthcare workers, nurses and doctors, on shift schedules work long hours in stressful environments. This results in physical exhaustion and sleep difficulties. In fact, one in five shift workers experience Shift Work Sleep Disorder (SWSD). These factors along with the pressure of the job lead to high burnout rates in healthcare workers. In conjunction with burnout, workers face impaired physcial health and poor mental health, which often leads to higher error rates in hospitals. If we are able to use readily availabel technology to predict when shift workers may be at high risk for burnout, we may be able to intervene before it is too late.

## Project Data
The AMED dataset was collected between Rice University and Mei University in Japan. Data is being continuously collected for new participants since September 2018. The current data is separated into 5 batches. Batch 3 and 4, for example, consist of 14 total participants, 10 nurses and 4 doctors, with fitbit and survey data. In theory, each participant should have 35 days of data (1 week of pre-intervention scores and 4 weeks of trail data); however, many participants have less data due to errors with the fitbit and human error. 

Fitbit data was collected from a fitbit charge 3 with heart rate, sleep, and step raw data. Survey data was collected every day of the study and includes relevant features such as caffeine intake, alcoholic drinks consumed, method of wake, in addition to wellbeing markers assesed twice a day. These wellbeing markers ask participants to scale their happiness, alertness, energy, physical health, and relaxation from 0-100 in the morning and evening.

## Features

Current fitbit features to explore include Heart Rate Mean, Standard deviation, and Entropy; Sleep Duration, Efficiency, Regularity Index, Start and Stop Times, and Sleep Restlessness; and Steps, NonActive and Active Entropy.

Current survey features to explore include Cups of Caffeine, Alcoholic Drinks, Wake Method, Shift Type, Work Regularity, Hours Worked, Over Time, "All Nighters", Time to Fall Asleep, and Wellbeing markers.

## Methods
