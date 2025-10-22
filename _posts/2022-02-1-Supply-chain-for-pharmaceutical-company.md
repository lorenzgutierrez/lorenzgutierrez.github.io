---
layout: post
title: Supply chain for pharmaceutical company
subtitle: Solved using and gurobi based software and results presented using PBI
thumbnail-img: /assets/img/covid.jpeg
cover-img: /assets/img/Pharmaceutical_portada.jpeg
gh-badge: [star, fork, follow]
tags: [Data Science, Optimization, Supply Chain]
comments: false
---

This was my first project at Accenture. Due to the pandemic, one of the world's largest pharmaceutical companies wanted to optimize their vaccine distribution routes across the globe. The vaccines were delivered in different packages and formulations worldwide, with the USA being the principal market.

The client needed an optimization solution to outperform their current Excel-based calculations, along with a Power BI dashboard to visualize the model's main outputs. During the project, we developed a model focused on minimizing vaccine shortages and the number of shipments, without primarily optimizing for cost.

We held numerous meetings to gather client data and requirements, as well as to connect our model to the client's database. The solution was implemented using [Riverlogic](https://www.riverlogic.com/), a Gurobi-based software platform for supply chain optimization.

## Data

Although the data was confidential, the input data was provided in Excel files where most of the constraints and model requirements were specified. The main challenges were missing or incorrect data from the client, as well as continuous format updates, which required constant modifications to our ETL scripts to accommodate these changes. We also had to continuously balance the trade-off between usability and data quality efficiency.

## Analysis

Although Riverlogic was used for the model optimization, a significant part of the project consisted of an ETL pipeline where user input data was processed using Python scripts to prepare the output file for Riverlogic. A substantial portion of the model logic was also implemented in these scripts, including user data validation.

It's important to mention that the Python script could be executed in different ways, depending on user preferences:
- By pressing a button in the user input Excel file (using VBA)
- Automatically when the input file was uploaded to Riverlogic servers

I was involved in the development of both execution methods.

## The Riverlogic Model

This was probably the most technically challenging part of the project. I had to learn new software, connect the inputs and outputs to Riverlogic servers, and create numerous SQL queries. We worked closely with Riverlogic's top developers, iteratively developing the model based on continuous client feedback.

The results were considered successful by the client, as our model accurately captured important real-world characteristics and behaviors they observed, including supply shortages, warehouse capacity utilization, and production rates.

