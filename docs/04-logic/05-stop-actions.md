---
nav_order: 5
title: Stop actions
layout: default
parent: Logic
---

# Stop actions
{: .no_toc }

You can end the survey automatically based on a participant’s answers to a question.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Stop Actions cannot be tested until the survey is published
{: .highlight }

### Create a Stop Action
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