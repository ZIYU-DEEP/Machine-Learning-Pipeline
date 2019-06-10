# Machine Learning Pipeline - Report

- **Which classifier does better on which metrics?**
  - Considering both *precision* and *recall* *rates* at 0.01, 0.02 and 0.05, the best results include **random forest** and **logistic regression**.
  - Although the *precision* and *recall* *rates* looks satisfactory, it is important for us to compare them with the baseline. We could simply use the following success rate as a baseline reference:
    - In 2012, there were 84,550 fully funded projects and 33,076 not funded
      projects out of 117,626 projects, yielding a success rate of 71.88%.
    - In 2013, there were 92,399 fully funded projects and 38,930 not funded
      projects out of 131,329 projects, yielding a success rate of 70.36%.
  - Clearly, our result would outpreform such a baseline.



- **How do the results change over time?**

  - There is a upward trend for the classifiers' performances. This is comprehensible, as the data itself can be viewed as "grown steadily", and there should not exist much heterogeneity across all the data in two years. Therefore, the more training example the data has learned, th better it preformance would be.

    

- **What would be your recommendation to someone who's working on this model to identify 5% of posted projects that are at highest risk of not getting fully funded to intervene with, which model should they decide to go forward with and deploy?**
  - In terms of *best performance*, I would recommend **random forest** with `max_feature = 15`. Its precision and recall rates at 0.05 are definitely among the best. Also, this method is ***robust to data variations*** (technically speaking, it uses a decision threshold of 0.7), and the training process supports parallel computing, which means the process can be easily ***speeded up***. In addition, it mantains a ***lower variance*** compared to other classifiers (technically speaking, its AUC-ROC score is higher), which implies it has a better ***generalizability***.
  - In terms of *simplicity* and *interpretability*, I would recommend **Logistic Regression** with `penalty = L1` and `C = 0.001`. Its precision and recall rates at 0.05 are definitely among the best. More importantly, it is ***easy to understand***, which makes its result more meaningful to nonprofessionals.