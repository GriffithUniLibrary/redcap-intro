---
layout: default
title: Basic questions
parent: Instruments
nav_order: 2
---

# Basic question types
{: .no_toc }

We will use the instrument to try out some basic question types by adding some demographic questions.

## Text box

In REDCap, the 'Text box' question type can be used in several ways: to capture short written responses and information like numbers and dates. Here, we will just capture our participant's name.

### Add a basic text field
{: .d-inline-block } 
Activity 
{: .label } 

1. Click on `Demographic question` to open it
2. Click `Add Field`
3. Choose `Text Box`
4. In the `Field` Label, type *First Name* (this gets displayed to your participants)
5. In the `Field` Name, type *first_name* (this gets stored as a column header in your database)
6. In the `Required` field, select “Yes”.
7. In the `Identifier?` Field, select “Yes”. (Identifiable information can be flagged to restrict it from export.)
8. Click `Save`.
9. Repeat the process to add the field Last Name (*name_last*)

## Multiple choice

Multiple choice fields are of two kinds:

- 'Radio buttons' and 'Drop down lists' only allow the participant to select a single option from a list. 
- 'Checkboxes' allow participants to select any number of items from a list.

### Add a radio button question
{: .d-inline-block } 
Activity 
{: .label }

1. Click `Add field`
2. Choose `Multiple choice - Radio buttons` from the drop-down list.
3. Type *Gender* in the `Field` Label and *gender* in the `Variable Name`.
4. Add the following options: *Male, Female, Intersex, Prefer not to say*.

{:. .note-title}
> About raw values
>
> The ‘raw value’, which appears before the column, is the value that gets recorded in your data. Thus your recorded value can be numeric, or a single letter code, while the participant can read a fuller description.
 
### Add a checkbox question
{: .d-inline-block } 
Activity 
{: .label }

3. Click `Add field`.
4. Choose *Checkboxes (Multiple Answers)* for the `Field Type`.
5. In the `Field Label`, type *Do you suffer from any of the following conditions?*.
6. In the `Variable Name`, type **pre_conditions**.
7. In the `Choices Field`, type the following on separate lines:

    - *Diabetes*
    - *Cardiovascular disease*
    - *Asthma*
    - *Anxiety or depression*
    - *None of the above*

8. In the `Required` field, click *Yes*.

REDCap automatically adds numeric Raw Values for each choice. Raw values are what gets saved to the database when a participant chooses a value. You can change the raw values to something else if you want.
{:. .note }
