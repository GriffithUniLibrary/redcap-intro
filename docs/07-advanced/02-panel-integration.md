---
layout: default
title: Panel integration
parent: Advanced topics
nav_exclude: true
---

# Panel integration
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## About panel companies and passthrough parameters

When working with a panel company (a company that provides survey participants for researchers), they usually require you to capture an ID of a participant via a URL parameter, then pass that ID back out to them once the participant has completed the survey or screened them out, so that the participant can be paid for their work. 

## Capture a URL parameter in an instrument field

### Add a parameter to your survey URL

This method only works with instruments that are enabled as surveys
{: .note }

REDCap can read a value from the URL that is used to load the survey, then store it in a field in the survey instrument. Parameters are carried in URL in the form:

`https://somedomain.com/page.html?foo=bar`

In the above example, the parameter is `foo` and the value of that parameter is `bar`. To capture that value in REDCap, we need to make sure that the URL that loads the survey contains the parameter you want. It will be in the form:

`https://www151.griffith.edu.au/redcap/surveys/?s=FWXWYEYMLCKXFDJL&psid=1234`

You can see here that there are two parameters: `s`, which tells REDCap which survey to load, and `psid`, which is the survey participant ID. They are separated by an ampersand (`&`) character. The `psid` is the parameter we want to capture in our survey instrument. Note that it can have any value, provided it doesn't contain any spaces or special characters.

### Create a field with the same name as the parameter

1. Create a new field of type `Text box`.
2. Give it any label you prefer.
3. Set the `Variable name` to **psid** (or whatever the name of your URL parameter is).
4. Add the action tag `@HIDDEN-SURVEY`. This will make sure the value of `psid` is not displayed on screen. 

![](../../assets/images/ptp-field-psid.png)
Adding the @HIDDEN-SURVEY action tag
{: .fs-3 .fw-300 .text-center }

When the survey loads, provided the URL contains a value for `psid`, that value will be stored in the instrument field. You can use this to create an return URL that takes the participant back to the panel company (see below).

Unless you create some logic in your instrument to prevent it, it will be possible for participants to complete the survey without providing a value for `psid`. 
{: .note }

### Create the outbound URL

When participants finish the survey, they need to be directed back to the panel company to show that they have completed the survey. The panel company will provide you with a base URL, containing the domain and page. Let's say for this example that the base URL is: 

`https://somepanelcompany.com/projects/end?rst=2`

The `psid` needs to be added to this URL, then it needs to be loaded by the participant once they have completed the survey. The simplest way to do this is to pipe the value for `psid` into the `Redirect to a URL` option in the Survey Options.

1. Open the `Survey Options` screen.
2. Scroll to `Survey Termination Options`.
3. Select the `Redirect to a URL` radio button.
4. Paste or type the base url into the URL field.
5. Add the parameter and the piping code to the end of the URL, as follows: `&psid=[psid]` (the square brackets tell REDCap to pipe a value from an instrument field). 

The result should look like: 

`https://somepanelcompany.com/projects/end?rst=2&psid=[psid]`

![](../../assets/images/termination-url.png)
Piping the PSID field intoto the Redirect URL
{: .fs-3 .fw-300 .text-center }

## Redirecting disqualified participants to a different URL

Some panel companies will expect qualified participants who complete the survey to be redirected to one URL, and prospective participants who do not qualify for the study to be redirected to a different URL. To do this, we need to be able to dynamically build the URL and then send the result to the `Redirect to a URL` option in the `Survey Options` screen.

We are not describing here how to calculate eligibilty, since that will depend on your study requirements. However, you should at least have a hidden Calculated field called **eligibility**. That calculation should resolve to `1` if the participant is eligible, and to `0` if the participant is ineligible.
{: .note }

There are three functions we need to use to create the final URL. First, we use an (action tag)[../04-logic/03-action-tags.md] called `@CALCTEXT` to generate the final URL that participants are directed to when they click the 'Submit' button. Inside the `@CALCTEXT` action tag, we use the `concat` function to concatenate the base URL with the relevant parameters, and the `if` function to decide which parameters should be added. 

### Code breakdown

#### Calctext
The `@CALCTEXT` action tag allows REDCap to perform text operations without treating the text as a value. We need to do this to build the URL.

#### Concat
The `concat` function concatenates strings. It uses the pattern: `concat(string1,string2,string3)` to create a final string of the form `string1string2string3`. 

#### If
The `if` function returns different values depending on some logical evaluation. It uses the pattern: `if(logical-test, value-if-true, value-if-false`). 

![](../../assets/images/ptp-logic-editor.png)
The equation in the Action tag editor
{: .fs-3 .fw-300 }

In this case, if `eligibility` is 0 (i.e. the participant is ineligible), we apply the following parameters: 

```
rst=2
psid={the value of psid}
```

Alternatively, if `eligibility` is 1 (i.e. the participant is eligible), we apply the following parameters:

```
rst=1
basic=14880
psid={the value of psid}
```

Of course, the actual parameters and values are completely up to you, but will probably be supplied to you by the panel company.

### Putting it all together

1. Create a new field of type `Text field`. 
2. Give it any name you like. We are going to hide it from the participant.
3. Set the `Variable name` to **end_url**. We will use this later.
4. In the `Action tag` section of the field settings, enter the following (note that this is demo code, yours will necessarily be different):

```
@CALCTEXT(concat(if([eligibility]=0, 'https://somepanelcompany.com/projects/end?rst=2&psid=', 'https://somepanelcompany.com/projects/end?rst=1&basic=14880&psid='),[psid]))
```

![](../../assets/images/ptp-field-endurl.png)
Creating the endURL field
{: .fs-3 .fw-300 .text-center }

URL shortening and redirection services like bit.ly do not pass through URL parameters unless they were part of the original URL. Since in this case, the parameter needs to be different every time, shortened or customised URLs can't be used.
{: .warning }

### Add the URL to the survey settings

Once you have tested the logic and made sure that the URL is being composed as you want, you can add it to the survey settings. 
1. Open the `Survey settings` for the survey you are editing.
2. Scroll down to `Survey termination options`.
3. Select the `Redirect to a URL` radio button.
4. Enter the Variable name of the URL that you have composed (we used **end_url** above).

![](../../assets/images/ptp-survey-settings.png)
Adding the End URL to the survey settings.
{: .fs-3 .fw-300 .text-center }

When the participant completes the survey, they will be automatically directed to one of the URLs built by your expression in the [end_url] field.

## Adding a quota redirect

In cases where the survey is over quota, the panel company may also want participants to be redirected to a third URL. Normally, Stop Actions are used to handle quotas in REDCap. However, since REDCap's `Survey Settings` page doesn't allow piping to be used in the `Options related to Survey Stop Actions`, we need to get a little creative. Instead, we will count survey completions manually and use the same technique as above to dynamically create different URLs depending on whether the participant is ineligible or over quota.

### Create a separate instrument for qualifying questions

To use this method, we will need to place the qualifying questions in one instrument, and the research survey questions in another.

1. Open the `Online Designer`.
2. Click `Create a new instrument from scratch`.
3. Name the instrument `Qualifying questions`.
4. Use the reordering arrows to the left of each instrument to move the Qualifying questions instrument above the main research survey. 
5. Open the main research survey and open the `psid` field. 
5. Use the Move button at the top of the field options to move the `psid` field into the `Qualifying questions` instrument.

### Add a single field to record completions

REDCap doesn't give us a way to access the number of completed surveys while a survey is running. Instead, we are going to count completions manually in order to set the quota.

1. Open the main research survey instrument
2. Create a new field with the variable name `completed`.
3. Set the field type to `Multiple choice (radio buttons)`.
4. In the `Field label`, type `Confirmation of completion`.
5. In the `Options` section, enter a single option: `1, I have completed the survey and am satisfied with my responses`.
6. Make the question required.

![](../../assets/images/completion-confirmation.png)
Adding the 'Completion confirmation' field.
{: .fs-3 .fw-300 .text-center }

Once we have done this, we can use the function `[aggregate-sum]` to count how many times a participant has ticked the box. Since they must tick the box to submit their survey, it is a fairly reliable indicator of the number of people who have actually completed the survey.

### Use a calculated field to count the number of completions

1. Open the `Qualifying questions` instrument
2. Add a new field with the variable name `completed_count`.
3. Set the field type to `Calculated field`.
4. In the `Field label`, type `Count of completions`.
5. In the `Calculation Equation` field, type `[aggregate-sum:completed]` (this adds together all the '1's contained in the `completed` field).

![](../../assets/images/completion-count.png)
Adding the 'Completion confirmation' field.
{: .fs-3 .fw-300 .text-center }

If the participant is neither ineligible nor over quota, then they are eligible to complete the survey and they will be progress to the main research survey. 
{: .note }
