# Diabetes Queensland

## Challenge 1: Type 1 Diabetes Diagnosis

Diagnosis of Type 1 Diabetes is often delayed. Because it is such a small percentage of the total population, it is not top-of-mind for General Practitioners.

How could technology be used to empower either General Practitioners or the General Public to diagnose Type 1 Diabetes when it presents?

## Challenge 2: Type 1 Diabetes Education

Most Type 1 Diabetics are diagnosed at a very young age - typically less than 10 years old. There is a lack of educational resources for them 

## Challenge 3: Type 2 Diabetes Prevalence

Are there patterns in the occurrence of Type 2 Diabetes by location? You might like to correlate occurrence with other datasets to see if you can make assertions about risk factors based on data.

## IoT Challenge for Diabetes

Many Type 1 Diabetics now have Continuous Glucose Monitors that produce data about the person's Blood Glucose Level - up to 280 data points per day.

There is a an open source project "[CGM in the Cloud](https://github.com/nightscout/cgm-remote-monitor)" that has a "Deploy to Azure" and "Deploy to Heroku" button on it.

There is no "Deploy to AWS" button.

Here are three challenges around these IoT devices:

* Create a "Deploy to AWS" feature 
  - At the moment users must configure a MongoDB on another provider to deploy CGM in the Cloud - can it be done as a one-stop shop with AWS?
  - Can it be deployed in the free tier of AWS?

* Create an opt-in "citizen data collection"
  - Allows users to choose to contribute to a Big Data dataset of anonymized aggregated data that can then be used by researchers and for machine learning.
  
* Can you add machine learning so that the program gives recommendations to users?


