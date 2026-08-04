# Lab 13 — Production-Ready ML Pipelines

**Course:** ITAI 1371 — Introduction to Machine Learning
**Author:** Cesar Zaldivar

---

## What I Did
Built and compared a manual preprocessing workflow against a scikit-learn Pipeline,
demonstrating how Pipelines prevent data leakage, simplify code, and make models
safer to deploy in real-world production systems.

## Results
- **Pipeline Model Accuracy:** 82.68%

## Knowledge Check — Key Questions & My Answers

**What are the three biggest advantages of using a Pipeline over the manual approach?**
1. **No missed steps:** The pipeline always keeps all preprocessing steps in the correct
   sequence, removing uncertainty from the process.
2. **Cleaner, more modular code:** Steps are encapsulated as reusable modules, making the
   code easier to read, maintain, and modify.
3. **Automatic data leakage prevention:** The pipeline ensures preprocessing steps are
   fitted only on training data — never on the test set.

**Why is the fit/transform distinction crucial, and how does the Pipeline handle it?**
`fit_transform()` is run only on the training set because its function is to learn the
data's distribution (mean, std) before transforming it. If `fit_transform()` were called
on the test set, the scaler would learn the test set's distribution — meaning the model
would have effectively "seen" the test data, making accuracy falsely optimistic. Pipelines
enforce the golden rule automatically: **Fit on Train, Transform on Test**. When you call
`final_pipeline.fit(X_train)`, all transformers fit on training data only. When you call
`.predict(X_test)`, it automatically applies only `.transform()` — you never have to think
about it.

**Where would you add a PCA step to the pipeline?**
I would add `PCA()` as a new step inside `final_pipeline`, between the `preprocessor` and
the `RandomForestClassifier`:
`make_pipeline(preprocessor, PCA(), RandomForestClassifier())`

**Why is handing over one pipeline object safer than 5 separate objects?**
1. **No missing steps or wrong order:** With 5 separate objects, the deployment team could
   apply them in the wrong order or skip one entirely (e.g., forget to scale before the model).
2. **Fewer lines of code = fewer human errors:** With 5 objects, you manually run
   scale → encode → combine → predict. With the pipeline: `final_pipeline.predict(raw_data)` — done.
3. **No version mismatch:** The pipeline bundles everything trained together into one file,
   guaranteeing the scaler and model always correspond to the same training run.

## What I Learned
- How scikit-learn Pipelines eliminate an entire class of data leakage errors automatically
- Why a single serializable pipeline object is far safer for deployment than separate components
- How to think about production ML systems — not just model accuracy, but reliability and
  maintainability

## Tools Used
`Python` · `pandas` · `scikit-learn` · `Google Colab`
