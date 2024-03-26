---
layout: default
title: Instruments, forms, surveys
parent: Instruments
nav_order: 1
---

# Instruments, forms and surveys
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Before we proceed: some terminology

Before you start building your project, it will be helpful to understand the terms that REDCap uses. The first and most important distinction is between `instruments`, `forms` and `surveys`.

REDCap considers anything that can capture data to be an `instrument`. Data can then be added to an instrument using either `forms` or `surveys`.
{:. .info }

{% include figure.html img="instruments-forms-surveys.png" alt="Instruments, forms and surveys." width="75%" %}

### Instruments

Think of an instrument as a collection of `fields` (e.g. name, age, etc). You can have any number of instruments in your project. For example, you might want to create one instrument for collecting participants' demographic information, and another instrument for collecting participants' current health indicators (it will become clear later why you might want to separate them).

### Forms

Whenever an instrument is created, a form is made available for the researcher to enter data into. 

Forms and surveys look identical in the `Designer` page. The only difference is that forms are filled out by you the researcher, while surveys are filled out by your participants. Provided surveys have been enabled for your project, you can turn any form into a survey. 

### Surveys

If you want to capture data for your project by asking participants to fill out surveys, you need to enable surveys in your project. If you forget to do this, you won't be able to make your data collection instruments visible to the public (see the section on [distribution](09-distribution.md)). In the 

{% include figure.html img="enable-surveys.png" caption="Don't forget to enable surveys if you plan on using them" alt="Screenshot showing the enable survey button" width="100%" %}

## Choosing an instrument design

It can be helpful to break your data collection into separate instruments. For example, you may only need to collect demographic data from your participants once, whereas you might wish to collect health data from them several times. Alternatively, you might want to present participants with different instruments based on their responses to demographic questions.

Here, we're going to create two instruments: one for *Demographic data*, and one to collect *Baseline health data*.

### Rename an instrument

1. Click `Online Designer` on the Project Setup tab OR click `Designer` under `Project Home and Design`
2. Under `Data Collection Instruments`, you'll see one instrument in the list called *Form 1*.
3. Click on `Choose actions` under `Instrument actions` and select `Rename`.
4. Name the instrument *Demographic data*.

### Create a new instrument

1. Click `Create` to create a new instrument from scratch.
2. Click `Add instrument here`
3. Name your instrument *Baseline health Data*.
