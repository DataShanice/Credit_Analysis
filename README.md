# Credit_Analysis  

I created machine larning models to evaluate credit risk and predict outcomes for loan applications. The dataset for this exercise is from LendingClub. Since the number of declined loans is far greater than the number approved, the data is imbalanced and the ml models must be adjusted to ensure there is either no or minimum sampling bias. I developed and evaluated imbalanced sample models. Following is a summary of my analysis.  

## Oversampling
I tested two oversampling models: (i) Random oversampling; and (2) SMOTE oversampling. In each case, and for other models discussed below, I first encoded the data as required and dropped rows with incomplete or incorrect data. Also, to normalize the outcomes for teh classifier, the loan_status column data is coded as low-risk or high-risk instead of the multiple options in the original dataset.

Results of Random oversampling:  
The balanced_accuracy_score if 0.63, which is the average of recall obtained by using the model. This is a low score for an application like credit decisions and indicates the model is not a good fit. The f1 scores for the model are also very low at 0.02 for high_risk and 0.81 for low_risk predictions.

Results of SMOTE oversampling:
SMOTE oversampling is a methd of synthesizing additional sample data from existing data, which is an alternative to oversampling from the actual data set. I created a SMOTE model to evaluate fit with the dataset. The SMOTE model performed more weakly than random oversampling, with a balanced accuracy score of just .604. Similarly, the f1 score for high_risk and low_risk are 0.02 and .78, which indicate the model is not a good fit.  

## Ensemble classifiers  
Since our oversampling models do not fit teh dataset well, I created two ensemble classifier models. The general principle of an ensemble classifier is to build diffreent prediction models from the data and combine the predictions algorithmically. I tried two approaches: (3) Balanced Random Forest Classifier; and (4) Easy Ensemble AdaBoost Classifier.

Results of Balanced Random Forest Classifier:  
The balanced_accuracy_score improved significanlty 0.7885, with this model. However, the f1 scores for the model are still low at 0.06 for high_risk. But for low_risk, the f1 score was much higher at 0.93. The weights that the model assigned to different factors indicates a large number of contributing factors with mid to small scale impacts. In other words, few factors were dispositive. This model, while better, is still not reliable for credit decisons.  

Results of Easy Ensemble AdaBoost Classifier:  
This model also achieves a high balanced score of 0.9154. However, the f1 score for high_risk is 0.06, though it is a much higher 0.95 for low_risk. This model is also not a good fit overall.

## Conclusions  
The data is unbalanced and models with oversampling and ensemble approaches do not produce a good fit. As our module learning suggests, a low f1 score points to a pronounced imbalance between sensitivity and precision. We will need more data over longer periods of time, and perhaps a better refines set of features, to predict the target better.
