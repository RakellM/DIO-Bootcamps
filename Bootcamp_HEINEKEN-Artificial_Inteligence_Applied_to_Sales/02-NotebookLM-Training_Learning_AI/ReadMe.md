# 🧠 Data Science Model Toolkit: Why One Model Never Solves Everything

## 📍 Context & Objectives

### Theme
Data Science is not about finding a "magic model", it's about having a **systematic decision process** to match the right model to the right problem.

### What I Learned in This Project
This study guide explores how to build a **mental toolkit** of models and, more importantly, **when to use each one** based on:
- Problem type (regression, classification, clustering, etc.)
- Data size and quality
- Interpretability needs
- Computational resources

### My Learning Objectives
- Understand the **step-by-step workflow** for model selection
- Compare **5 core model families** (Linear Models, Trees, SVM, Neural Nets, k-NN)
- Create a **decision flowchart** I can use in real projects
- Document **prompts that work** to extract practical advice from NotebookLM


## 📚 Sources

I selected these open-access sources to build my study guide:

| # | Source | Type | Why I Chose It |
|---|--------|------|----------------|
| 1 | ["Choosing the Right Estimator" - scikit-learn cheat sheet](https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html) | Interactive guide | Official, visual, practical |
| 2 | ["Which Machine Learning Algorithm to Use?" - Analytics Vidhya](https://www.analyticsvidhya.com/blog/2020/03/choosing-right-machine-learning-algorithm/) | Article | Real-world decision framework |
| 3 | ["A Tour of Machine Learning Algorithms" - Machine Learning Mastery](https://machinelearningmastery.com/a-tour-of-machine-learning-algorithms/) | Article | Clear categorization by learning style |
| 4 | [Introduction to Statistical Learning (Chapter 2 - ISL)](https://www.statlearning.com/) (free PDF) | Textbook chapter | Academic but accessible |

> *Note: All sources are publicly available. I uploaded the text/PDF versions to NotebookLM.*

---

## Engineering Prompts & Troubleshooting Log

Here I document my prompt experiments, what have worked, what have failed, and how I adjusted.

### Prompt Test #1: General Question (Too Vague)

**Prompt:** *"Tell me about machine learning models"*

**Response from NotebookLM:** Very broad, listed 20+ models without comparison.

**Problem:** Too generic. The AI didn't know what aspect I cared about.

**Fix I Tried:** Added constraints and a specific goal.


### Prompt Test #2: Structured Framework (Worked)

**Prompt:** *"Based only on the 4 sources, create a step-by-step decision framework to choose a model. Start with: 'What is your problem type?' and go through at least 5 decision nodes."*

**Response:** Excellent! Gave a flowchart-like structure with questions:
1. Supervised or unsupervised?
2. Regression, classification, or clustering?
3. How many features?
4. Need interpretability?
5. How much training data?

**What I Learned:** The AI performs much better when you ask for a **structure** (step-by-step, decision tree, table).

![img](./images/NotebookLM-Mind_Map.png)


### Prompt Test #3: Comparison Table (Worked with Refinement)

**Prompt:** *"Make a comparison table of Linear Regression, Decision Tree, SVM, Neural Network, and k-NN."*

**Response:** Table was too simple (only accuracy vs speed).

| Model                            | Grouping                   | Learning Style            | Typical Use Case                            | Key Characteristic                                                                            |
| -------------------------------- | -------------------------- | ------------------------- | ------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Linear Regression**            | Regression Algorithms      | Supervised                | Predicting a quantity (e.g., house prices). | Models relationships between variables and refines them using an error measure.               |
| **Decision Tree**                | Decision Tree Algorithms   | Supervised                | Classification and Regression.              | Constructs tree structures based on attribute values; known for being fast and accurate.      |
| **SVM (Support Vector Machine)** | Instance-based             | Supervised                | Category prediction (<100K samples).        | Finds "support vectors" in the feature space to define boundaries between classes.            |
| **Neural Network (ANN)**         | Artificial Neural Networks | Supervised / Unsupervised | Pattern matching in complex data.           | Inspired by biological structures; involves an enormous subfield including **Deep Learning**. |
| **k-NN (k-Nearest Neighbor)**    | Instance-based             | Supervised                | Predicting categories or structures.        | Compares new data to a stored database of examples using similarity measures.                 |



**Problem:** Not enough comparison dimensions.

**Fix I Tried:** *"Add rows for: data size needed, interpretability (1-5), training time, risk of overfitting, and best use case example."*

**Result:** Perfect 5x5 comparison table I could use in my mini-guide.

| Feature                    | Linear Regression                                                   | Decision Tree                                                               | SVM                                                              | Neural Network                                                          | k-NN                                                                   |
| -------------------------- | ------------------------------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Data Size Needed**       | Typically **<100K samples** for standard versions.                  | Variable; can be fast and accurate on various sizes.                        | Recommended for **<100K samples** in classification.             | Requires **very large datasets** of analog data.                        | Recommended for **<100K samples**.                                     |
| **Interpretability (1-5)** | **4** - High; models simple relationships as a line of best fit.    | **5** - Highest; forks based on **actual attribute values**.                | **2** - Low; based on complex geometric **support vectors**.     | **1** - Lowest; massive, complex subfield with hundreds of variations.  | **3** - Moderate; logic is based on simple **similarity measures**.    |
| **Training Time**          | **Fast**; uses iterative refinement via error measures.             | **Fast**; known for speed in making prediction decisions.                   | **Moderate**; involves finding optimal boundaries.               | **Long**; exploits "abundant cheap computation" for complex structures. | **Very Fast**; it simply stores the training instances in a database.  |
| **Risk of Overfitting**    | **Low to Moderate**; mitigated by **Regularization** (Lasso/Ridge). | **High**; often improved by using **Ensemble** versions like Random Forest. | **Moderate**; defined by the margin between support vectors.     | **High**; due to high complexity and number of parameters.              | **High**; highly sensitive to the specific instances stored in memory. |
| **Best Use Case Example**  | Predicting **quantities** like a stock price.                       | Clear, **rule-based classification** (e.g., medical diagnosis).             | **Category prediction** with smaller, high-dimensional datasets. | Complex patterns in **images, text, or video**.                         | Finding a match based on **historical similarity**.                    |



### Prompt Test #4: Edge Cases (Interesting)

**Prompt:** *"What if I have 1 million rows but only 5 features? Does the answer change?"*

**Response:** Yes, AI explained that tree-based models scale better than SVM or k-NN at that size.

**What I Learned:** Always ask **"What if...?"** follow-ups. That's where real insight lives.



### 📊 Summary of What Worked vs. What Didn't

| ✅ What Worked | ❌ What Didn't |
|----------------|----------------|
| Asking for step-by-step frameworks | Vague open-ended questions |
| Comparison tables with explicit dimensions | "Tell me about X" |
| Follow-up "what if" scenarios | Ignoring source constraints |
| "Based only on these sources" | Asking for future predictions |



## Mini-Guide of Study (Final Delivery)

### Part 1: Structured Summary

#### The 5-Step Model Selection Workflow

Based on synthesized knowledge from all sources:

| Step | Question to Ask | Possible Answers |
|------|----------------|------------------|
| 1 | Supervised or unsupervised? | Supervised → go to step 2; <br> Unsupervised → consider clustering (k-Means, DBSCAN) |
| 2 | Regression, classification, or clustering? | Regression → Linear/Ridge/Lasso; <br> Classification → go to step 3 |
| 3 | How many features (p) and samples (n)? | n >> p → Linear models work well; <br>p >> n → Regularization or tree-based |
| 4 | Need interpretability? | Yes → Linear/logistic regression or shallow decision tree; <br>No → Neural net or ensemble |
| 5 | Small data (<10k) or big data (>100k)? | Small → SVM, k-NN work; <br> Big → Tree ensembles (Random Forest, XGBoost) |

#### Quick Reference: When to Use Which Model

| Model | Best For | Avoid When |
|-------|----------|-------------|
| **Linear/Logistic Regression** | Interpretability, few features, linear relationships | Complex non-linear patterns |
| **Decision Tree** | Simple rules, mixed data types | Small changes in data cause big changes (high variance) |
| **Random Forest** | High accuracy, handles non-linearity well | Need extreme interpretability (black box-ish) |
| **SVM (with RBF kernel)** | Small to medium datasets, clear margin separation | n > 20,000 samples (too slow) |
| **k-NN** | Low-dimension data (<20 features), lazy learning acceptable | High dimensions (curse of dimensionality) |
| **Neural Network** | Very large data, images, text, speech | Small data, need explainability |



### Part 2: Glossary of Key Concepts

| Term | Definition (in my own words) |
|------|-------------------------------|
| **Interpretability** | How easily a human can understand *why* a model made a prediction. <br>Linear models = high; <br>Neural nets = low. |
| **Bias-Variance Tradeoff** | Simple models underfit (high bias); complex models overfit (high variance). <br>Goal: find the sweet spot. |
| **Curse of Dimensionality** | As features increase, data becomes sparse. Distance-based models (k-NN, SVM) struggle. |
| **Ensemble Method** | Combines multiple models (e.g., Random Forest = many decision trees). Often more accurate but less interpretable. |
| **Supervised vs. Unsupervised** | Supervised: knows answers (labels). <br>Unsupervised: finds hidden patterns (clustering). |
| **Regularization** | Penalizes complex models to reduce overfitting (Lasso, Ridge, ElasticNet). |
| **Decision Boundary** | The surface separating different classes in feature space. Linear models draw straight lines; trees draw boxes. |



### Part 3: Reusable Prompts for Future Review

Save these prompts to reuse with NotebookLM (or any AI) when studying a new data science topic.

#### For Model Comparisons

```
Create a comparison table of [MODEL 1], [MODEL 2], [MODEL 3] with rows for:
- Data size needed
- Interpretability (1-5)
- Training time (low/medium/high)
- Risk of overfitting
- Best use case example
Use only the uploaded sources.
```

#### For Decision Frameworks

```
Based on the uploaded sources, create a step-by-step decision tree starting with:
"[FIRST QUESTION, e.g., Regression or Classification?]"
Include at least 5 decision nodes and end with specific model recommendations.
```


#### For Understanding Tradeoffs

```
Explain the tradeoff between [CONCEPT A] and [CONCEPT B] using concrete examples from the sources. Then give me 3 "what if" scenarios that test this tradeoff.
```


#### For Troubleshooting My Own Project

```
I have a dataset with [N] rows and [P] features. The problem is [REGRESSION/CLASSIFICATION]. I need [HIGH/LOW] interpretability. Walk me through your recommended model selection process using the sources. At each step, tell me what to check in my data.
```

#### 📌 For Quick Review Before an Interview

```
Generate 5 quiz questions about model selection, with answers, based only on the uploaded sources. Make them practical ("You have X scenario — which model and why?")
```

## Final Reflection

> **Biggest lesson from this project:**  
> Asking the right question to an AI is a skill. Vague prompts give vague answers. Structured prompts with constraints, dimensions, and "based on these sources" turn NotebookLM from a toy into a true study partner.

> **For my future self:**  
> When I face a new dataset, I will literally use the 5-step framework above before writing a single line of code. And I'll keep this prompt log as a template for studying any technical topic.



## Repository Info

- **Author:** Raquel Marques
- **Date:** 2026-06-07
- **Topic:** Data Science Model Toolkit
- **Tools Used:** NotebookLM, GitHub, scikit-learn documentation
- **DIO Challenge:** *Aprendizagem Ativa com NotebookLM*


