# Lab 04 — Exploratory Data Analysis: Titanic Dataset

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Performed a full exploratory data analysis on the Titanic passenger dataset,
visualizing survival rates across gender, passenger class, and age groups to
identify which factors most strongly predicted survival.

## Knowledge Check — Key Questions & My Answers

**What is the primary goal of Exploratory Data Analysis (EDA)?**
EDA's primary goal is to review the data ahead of running in-depth analysis —
by counting, sampling, and visualizing the data's characteristics to understand
the data types, as well as quantitative and qualitative aspects of the dataset.

**What kind of person had the best chance of surviving the Titanic?**
A 1st-class female child had the highest statistical probability of survival.
- **Gender:** Female — survival rate ~74% vs. ~18-19% for men. The single
  strongest predictor of survival ("women and children first").
- **Class:** 1st Class — survival rate over 60%, compared to ~47% for 2nd class
  and ~24% for 3rd class.
- **Age:** Young child — children in 1st and 2nd class had much higher survival
  priority.
- Conversely, a 3rd-class adult male had the lowest statistical probability of survival.

**Why is it important to visualize data instead of just looking at summary statistics?**
Visualizations allow you to observe distribution across class, age, gender, and port of
embarkation — and understand the relationships among them. For instance, higher survival
rates were linked to port of embarkation, fare, and class, all connected to socio-economic
factors. Passengers who boarded at Cherbourg, France tended to be wealthier. A simple
count or mean cannot show that on its own.

## What I Learned
- How socio-economic factors (class, fare, embarkation port) were deeply correlated
  with survival outcomes
- How to read and interpret grouped bar charts, histograms, and survival plots
- Why visualizations are essential — they reveal relationships that averages and counts
  completely hide

## Tools Used
`Python` · `pandas` · `Matplotlib` · `Seaborn` · `Google Colab`

