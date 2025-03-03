---
date: '2025-03-01T17:23:11+01:00'
author: "Marcin Kostrzewa"
draft: false
title: 'Introduction to Counterfactual Explanations'
categories: ["counterfactual explanations"]
tags: ["XAI", "counterfactuals", "explainable AI", "AI transparency"]
---

# What If AI Could Rewrite Its Decisions?

In a world increasingly shaped by algorithmic decisions, a fundamental question emerges:
when AI makes a decision about us, how can we understand why and &mdash; more importantly &mdash; what we could change 
to get a different outcome?

Explainable AI (XAI) is all about answering those questions, pulling back the curtain from black-box algorithms. 
But while most XAI tools tell you what went wrong, one approach &mdash; counterfactual explanations (CFEs) &mdash; goes further.
CFEs don't just tell you why an AI decided what it did, but shows you how that decision could be different.

# XAI Basics: LIME, SHAP, and the CFE Twist

Explainable AI (XAI) {{< cite "manifesto, survey" >}} emerged from a simple need: if AI systems make decisions affecting people's lives, 
those decisions should be understandable. Traditional approaches like LIME (Local Interpretable Model-agnostic Explanations)
{{< cite "lime" >}} and SHAP (SHapley Additive exPlanations) {{< cite "shap" >}} have become the workhorses of XAI.
These methods tell us what features matter in a prediction.

LIME creates a simplified, interpretable model around a specific prediction, while SHAP assigns importance values to each feature based on game theory principles. 
LIME zooms in on local decisions and SHAP spreads the credit across all features.

While powerful, they leave a crucial question unanswered: what changes would lead to a different outcome?
This is where counterfactual explanations shine. Instead of simply highlighting important features, 
CFEs provide actionable paths to alternative outcomes. They shift the conversation from "why did this happen?" 
to "what would it take for something else to happen instead?"

Feature | LIME/SHAP | Counterfactual Explanations
--- | --- | ---
Focus | Feature importance | Actionable changes
Question answered | "Why this decision?" | "How to get a different decision?"
User benefit | Understanding | Actionability

---

So, what are counterfactual explanations? In plain terms, they show the smallest changes that would flip an AI’s decision. Think of them as "What if?" scenarios with a purpose. 

Here’s an example: An AI denies your loan because your income is 100 000 zł. A counterfactual might say, "If your income were 120 000 zł, you’d get approved." It’s like a cheat code for understanding &mdash; and maybe challenging &mdash; the AI’s logic. Unlike feature breakdowns, CFEs feel personal and actionable.


# The Math: A Formal Look Under the Hood

CFEs can be formulated like in {{< cite "Guidotti2022" >}}:

> Given a classifier $b$ that outputs the decision $y = b(x)$ for an instance $x$, a counterfactual explanation consists of an instance $x'$ such that the decision for $b$ on $x'$ is different from $y$, i.e., $b(x') \neq y$, and such that the difference between $x$ and $x'$ is minimal.

One of the first approaches to generating counterfactual explanations was proposed by Wachter et al. {{< cite "Wachter2017" >}}, who formulated it as an unconstrained optimization problem. 

Given an input instance $x_0$ and a desired outcome $y'$, their approach finds a counterfactual $x'$ by minimizing:
$$
\arg⁡min_{⁡x'}\ell\left(h(x')−y'\right)^2+\lambda\cdot d\left(x_0,x'\right)
$$

where $\ell(\cdot)$ is a loss function, typically squared error, $d(x_0, x')$ is a distance metric (e.g., Manhattan or Euclidean) and $\lambda$ controls the trade-off between prediction accuracy and proximity to the original instance.

While Wachter's formulation provides a solid mathematical foundation, numerous alternative approaches have been developed to address various aspects of counterfactual generation. In future posts, we will explore these methods in more detail and also present our own findings on effective ways to generate useful counterfactual explanations.

# More Examples: CFEs in Action

Let’s bring CFEs to life with a few scenarios:

**Healthcare**: An AI says no surgery is needed. CFE: “If your blood pressure were 10 points higher, it’d say yes.”

**Hiring**: You’re not hired. CFE: “With 2 more years of experience, you’d make the cut.”

**Spam Filter**: An email’s flagged. CFE: “Drop the word ‘free,’ and it’s safe.”

These examples show how CFEs reveal what truly matters in model decisions. By examining these decision boundaries,
we can better assess if the AI is making fair judgments. Is it reasonable that a small change in blood pressure 
completely flips a medical recommendation? Should two years of experience be the deciding factor in hiring? 
CFEs help us question whether models are using appropriate criteria when making important decisions about people's lives.

# Why CFEs Matter: Real-World Impact

Counterfactual explanations aren't just theoretically interesting &mdash;they have profound real-world implications:

**Regulatory Compliance**: The EU's GDPR includes a "right to explanation" for algorithmic decisions. CFEs provide a clear, actionable way to satisfy this requirement.

**Empowering Users**: By showing paths to different outcomes, CFEs empower individuals to take action rather than simply accepting algorithmic decisions.

**Uncovering Model Biases**: When counterfactuals consistently suggest changes to sensitive attributes (gender, race, age), this may indicate problematic patterns in the model.    

**Building Trust**: Transparent, actionable explanations build trust in AI systems&mdash;essential for widespread adoption of algorithmic decision-making.

**Improving Models**: Examining counterfactuals helps data scientists understand model behavior and identify opportunities for improvement.

# Conclusion

Counterfactual explanations represent a fundamental shift in how we think about AI transparency. 
Rather than simply explaining what is, they illuminate what could be.
As AI systems become more deeply integrated into critical decision processes, 
the ability to understand not just why a decision was made but how it could be different will
be essential &mdash; for users, for developers, and for society.

At genwro.AI, we're committed to advancing this field, creating explanations that are not 
just technically sound but genuinely useful for humans interacting with AI systems.
In next posts, we will dive deeper into various existing methods of generating counterfactual explanations and present some of our own findings.
Stay tuned! :wink:
