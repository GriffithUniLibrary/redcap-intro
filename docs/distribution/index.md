---
nav_order: 9
title: Distribution
layout: default
has_children: true
---

### Survey settings

You can set the overall look and feel, as well as the behaviour, of your survey before sending it out.
Many of the options are either self-explanatory or beyond the scope of this workshop. We will not go through every option.

{% capture surveysettings %}

1. Click `Return` to the list of instruments.
2. Click `Survey settings` alongside the _Demographic data_ instrument.
3. Under `Question Display Format` you have the option to display questions all on one page or on separate pages using section headers as dividers.
4. Note that the survey can be given a `Survey Expiration date`.
5. The `Save and Return Later` option creates a ‘return code’ that allows participants to return to a partially completed survey.
6. Check `Auto-continue` to next survey.

{% include alert.html text="Checking Auto-continue to next survey will make sure that once the participant has completed the `demographics` survey, they are automatically redirected to the `Baseline Health Data` survey. If you don’t use this option, you would need to send participants a separate link to the second survey." color="info" %}

{% endcapture %}
{% include card.html header="Survey Settings" text=surveysettings %}

## Distributing your survey

### Enabling your survey

You’ll notice that there will be a green button under each survey reading `Enable`. Tip: If you don’t see it, you need to go to your Project Setup and select Use surveys in this project.  

{% include figure.html img="my-instruments.png" alt="Alt text" caption="REDCap Projects Screen" width="100" %}

{% capture publicurl %}

1. Click `Survey Distribution Tools` in the left-hand navigation.
2. Note that the `Public Survey URL` can be copied and pasted into an email or web page.
3. More memorable URLS can be created using `Create Custom Survey Link`. They may only contain letters, numbers and underscores.
4. Click `Create Custom Survey Link` and type in __RCTraining_[YYYY]_[MM]_[YB]__ where [YYYY] is the year, [MM] is the month and [YB] are your initials.
5. Click `Submit`.
6. You can use a QR code to have people’s smartphones automatically load the survey URL.
7. Click `Survey Access Code` or QR Code.
8. Try pointing your smartphone camera at the QR code to see the survey load.
9. The QR code can be dragged and dropped into a document, email or web page, or it can be saved as an image to be used later.
{% endcapture %}
{% include card.html header="Distributing a public survey URL" text=publicurl %}

### Automatic invitations

To automatically invite participants via email you need to create a participant list. The participant list just consists of email addresses—no other details are needed.

{% capture participantlist %}
Create a participant list and send invitations

1. In `Survey Distribution Tools`, click the `Participant List` tab.
2. Click `Add Participants`.
3. Enter your own email address.
4. Click the `Add Participants` button.
5. Click `Compose Survey Invitations`.
6. Check the `Enable Reminders` box.
7. Select _Send every 2 days_.
8. Select _Send Only Once_.  This will send one reminder after two days, only if the participant hasn’t yet completed the survey.
9. In the `Subject Line`, type _Invitation to participate in vaccine efficacy trial_. Specific subject lines are less likely to be flagged as spam than generic ones.
10. The email may be edited and formatted with common text formatting options.
11. Check that the email address in the `Participant List` on the right column is checked.
12. Click `Send Invitations`.
{% endcapture %}
{% include card.html header="Distributing a public survey URL" text=participantlist %}

### The REDCap mobile app

REDCap offers a mobile app on iOS and Android. The mobile app allows for mobile, offline data input. That is, you don’t need mobile reception to use it. This can be ideal for environmental research or remote-area social research.

We won’t review it in this session, but you can download it for free and try it out.

### Moving your project to production status

When we are happy with our project settings, instrument design and survey settings, we can proceed to bring our project into Production status. Moving to Production status allows us to collect real data.
NB: Once your project is in Production status, structural changes become much more difficult. This is because it’s possible that changes you make might result in data loss. You may need to submit any changes to an administrator.
Obtaining ethics approval
{% include alert.html text="WARNING: REDCap allows you to make your project live without administrator oversight. It is your responsibility to obtain ethics approval from the Office of Research before proceeding with any human research." color="warning" %}

{% capture production %}

1. Click on `Project Setup` on the left-hand navigation.  
2. Note that The `Main Project Settings` section shows a green check and the words _“I’m done!”_
3. We are now done with the second section (design data collection instruments). Click _I’m done_.
4. The `Optional modules` allow for longitudinal studies and randomisation. These are outside the scope of today’s workshop.
5. Click _I’m done_ on the `Optional modules`.
6. Click _I’m done_ on `Set up project bookmarks`.
7. Click _I’m done_ on `User rights and permissions`.
8. `User rights` may be important if you are collaborating with other researchers on this project. They are outside the scope of this workshop.
9. Click _I’m done_ on the `Test your project` section.
10. Click _I’m done_ on `Move your project to production status`.

{% capture checklist %}
It is not strictly necessary to click all of the “I’m done” boxes to move to production, but it is a handy checklist to make sure you have completed what you need to do before going live.
{% endcapture %}

{% include alert.html text=checklist color="info" %}

{% endcapture %}
{% include card.html header="Move your project to production status" text=production %}

{% include figure.html img="move-to-production.png" alt="Alt text" caption="Move your project to production status" width="100" %}

{% capture livedata %}

1. Click on `Survey Distribution Tools` on the left-hand navigation.  
2. Click `Open Public Survey`.
3. Complete the survey (there will be three sections) and click `Submit`. Try experimenting with the validation and calculation fields by entering different values.
4. Close the tab.
5. Click `Project Home` and note that there is now a new record in the project.
{% endcapture %}
{% include card.html header="Entering live data" text=livedata %}

----

## About identifiers

REDCap allows for personally identifiable information to be automatically removed from reports and exported data. Any field can be marked as an identifier.

REDCap uses the US HIPAA model to list what are likely to be personally identifying data. You can look it up using the REDCap help. It is a starting point and it likely to be similar to the Australian model.

{% include alert.html text="If you are collecting personal information from participants you should refer to the Privacy Principles found in the *Privacy Act 1988* (Cth) and Griffith’s Privacy Plan (see [https://www.griffith.edu.au/about-griffith/corporate-governance/plans-publications/griffith-university-privacy-plan#research](https://www.griffith.edu.au/about-griffith/corporate-governance/plans-publications/griffith-university-privacy-plan#research))." color="warning" %}
