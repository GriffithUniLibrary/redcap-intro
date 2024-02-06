---
layout: default
title: Basic questions
parent: Instruments
nav_order: 2
---

# Basic question types
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

We will use the first instrument to try out some basic question types by adding some demographic questions.

## Text box

In REDCap, the `text box` question type can be used in several ways: to capture short and long written responses, but also to capture information like numbers and dates. Here we will just capture our participant's name.

### Add a basic text field

1. Click on `My First Instrument`
2. Click `Add Field`
3. Choose `Text Box`
4. In the `Field` Label, type *Family Name* (this gets displayed to your participants)
5. In the `Field` Name, type *name_family* (this gets stored as a column header in your database)
6. In the `Required` field, select “Yes”.
7. In the `Identifier?` Field, select “Yes”. (Identifiable information can be flagged to restrict it from export.)
8. Click `Save`.
9. Repeat the process to add the field Given Name (name_given)

{% include accordion.html title1="Activity: Add a basic text field" text1=buildform open=true %}

## Multiple choice

Multiple choice fields are of two kinds:

- `Radio buttons` and `drop down lists` only allow the participant to select a single option from a list. 
- `Checkboxes` allow participants to select any number of items from a list.

### Add a radio button question

1. Click `Add field`
2. Choose `Multiple choice - Radio buttons` from the drop-down list.
3. Type *Gender* in the `Field` Label and *gender* in the `Variable Name`.
4. Add the following options: *Male, Female, Intersex, Unspecified*.

{:. .note-title}
> About raw values
>
> The ‘raw value’, which appears before the column, is the value that gets recorded to your data. Thus your recorded value can be numeric, or a single letter code, while the participant can read a fuller description.

### Add a checkbox question

3. Click `Add field`.
4. Choose *Checkboxes (Multiple Answers)* for the `Field Type`.
5. In the `Field Label`, type *Do you suffer from any of the following conditions?*.
6. In the `Variable Name`, type **pre_conditions**.
7. In the `Choices Field`, type the following on separate lines:

- *Diabetes*
- *Cardiovascular disease*
- *Asthma*
- *Anxiety or depression*

8. In the `Required` field, click *Yes*.

REDCap automatically adds numeric Raw Values for each choice. Raw values are what gets saved to the database when a participant chooses a value. You can change the raw values to something else if you want.
{:. .note }

___

## Dealing with identifiable information

Not in workshop
{: .label .label-yellow }

REDCap allows you to automatically remove personally identifiable information from reports and exported data. Any field can be marked as an identifier.

REDCap uses the US HIPAA model to list what are likely to be personally identifying data. You can look it up using the REDCap help. It is a starting point and it likely to be similar to the Australian model.

If you are collecting personal information from participants you should refer to the Privacy Principles found in the *Privacy Act 1988* (Cth) and Griffith’s Privacy Plan (see [https://www.griffith.edu.au/about-griffith/corporate-governance/plans-publications/griffith-university-privacy-plan#research](https://www.griffith.edu.au/about-griffith/corporate-governance/plans-publications/griffith-university-privacy-plan#research)).
{:. .error }