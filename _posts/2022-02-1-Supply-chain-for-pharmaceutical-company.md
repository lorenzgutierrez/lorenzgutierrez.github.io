---
layout: post
title: Supply chain for pharmaceutical company
subtitle: Solved using and gurobi based software and results presented using PBI
thumbnail-img: /assets/img/covid.jpeg
gh-badge: [star, fork, follow]
tags: [Data Science, Optimization, Supply Chain]
comments: false
---

First project on Accenture. Due to pandemic, one of the biggest and most important pharmaceutical companies in the world, wanted to improve their vaccines routes across the globe. The vaccines were delivered in different packages and formulas across the globe, with USA being its principal market. The client required to develop an optimization problem to outperform their current calculations (doing in excel), as well as an overview with the main outputs of the model in PBI. During my stay in the projectwe developed a model focused minimizing the shortage of vaccines and the amount of shipments without taking care of the cost. We had a lot of meetings gathering client data and requirements as well as connecting our model to the client database. The solution was presented using [Riverlogic](https://www.riverlogic.com/), a Gurobi based software for supply chain problems.

## Data
Although the data was confidential, the input data was presented in an excel, were most of the constrains and model requirements were explicited. The issues were mainly missing or incorrect data provided by the client, as well as continues format updates of it, making the ETL scripts to be modified to acomodate to such changes. Also, a trade off between usability and data quality efficiency had to be taken into account all the time.

## Analysis
Although Riverlogic was used for the model optimization, a big part of the project consisted on an ETL were user input data was processed using a python script so the output file was ready to be fed into Riverlogic. A huge part of the model was also explicited in ths script, and user data validation was also implemented in this step. Is important to mentionate that the python script was run in different ways, depending on the user desires, it could be run by pressing a button in the user input excel (VBA was used) or was automatically run when the input file was uploaded into Riverlogic servers, in both cases I was part of this development.

## The Riverlogic Model
Probably the most difficult part of the project, tecnically speaking, as I had to learn new software, connecting the outputs and inputs to Riverlogic servers and creating a lot of SQL querys. We closely work with Riverlogic`s top developers, developing the model after continues feedback from the client. The results were considered succesful by the client, as important characteristics and behaviours observed by them in the reality (supply shortage, filled warehouses, production rates) were captured by our model.

