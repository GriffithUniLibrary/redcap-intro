---
nav_order: 2
title: Branching logic
layout: default
parent: Logic
---

# Branching logic
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Branching logic

Branching logic is also known as conditional display logic.

You can decide to show or hide specific questions based on the results of previous questions, including the results of calculated questions. Here, we are going to show a participant a warning about their BMI if it is over a certain value.

Remember that branching logic operates on the question to be displayed, not on the question before.
{:. .info }

Branching logic cannot be tested until the survey is published.
{:. .warning }

### Activity: Create a BMI Warning
{: .d-inline-block }
Activity
{: .label }
> 1. Click `Add Field`
> 2. Choose `Descriptive Text` (with optional Image/Video) for the `Field Type`.
> 3. In the `Field` Label, type the following:
> `Based on the information you've provided, your BMI (body mass index) is in a range associated > with increased risk of cardiovascular diseases and diabetes.`
> 4. In the `Variable Name`, type bmi_warning.
> 5. Click `Save`.
> 6. Click the `Branching Logic Button` ( ).
> 7. Select the `Drag-N-Drop Logic Builder`.
> 8. Drag bmi = (define criteria) to the right column.
> 9. Select greater than (`>`) and type 30 in the value field.
> 10. Note that the equation `[bmi] > 30` also appears in the Advanced Branching Logic Syntax section above.
{: .code-example }
<!-- The {: .code-example } snippet causes the paragraph above to be enclosed in a box. -->

## Stop Actions

You can end the survey automatically based on a participant’s answers to a question.

Stop Actions cannot be tested until the survey is published
{: .highlight }

### Activity: Create a Stop Action
{: .d-inline-block }
Activity
{: .label }
> 1. Click `Return to list of instruments`.
> 2. Choose the _Baseline Health Data_ instrument.
> 3. Scroll to the question that reads: Do you suffer from any of the following conditions?
> Click the red button in the question menu.
> 4. Select _Asthma_ and click `Save`.
> 5. Note that the _Asthma_ option now has `[End Survey]` alongside it in red.
{: .code-example }
<!-- The {: .code-example } snippet causes the paragraph above to be enclosed in a box. -->

Stop Actions don’t support ending the survey based on multiple conditions (e.g. `[Age] > 45 AND [Diabetes] = YES)` but you may be able to achieve a similar result using a combination of Branching and Stop Actions.
{:. .note }

## Action tags

Action tags can help format or adapt entries automatically. For example they can limit the number of characters a participant enters in a field, or prevent them from selecting more than a certain number of options.

Here we are going to create a ‘None of the Above’ checkbox option, that automatically unchecks all the other boxes, and unchecks itself if any other box is ticked.
{:. .info }

### Activity: Add ‘None of the Above’ to the Existing Conditions’ question
{: .d-inline-block }
Activity
{: .label }
> 1. Click the `edit` button ( ) next to the question labelled _Do you suffer from any of the following conditions?_
> 2. Add a new option to the list of options as follows: `5, None of the above`.
> 3. In the `Action Tags` field, type `@NONEOFTHEABOVE=5`. This indicates that the answer option coded as ‘5’ operates as the ‘none of the above’ option.
{: .code-example }
<!-- The {: .code-example } snippet causes the paragraph above to be enclosed in a box. -->

Note that we can only test this action tag by looking at the live survey, once it has been published.
{:. .warning }

Now we will add an action tag that causes the calculated field we created before to be hidden from the participant view.
{:. .info }

Activity: Hide a question using action tags
{: .d-inline-block }
Activity
{: .label }
> 1. Click the `edit` button ( ) next to the question labelled _Your Body Mass Index (BMI)_.
> 2. In the `Action Tags` field, type `@HIDDEN-SURVEY`. This will prevent the question being shown to the participant in the survey (although you will still be able to see it in the form view).
{: .code-example }
<!-- The {: .code-example } snippet causes the paragraph above to be enclosed in a box. -->

There are versions of this tag that will hide the question from just the survey, just the mobile app, or from all instruments.
{:. .info }