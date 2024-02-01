# Classification of Leukemia by Gene Expression

## Objective
The objective of this project is to develop a machine learning model for the classification of cancer samples based on gene expression data. Specifically, the project aims to accurately classify samples into acute myeloid leukemia (AML) and acute lymphoblastic leukemia (ALL) categories. 

## Data
There are two datasets:
1. "data_set_ALL_AML_train" - the training sample (includes 38 samples in total)
2. "data_set_ALL_AML_independent" - the test sample (includes 34 samples in total)

Both datasets contain microarray gene expression data from patients with AML and ALL. The first two columns ('Gene Description' and 'Gene Accession Number') contain gene descriptions. 
In total, both datasets contains microarray expression data from 7,129 genes, where each gene is a row in the dataset. Goulb et al. (1999; where this data originates - see below) re-scaled the intensity values such that overall intensities for each chip are equivalent. 
The samples are the columns of the dataset. 
Next to each column for each sample there was a column of a variable named "Call", which has one of three values - "A", "P", or "M". These stand for Absent, Present and Marginal. They are based on the signal in the microarray for a gene at hand and they determine a gene's expression in a sample.  

There is a third file called 'actual' that contains the actual type of leukemia each patient has. 

## Model
A random forest classifier was implemented using scikit-learn. 

## Results
The model's overall precision and accuracy were good, producing an F1 score of 0.78. Nevertheless, it became clear from examining the results for each class of leukemia that the model performed better in predicting whether patients had ALL than AML. This could be explained by the unequal distribution of the samples, where a much higher proportion of patients in the training group had ALL compared to AML. 

## Conclusion
This study demonstrates, like in Goulb et al. (1999), the feasibility of predicting leukemia types using gene expression data. It is imperative to recognise, however, that there is room for improvement in the idenification of AML patients. This could be accomplished by starting with a larger and more balanced sample of patients. Additionally, the accuracy this classification model may be considerably increased by applying the aforementioned adjustments, and fine-tuning the selection of features for the model.

## Acknowledgement
This dataset originates from a study conducted by Goulb et al. (1999) in which they used said data to classify the type of cancer in each patient by variation in gene expression.