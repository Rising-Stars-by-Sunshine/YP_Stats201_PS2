# Method

## Description:
The following content is the **METHOD** part of the project. It contains the Prediction Problem and the Machine Learning Workflow.

## 1.1 The Prediction Problem

### Research Question Formulation:

**Objective:** The specific research question aims to identify predictive factors associated with student dropout or successful degree completion, particularly focusing on non-academic factors such as socioeconomic background and student demographics.

**Significance:** Research has consistently shown that non-academic factors, such as socioeconomic status and financial circumstances, significantly impact student persistence and dropout rates (Tinto, 2017; Pascarella & Terenzini, 2005). This question is crucial in the field of higher education as understanding the multifaceted determinants of student outcomes can inform targeted interventions and support services, ultimately enhancing retention rates and improving educational equity.

### Operational Measures:

**Dependent Variable (Y):** Student academic success (Graduate/Dropout) (rate)

**Independent Variable (X):** Demographic Variables (e.g., age, gender), Financial Circumstances (e.g., debt), Student Background (e.g., Parent's qualification), Social-Economic Factors (e.g., Area GDP)

**Datatype:** Cross-sectional

### Hypothesis Development:

**Prediction Hypothesis:** It is hypothesized that students with lower levels of socio-economic status, weaker financial circumstances, and less advantageous student backgrounds are more predisposed to dropout from higher education institutions.

**Justification:** This hypothesis is grounded in established literature indicating that socio-economic factors, financial constraints, and student background significantly impact educational attainment and persistence. Individuals from disadvantaged socio-economic backgrounds often face greater barriers to academic success, including limited access to resources, inadequate support systems, and heightened financial strain. Moreover, research suggests that students with parents possessing lower qualifications may lack familial role models and support networks conducive to academic achievement, further exacerbating their risk of dropout. By addressing these underlying social determinants of education, institutions can better tailor interventions and support services to mitigate dropout rates and promote equitable educational outcomes.

**Machine Learning Algorithm Selection:** XGBoost (eXtreme Gradient Boosting) is the optimal choice for analyzing student dropout risk in higher education due to its robust capabilities and versatility. Its scalability, flexibility, and regularization techniques enable accurate predictions by capturing complex relationships within large datasets efficiently. With its ability to handle diverse data types and provide feature importance analysis, XGBoost offers insights into the factors driving student dropout. Its proven high performance in predictive modeling tasks, combined with interpretability, makes it ideal for informing targeted interventions to improve student retention rates. Therefore, the selection of XGBoost is grounded in its ability to address the complexities of predicting student dropout effectively.

## 1.2 The Machine Learning Workflow

### Model Development:
**Data Processing:** We deleted the "Enrolled" within the data since we are analyzing academic success/dropout. We then made 0 represent "Dropout" and 1 represent "Graduate". "Nationality" was deleted due to high pearson correlation with "International". Qualification and occupations were ranked. We want to focus less on student's academic performance, so the academic performance related columns were deleted. Finally, for "Marital ", "Application mode", "Application order", and "Course", Onehot Encoder was applied.

### Results Presentation:
**Training and Testing:** The code performs a train-test split to evaluate the model's performance. It divides the dataset into two parts: one for training the model (X_train, y_train) and the other for evaluating its performance (X_test, y_test). The split ratio is set to 80-20, where 80% of the data is used for training and 20% for testing. This split helps in assessing how well the model generalizes to unseen data.

**Data Visualization:** The code includes visualization techniques to convey critical insights:

• Confusion Matrix: The confusion matrix is computed using the confusion_matrix function from scikit-learn. It shows the counts of true positive, false positive, true negative, and false negative predictions, providing insight into the model's performance across different classes.

• ROC Curve: The Receiver Operating Characteristic (ROC) curve is plotted using the roc_curve function from scikit-learn. It visualizes the trade-off between the true positive rate and the false positive rate across different thresholds. This curve helps in assessing the model's discriminative ability.

• Feature Importance Plot: Feature importance is visualized using XGBoost's plot_importance function. It shows the importance of each feature in the model's predictions, helping to identify which features have the most significant impact.

### Model Evaluation:
**Evaluation Criteria:** The code specifies evaluation criteria or metrics to assess the model's performance:

• Accuracy: The accuracy score is computed using the accuracy_score function from scikit-learn. It measures the proportion of correctly classified instances out of the total instances, providing an overall assessment of the model's performance.

• Precision, Recall, and F1-score: The classification report is generated using the classification_report function from scikit-learn. It includes precision, recall, and F1-score for each class, providing a detailed evaluation of the model's performance across different classes.

**Iterative Improvement:**
The code outlines strategies for iterative model refinement to enhance its predictive accuracy:

• Balance data: There are more Graduate then Dropout. To address the class imbalance issue where there are more graduates than dropouts, downsampling can be applied to the majority class (graduates) as suggested by Kamiran and Calders (2012).

• Compare model: Model performance can be compared to find best model.

## Flowchart

<img src="Flowchart.png" alt="Flowchart">
Figure 1: Flowchart for Method Created by Whimsical

## Reference
```
@article{kamiran_data_2012,
  title = {Data {{Preprocessing Techniques}} for {{Classification Without Discrimination}}},
  author = {Kamiran, Faisal and Calders, Toon},
  year = {2012},
  month = jan,
  volume = {33},
  number = {1},
  pages = {1--33},
  issn = {0219-1377, 0219-3116},
  doi = {10.1007/s10115-011-0463-x},
  journal = {Knowledge and Information Systems},
}
@book{tinto_completing_2017,
  title = {Completing {{College}}: {{Rethinking Institutional Action}}},
  author = {Tinto, Vincent},
  year = {2017},
  publisher = {{University of Chicago Press}},
  address = {{Chicago}},
}
@book{pascarella_how_2005,
  title = {How {{College Affects Students}}: {{A Third Decade}} of {{Research}}},
  author = {Pascarella, Ernest T. and Terenzini, Patrick T.},
  year = {2005},
  publisher = {{Jossey-Bass}},
  address = {{San Francisco, CA}},
}
```
