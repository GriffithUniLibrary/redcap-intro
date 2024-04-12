---
layout: default
title: Calculated fields
parent: Instruments
nav_order: 4
---

# Calculated fields
{: .no_toc }

A calculated field can use previously submitted answers to calculate and display a value.

You can use calculated fields to determine values based on the values of previous fields. Here we will determine the participant’s age and body mass index (BMI) based on their date of birth and their height and weight.

## Calculate a participant’s age
{: .d-inline-block } 
Activity 
{: .label } 

1. Click `Add field`.
2. Choose *Calculated Field* for the `Field Type`.
3. In the `Field Label`, type Your age.
4. In the `Variable Name`, type *age*.
5. In the `Calculation Equation`, type: `datediff([dob],"2020-01-01","y")`

REDCap understands terms like ‘now’ and ‘today’, but they are not recommended for calculating age because they will lead to variation in values over time. This is why we select a set date such as January 1 or the project start date.
{:. .note }

## Calculate a participant’s BMI
{: .d-inline-block } 
Extra activity
{: .label } 

Here, we are going to use the 'height' and 'weight' values provided by the user to calculate their body mass index (BMI).

1. Click `Add field`.
2. Choose `Calculated Field` for the `Field Type`.
3. In the `Field Label`, type Your Body Mass Index (BMI).
4. In the `Variable Name`, type *bmi*.
5. In the `Calculation Equation`, type: `[weight]*10000/([height]*[height])`.

REDCap understands many calculation functions you might be familiar with from Excel, including IF() statements.
{:. .note }

Calculated fields cannot be tested in the Preview mode.
{:. .warning }
