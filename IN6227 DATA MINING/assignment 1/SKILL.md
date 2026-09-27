---
name: end-to-end-classification
description: Explore a classification dataset, train and compare two existing classification models, and generate a short Word report of two pages using the provided Word template.
---

# end-to-end classification

Complete an end-to-end classification experiment. Explore and clean the data, select two existing classification models, train and evaluate them on the provided dataset, and compare their performance using suitable evaluation metrics. Finally generate a report following [assets/IN6227-Reports-Template.doc](assets/IN6227-Reports-Template.doc)

## 1. Read and explore the data

- Read the dataset file or directory provided by the user and identify the training data, test data, and target column.
- Explore the dataset, including the number of rows and features, feature types, class distribution, missing values, duplicates, outliers, and obvious data quality problems.
- Perform reasonable data cleaning when needed. Do not modify the original dataset files. 
- Check the provided Word template[assets/IN6227-Reports-Template.doc](assets/IN6227-Reports-Template.doc) before generating the final report. Create a fresh output folder in the working directory unless the user specifies another location; preserve previous runs.

## 2. Prepare the classification experiment

- Use the provided training and test sets if available. If no test set is provided, create a suitable train/test split.
- Prepare the features for modeling. Handle missing values, categorical features, and numerical scaling when necessary.
- Fit preprocessing steps using the training data only. Use the training data for model selection and parameter tuning, and keep the test data for final evaluation.
- Choose exactly two existing classification models that are suitable for the dataset. Give a short and simple reason for choosing each model.
- Use the same data split for both models so that their results can be compared fairly.
- Select suitable evaluation metrics. Normally include accuracy and F1 score. Add precision, recall, ROC AUC, or other useful metrics when they help explain the results. Briefly explain the choice of the main metric, especially when the classes are imbalanced.

**Checkpoint 1 — Experiment plan.** Briefly show the dataset summary, preprocessing steps, selected models, and evaluation metrics. Ask the user to review the plan and wait for approval before training. Record actual feedback and actions in `checkpoints.md`.

## 3. Train, test, and compare the models

- Write and run a readable Python script or notebook using existing classification models.
- Train both models using the same training data and random seed where applicable.
- Use a small amount of parameter tuning only when it is useful. Avoid large or unnecessary model searches.
- Record the main model configurations, including selected settings, any parameter tuning and stopping criteria or training limits where applicable.
- Evaluate both models on the test data and save their main performance metrics.
- Compare the two models using the selected metrics. Explain the main differences in simple terms and identify which model performs better for this task.
- Save a results table and test predictions when applicable.

**Checkpoint 2 — Results review.** Show the main results of both models, together with a confusion matrix or several prediction examples when useful. Ask the user to review the results and wait for approval before generating the final report. Record actual feedback and actions in `checkpoints.md`.

## 4. Generate the editable Word report

Create an editable English Word report (`report.doc`) from a copy of `assets/IN6227-Reports-Template.doc`. Keep the original template layout, formatting, headings, margins, and font style. The complete report should be two pages.

Write the report in clear and natural academic English suitable for a university coursework report. Focus on what was done, why it was done, the main results, and what the results mean. Keep technical details only when they help the reader understand the experiment. Do not include unnecessary details such as package versions, low-level runtime settings, iteration tolerances, number of workers, software installation problems, or debugging history.

The report must clearly cover all five criteria below:
- Data exploration and cleaning: Describe the dataset and its main characteristics. Identify relevant issues such as missing values, outliers, duplicates, or class imbalance. Explain the preprocessing steps that were applied and why they were needed.
- Feature selection/engineering (if applicable): Explain any feature selection, transformation, or feature engineering that was performed and the reason for doing it. If no feature selection or engineering was needed, briefly explain why.
- Model training: Describe the two classification models and their main configurations. Include any hyperparameter tuning that was performed and briefly describe the stopping criteria or training limits where applicable. Focus on settings that are useful for understanding the experiment rather than unnecessary implementation details.
- Evaluation and comparison: Compare the two models using suitable evaluation metrics. Present the main results clearly, preferably using a comparison table. Explain the important differences between the two models rather than only listing metric values.
- Findings and discussion: Summarize the main findings and discuss what can be learned from the comparison. Explain important strengths, weaknesses, trade-offs, or limitations, and state which model performed better for the task based on the results.

Add a simple visual when it helps explain or compare the model results more clearly,  for example, but not limited to, a confusion matrix or a small comparison chart. 

Aim to make effective use of the two-page limit. The report should normally be close to two pages without exceeding two pages.

Use the template sections as follows:

| Template section | Required content |
| --- | --- |
| INTRODUCTION | Introduces the dataset, classification problem, important dataset characteristics, the purpose of the experiment, and the two models being compared. Do not present detailed model results in the introduction. |
| METHODS OR PROCEDURES | Cover **Data exploration and cleaning**, **Feature selection/engineering**, and **Model training**.  |
| RESULTS | Cover **Evaluation and comparison**. Present the main model comparison clearly. Use a table for the key metrics. Include a visual that adds useful information to the comparison, for example, but not limited to, confusion matrices, model comparison charts, ROC curves, or feature importance plots. |
| DISCUSSION | Cover **Findings and discussion**, including the main differences, trade-offs, and limitations.  |
| CONCLUSION | Give a overall conclusion based on the experiment results. |
| REFERENCES | Only sources actually used. Remove the template's unrelated example references. |

Keep the Word report within **two pages** and keep the report concise and readable. If the report is substantially shorter than two pages, improve the useful content or presentation before finalizing it. If it exceeds two pages, remove repeated explanations and low-value technical details first instead of reducing the font size or spacing. Before finishing, check that all five criteria are clearly covered and that all reported values match the actual experiment results.

Deliver report.doc, the runnable Python script or notebook, the results table, test predictions when applicable, and checkpoints.md.
