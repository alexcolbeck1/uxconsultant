---
layout: case-study.njk
title: Enabling Patients to Update Their NHS Contact Details
client: NHS England
description: Designing and launching a new service within 7 months to help update patient contact details.
order: 5
heroImage: /images/hero-nhs-login.jpg
heroImageAlt: A photograph of a hand holding a mobile phone with the NHS app login screen on it
tags:
  - Healthcare
  - Public sector
  - Service design
  - Accessibility
---

{% from "captioned-image.njk" import captionedImage %}

## Overview

The NHS needed a way for patients to update their own contact details on the national database—a task previously only NHS staff could perform. The goal was to improve data accuracy, reduce operational burden, enable digital communication, and save millions in paper correspondence costs.

## What I Did

- Analysed discovery findings from a previous NHS team
- Facilitated ideation and solution workshops to define opportunities
- Created hypotheses statements with BA and UR teams
- Built working HTML prototypes using the NHS prototype kit
- Conducted iterative rounds of moderated usability research
- Created service blueprints mapping processes, systems, and policies
- Supported the team through Alpha and Beta phases
- Ensured accessibility and inclusive design throughout

## The Problem

The national patient database had critical data quality issues. In April 2019, while 80% of records had a mobile number and 25% had an email, none were verified by the NHS. NHS services spent **£8m per year on paper** and **£2m on envelopes**, yet couldn't trust the central database. Patients had no way to update their own details or choose communication preferences, and different NHS services maintained conflicting records.

## The Approach

Working within an Agile team, I helped define the problem space and prototype solutions. We hypothesised that NHS login—the emerging authentication service—was the logical place for patients to manage their details. I built HTML prototypes and validated them through popup research in Leeds and lab-based usability testing. When the pandemic hit mid-project, we pivoted to remote research and continued refining the design through private beta with pilot GP surgeries.

## Design concepts

{{ captionedImage({
  src: "/images/image-nhs-login-1.jpg",
  alt: "A screenshot of an NHS web page with the cards 'Contact details' and 'Login and security settings'",
  caption: "A design concept to introduce the feature of contact detail management."
}) }}

{{ captionedImage({
  src: "/images/image-nhs-login-2.jpg",
  alt: "A screenshot of an NHS web page with a user's email and mobile number with change links next to them",
  caption: "A new page to enable users to see their current details and change them if necessary."
}) }}

{{ captionedImage({
  src: "/images/image-nhs-login-3.jpg",
  alt: "A screenshot of an NHS web page with a question 'Which email address do you want to change?'",
  caption: "A question to clarify which details the user needs to change."
}) }}

## Outcomes

This became the first NHS service allowing patients to directly update their national record. Despite pandemic challenges and a team change between Alpha and Beta, the service launched to private beta within seven months and achieved national rollout by January 2021. The work was nominated for an NHS Going the Extra Mile (GEM) award.

## Results

- **60% conversion rate** - of interrupted users, 60% updated their details
- **15,000+ records updated** in the first 3 months of private beta
- **Only 4-5% dropout** once users chose to update
- **First-ever patient-driven update** to the national patient database
- Enabled future digital communication channels across the NHS
- Potential savings of millions in paper and postage costs annually
