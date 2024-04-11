---
layout: default
title: Action tags
parent: Logicexclude
nav_exclude: true
toc_exclude: true
---

# Action tags
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

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

Hide a question using action tags
{: .d-inline-block }
Activity
{: .label }
> 1. Click the `edit` button ( ) next to the question labelled _Your Body Mass Index (BMI)_.
> 2. In the `Action Tags` field, type `@HIDDEN-SURVEY`. This will prevent the question being shown to the participant in the survey (although you will still be able to see it in the form view).
{: .code-example }
<!-- The {: .code-example } snippet causes the paragraph above to be enclosed in a box. -->

There are versions of this tag that will hide the question from just the survey, just the mobile app, or from all instruments.
{:. .info }
