---
layout: post
title: ML-Driven Recommendation System
subtitle: Building a personalized recommendation engine that delivered $500K annual revenue impact
tags: [machine-learning, data-science, recommendation-system, python, leadership, mlops]
comments: true
---

## Project Overview

I led the end-to-end development of a machine learning-based recommendation system for a major telecommunications company, serving over 3 million users. This project transformed a failing rule-based approach into an intelligent, personalized solution that increased conversion rates by 60% and delivered over $500K in annual revenue impact.

## The Challenge

The company was facing a critical problem with their mobile plan upgrade recommendations:
- **99.85% ignore rate** - users were systematically ignoring all offers sent via WhatsApp
- **Rule-based system** with zero personalization, treating all 3M users identically
- **$700K in annual revenue opportunity** being wasted due to poor targeting
- **0.05% acceptance rate** - essentially random chance

## My Role

As **Principal Data Scientist and Team Lead**, I owned this project from conception through production deployment:

- Managed a **4-person cross-functional team** (2 Data Scientists, 1 Senior Data Scientist, 1 Manager)
- Designed the complete **technical architecture** and ML solution from scratch
- Owned **client relationships** and stakeholder communication throughout the 4-month project
- Made critical strategic decisions on model architecture, feature engineering, and deployment

## Technical Innovation

### The Key Insight

Rather than asking "will this user upgrade?" (classification), I reframed the problem as "which specific plan does each user prefer?" (ranking). This fundamental shift enabled true personalization.

### Solution Architecture

- **Ranking-based approach** using LightGBM to predict user-plan transition probabilities
- Generated **personalized rankings** for 3M users monthly (45M predictions per month)
- Same 15-plan inventory produced completely different recommendations for each user based on individual behavior patterns
- **Production-ready MLOps pipeline** in Databricks with automated retraining and monitoring

### Custom Evaluation Metrics

Traditional ML metrics (accuracy, precision, recall) proved inadequate for ranking quality assessment. I developed **ranking distribution analysis** - validating that accepted offers consistently ranked higher than rejected ones across the user base.

## Overcoming Significant Challenges

### 1. Client Skepticism

When the client initially rejected the solution, I proposed a controlled **20K-user A/B test**. Within one month, we demonstrated a **60% improvement** in conversion rates, completely transforming the client relationship and gaining buy-in for full deployment.

### 2. Data Drift from Economic Volatility

Operating in a market with **3% monthly inflation** made traditional 3-6 month training windows impossible. I implemented innovative **monthly retraining strategies** focusing on relative pricing relationships rather than absolute values, turning this constraint into an advantage.

### 3. Feature Engineering Under Pressure

Despite client pressure to simplify, I maintained rigorous feature engineering standards, ensuring the model captured genuine user preferences rather than superficial patterns.

## Business Impact

**Revenue & ROI:**
- **$30-40K additional monthly revenue** ($400-500K annually)
- **2-month ROI payback** on $60K project investment
- **40-60% improvement** in conversion rates (from 0.05% to 0.08%)

**Operational Excellence:**
- **Zero production failures** since deployment
- Serving **3M users monthly** with consistent performance
- Automated pipeline requiring minimal manual intervention

## Key Learnings

This was my **first recommendation system** - approaching it from first principles rather than copying existing solutions led to innovative approaches:

1. **Question the problem formulation** - ranking vs. classification made all the difference
2. **Prove value incrementally** - the 20K-user test was crucial for stakeholder buy-in
3. **Design for your constraints** - monthly inflation became a feature, not a bug
4. **Custom metrics matter** - standard ML metrics don't always capture business value

## Technical Stack

**Languages & Libraries:** Python, LightGBM, Pandas, NumPy, Scikit-learn

**Infrastructure:** Databricks, Apache Spark, MLOps automation

**Deployment:** Production pipeline with automated monitoring and retraining

---

## Reflection

This project demonstrated that fresh perspective combined with solid data science fundamentals can deliver transformative business results. By focusing on the actual business problem rather than applying template solutions, we created a system that continues to drive significant value for millions of users.

The experience reinforced the importance of leadership in data science - technical excellence must be paired with stakeholder management, strategic thinking, and the ability to navigate both client skepticism and complex operational constraints.
