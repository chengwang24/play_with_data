choose categorical variable as the X, pcr(outcome) as y_target.
X:'ER', 'PgR', 'HER2', 'TrippleNegative', 'ChemoGrade', 'Proliferation', 'HistologyType', 'LNStatus', 'TumourStage'
analyze the relation between each feature and pcr_outcome use chi-square test
![3fec3af734c6fd40c43ef0f8dc7897e](https://github.com/chengwang24/play_with_data/assets/78476126/5390e6f2-595a-41b0-9072-a7bcfad52df3)

ABOVE approach focuses on the individual effects of each variable but does not explicitly measure how the combination of X affects y_target.
To measure the combined effect of variables, a multinomial logistic model was employed. The shorcut of code and results are presented below.
![image](https://github.com/chengwang24/play_with_data/assets/78476126/81d7f97d-f898-4c37-9778-352371b97122)
results:![1706468930229](https://github.com/chengwang24/play_with_data/assets/78476126/62af67b5-0a35-432a-be67-9189d98c5c73)

#The coefficient is positive, indicating a positive correlation. 
#This suggests that an increase in this feature may increase the probability of the sample being classified as the positive class.
![1706468979938](https://github.com/chengwang24/play_with_data/assets/78476126/9d7c0137-20d6-4ce5-b067-0d11aca9ef9c)

Two methods were attempted to address the imbalanced dataset issue:
1.Oversampling using SMOTE (Synthetic Minority Over-sampling Technique).
2.Adjusting the threshold of the logistic model to make it more sensitive. This means the model will make more cautious predictions for the positive class.

