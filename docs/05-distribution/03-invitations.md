---
nav_order: 3
title: Invitations
layout: default
parent: Distribution
---

# Automatic invitations
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

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