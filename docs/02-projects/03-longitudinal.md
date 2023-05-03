---
Parent: Working with projects
title: Longitudinal studies
nav_order: 3
layout: default
---

# Data dictionaries
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

REDCap can export and import the data structure for your project into a CSV-formatted file called a data dictionary.
{:. .highlight }

A data dictionary is helpful for saving the design of your survey, or alternatively for rapidly building and importing a long survey with many questions. The easiest way to see how they work is to export one and look at it in Excel.

## Activity: Export and edit a data dictionary
{: .d-inline-block }
Activity
{: .label }

1. In the `Designer`, click the `Data Dictionary` tab.
2. Click `Download the current Data Dictionary`. A CSV file titled `[Project Name]_DataDictionary_[Date].csv` will download to your `Downloads` directory.
3. Locate the downloaded file and double-click it to open it in Excel.
4. Walk through the columns, noting especially the formatting of multiple choice options and calculated fields.
5. In a new line, enter the following
    `Variable: prize; Form Name: prize_draw; Field Type: radio; Field Label: What reward would you like?; Choices: 1, Gift card | 2, Chocolates | 3, Movie tickets.`
6. Save the file (in CSV format, if prompted by Excel).
{% include figure.html img="csv-newline.png" alt="Spreadsheet containing redcap data" caption="Adding a new line to a data dictionary" width="100" %}

Once you've edited yor data dictionary, you can upload it with the changes you've made and they will be added to the instruments in your project. You can even add new instruments this way!

{% capture uploaddict %}
7. In the `Data Dictionary` tab, click `Upload a Data Dictionary`.
8. Navigate to your CSV file and select it for upload.
9. Click on the `Online Designer` tab.
10. Observe that a new instrument has been created called _Prize Draw_.
11. Open the _Prize Draw_ instrument and note the multiple choice field that was added by the uploaded data dictionary.
{% endcapture %}
{% include card.html header="Upload a data dictionary" text=uploaddict %}

{% include figure.html img="new-instrument.png" alt="The project designer screen" caption="A new instrument added to the Project Designer" width="100" %}
