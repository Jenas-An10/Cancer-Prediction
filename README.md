   ### Applied Human Computational Genomics ​

   ### Georgia Institute of Technology​

### By Joseph Luper Tsenum, Xu Qiu, Zun Wang​

   ## Cancer-Related LncRNA Machine Learning Predictor App (CaRLMaLP R-Shiny App)
#### Introduction

Long Noncoding RNAs, or lncRNAs are RNAs not translated into proteins. Recent studies have shown that lncRNAs play a crucial role in cancer through their regulations of biological pathways. Cancer-Related LncRNA Machine Learning Predictor App (CaRLMaLP R-Shiny App) is a Web-based user interface for predicting cancer-related lncRNAs by integrating manifold features (genomic, expression, epigenetic and network features) with five machine-learning techniques (Random Forest (RF), Naïve bayes (NB), Support Vector Machine (SVM), Logistic Regression (LR) and K-Nearest Neighbors (KNN). With this App, predicting novel cancer-related lncRNA with high accuracy and efficiency is possible. This App was developed using R Shiny and based on the machine learning work from [CRlncRC](https://bmcmedgenomics.biomedcentral.com/articles/10.1186/s12920-018-0436-9). Also, our full training dataset is originated from CRlncRC, containing 11963 genes and 85 features. To learn more, please listen to our introductory video at https://www.youtube.com/watch?v=f4Hc0oom1tE.
                

## User manual 

### Run App 
The website to our CaRLMaLP R-Shiny App is at https://zunwang0513.shinyapps.io/cancer-related_lncrna_ml_predictor_app_carlmalp_shiny/ or https://xp5n20-joseph-tsenum.shinyapps.io/cancer_related_lncrna_ml_predictor_carlmalp_shiny1/  
Please, upload the user feature file in the Input panel, choose the machine learning algorithm to run the app.

### Create Input
Input should be a csv file with Gene_ID as the first column (can be any form of Gene ID), the rest of the file should contain some of the columns (does not have to be all) in the features file 'feature_set.csv'. Our features file contains 4 types of integrated feature: genomic features, epigenetic features, expression features, network features.


For more information on how to generate integrated features, please refer to supplementary material of [CRlncRC2](https://www.frontiersin.org/articles/10.3389/fgene.2019.00735/full#supplementary-material)

### Result Interpretation
#### Machine Learning Panel
After uploading features for each Gene_ID, users can choose a machine learning algorithm from the drop-down menu. Then click run to start the machine learning. Since the user input may have less number of features, this app provides the confusion matrix and AUC ROC curve as indicators for the robustness.
##### Prediction Result
The prediction result contains a table: the first column is the Gene_ID provided by the user, the second column is the prediction result. 1 means positive cancer-related, and -1 means negative cancer-unrelated.
##### Confusion Matrix
The confusion matrix plot counts the number of true positives, true negatives, false positives, and false negatives for the trained model. The higher the number of true positives and true negatives, the more robust the model is.
##### AUC ROC Curve
Area under the ROC curve demonstrates the accuracy of the model trained, also indicating the accuracy of the prediction. The closer the area under curve to 1, the higher the accuracy of the prediction.
##### Feature Importance
Users can view the contribution of each feature they provide. We provided feature importance ranking for three of our algorithms: Naive Bayes, Logistic Regression, and Random Forest. The higher the feature index on the y-axis, the more important the feature is in the course of determining prediction outcome. For kNN and SVM, it is unable to provide the feature importance due to the nature of the algorithm. 
![modified](https://github.gatech.edu/storage/user/56953/files/b8b1fc6f-d9fc-4935-8c44-c82bfad1e193)

#### PCA Panel
On the other panel, we provided a PCA plot for the interpretation of the result as well. Also, by uploading the user's features and choosing the machine learning algorithm, and then click run, the PCA will start running. The user can see if PCA has a similar cluster pattern with the prediction result.
![modified2](https://github.gatech.edu/storage/user/56953/files/658320b6-a8d7-4d20-a79a-6cc6b5bc198d)

### Contact Us

1. Joseph Luper Tsenum: jtsenum3@gatech.edu
2. Xu Qiu: xqiu64@gatech.edu
3. Zun Wang: zwang3311@gatech.edu

Engineered Biosystems Building (EBB)

Georgia Institute of Technology

950 Atlantic Drive Atlanta, GA 30332

### References

1. Zhang, X., Wang, J., Li, J. et al. CRlncRC: a machine learning-based method for cancer-related long noncoding RNA identification using integrated features. BMC Med Genomics 11 (Suppl 6), 120 (2018). https://doi.org/10.1186/s12920-018-0436-9

2. Pedregosa et al. Scikit-learn: Machine Learning in Python. JMLR 12, pp. 2825-2830, 2011.

3. Chang W, Cheng J, Allaire J, Sievert C, Schloerke B, Xie Y, Allen J, McPherson J, Dipert A, Borges B (2022). shiny: Web Application Framework for R. R package version 1.7.4, https://shiny.rstudio.com/.
