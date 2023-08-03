---
nav_order: 2
title: Branching logic
layout: default
parent: Logic
---

# Branching logic
{: .no_toc }

Branching logic is also known as conditional display logic.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

You can decide to show or hide specific questions based on the results of previous questions, including the results of calculated questions. Here, we are going to show a participant a warning about their BMI if it is over a certain value.

Remember that branching logic operates on the question to be displayed, not on the question before.
{:. .info }

Branching logic cannot be tested until the survey is published.
{:. .warning }

### Create a BMI Warning
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