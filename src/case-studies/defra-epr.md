---
layout: case-study.njk
title: Extended Producer Responsibility for Packaging (pEPR)
client: DEFRA (Department for Environment, Food & Rural Affairs)
description: Designing a digital service to help packaging producers report data and calculate their recycling fees.
order: 7
heroImage: /images/hero-defra-epr.jpg
heroImageAlt: A photograph of a person holding a blue recycling bin in front of some green wheelie bins
tags:
  - Government
  - Service design
  - Public sector
  - Accessibility
---

{% from "captioned-image.njk" import captionedImage %}

## Overview

The Extended Producer Responsibility for Packaging (pEPR) scheme represents a major reform in how the UK manages packaging waste. The scheme shifts the cost of collecting and recycling packaging from local councils to the businesses that produce it, creating financial incentives for companies to use less packaging and choose more sustainable materials.

As an Interaction Designer on this project, I was tasked with designing a digital service that would enable packaging producers to navigate these new regulatory requirements efficiently.

## The challenge

The pEPR scheme required businesses to:
- Report detailed data about all packaging they supply to the UK market
- Calculate fees based on their packaging volumes and materials
- Understand modulated fees that incentivise recyclable, reusable, and refillable packaging

The challenge was significant: businesses needed to enter large, complex datasets while receiving accurate cost estimates. Any friction in this process could create major operational burdens for companies already adapting to new regulations.

## What I did

Working within a multi-disciplinary GOV.UK team, I designed prototypes using the GOV.UK Design System to:

- Help users to understand the new reforms and whether they will be impacted
- Simplify large data entry
  - Created intuitive patterns for entering bulk packaging data across multiple material types
  - Designed validation and error handling that helped users correct issues without losing progress
  - Developed clear data summary and review stages to build confidence before submission
- Enable accurate fee calculations
  - Designed a quoting system that provided transparent cost breakdowns
  - Made fee modulation understandable, showing how different packaging choices affect costs

## Example designs

{{ captionedImage({
  src: "/images/image-defra-1.jpg",
  alt: "A screenshot of a GOV.UK task list titled 'Report your organisation's packaging data'",
  caption: "An example of using the GOV.UK task list pattern to guide a user through various reporting tasks."
}) }}

{{ captionedImage({
  src: "/images/image-defra-2.jpg",
  alt: "A screenshot of a GOV.UK check your answers page titled 'Check your organisation's details'",
  caption: "An example of using the GOV.UK check your answers pattern to help a user confirm their organisation's details."
}) }}

## The Impact

The pEPR scheme launched in 2025, directing £1.1 billion to councils for improved waste collection. The service enables businesses to comply with regulations expected to support 25,000 new jobs, underpin £10 billion in infrastructure investment, and shift the UK towards a circular economy.

## Working in Government

This project exemplified the unique challenges and rewards of public sector design work:

- **Balancing multiple stakeholders** – I worked closely with policy, legal and developers
- **Regulatory complexity** – translating environmental policy into usable digital services
- **Scale and impact** – affecting thousands of businesses and fundamentally changing packaging practices across the UK
- **GOV.UK standards** – maintaining accessibility and consistency with established patterns
