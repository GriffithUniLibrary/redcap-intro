---
layout: default
title: Validation
parent: Instruments
nav_order: 3
---

# Question validation
{: .no_toc }

We can apply validation to certain types of text entries. For example, we can ensure that a phone number or email address is correctly formatted.

{: .d-inline-block } 
Activity 
{: .label } 
### Validate postcodes

1. Click `Add field`.
2. Choose `Text box`.
3. Type Postcode in the `Field` Label and type *postcode* in the `Variable Name`.
4. In the `Validation` field, select *Postal code (Australia)*. This will ensure only four numerals can be entered into the field.
5. In the `Field` note field, type *“Providing your postcode is optional. We collect approximate residency data to assist with interpreting trial results.”*
6. Click `Save`.


{: .d-inline-block } 
Activity 
{: .label } 
### Validate emails

1. Click `Add field`.
2. Choose `Text box`.
3. Type *Email* in the `Field` Label and type *email* in the `Variable Name`.
4. In the `Validation` field, select *Email*. This will ensure only correctly formatted emails can be entered into the field.
5. In the `Identifier` field, select *“Yes”*.
6. In the `Field` note field, type *“Providing your postcode is optional. We collect approximate residency data to assist with interpreting trial results.”*
7. Click `Save`.
8. Click `Return to list of instruments`.

{: .d-inline-block } 
Activity 
{: .label } 
### Validate dates

2. Click `Add field`.
3. Choose `Text box`.
4. Type *Date of Birth* in the `Field` description and type *dob* in the `Variable Name`.
5. In the `Validation` field, select *Date (D-M-Y)*. This will ensure only dates can be entered into the field.

{: .d-inline-block } 
Activity 
{: .label } 
### Validate numbers

1. Create two new text box fields:  for Height (cm) (Variable Name: **height_cm**) and Weight (Kg) (Variable Name: **weight_kg**) using the instructions above.
2. For each one, set the `Validation` to *Integer*. This will ensure only numbers can be entered into the field.
