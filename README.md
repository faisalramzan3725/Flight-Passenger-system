# Flight-Passenger-system
For the given classification task, we are following the given steps to perform classification task. The detail explanation about these following steps is mentioned in jupyter notebook (flight_passager_prediction_using _RFC.ipynb). Steps: • Data Analysis. • Data Cleaning and Preprocessing. • Data Exploration and Visualization. • Preparing Features and Target. • Classification Model and Predictions. • Evaluation of model (Results) • Parameter fine tuning. • Classification Results. Background: Classification Model working steps: Random Forest Model works in four steps: • Select random samples from a given dataset. • Construct a decision tree for each sample and get a prediction result from each decision tree. • Perform a vote for each predicted result. • Select the prediction result with the most votes as the final prediction.  Fig (a) RFC Algo  2. How do you check the validity of the model found? Ans: Generally, we use different evaluation methods (Accuracy, F1_score and confusion matrix) to measure the performance of our model that measure how much model is good to classify the samples from different classes. As in the given task, during data analysis and visualization phase we observed that our classes are imbalance means we have unbalance set of classes or instances as shown in the histogram distribution in the python notebook. Random Forest Classifier (RFC) perform well and have a final accuracy score of 0.994% on the test data with updated number of parameters. That is pretty good but, in such situation, when we have imbalance classes the accuracy is not consider as great measure to evaluate the model performance. So, we use F1 score (0.993%) metric to evaluate the performance of our model prediction because F1 score metric is used when we have imbalance dataset or set of classes. Furthermore, we need to check that our model performs equally well for each class? Were there any pairs of classes it found especially hard to distinguish? So, to deal with such type of problems we need to find out the confusion matrix for more information. A confusion matrix Fig(b) shows how many of a classifier’s predictions were correct, and when incorrect, where the classifier got confused. In the confusion matrices below Fig(b), the rows represent the true labels and the columns represent predicted labels. Values on the diagonal represent the number (or percent, in a normalized confusion matrix) of times where the predicted label matches the true label. Values in the other cells represent instances where the classifier mislabeled an observation; the column tells us what the classifier predicted on test set, and the row tells us what the right label are shown below.  Fig (b): Confusion Matrix  3. As new step, can you accept that the algorithm does not identify all the person who have been saved, but want to have much more certainty that the person identified by the algorithm have really been saved? Ans: In the section of preparing features for test sets shown in given figure.  Fig (c)  As comparison with Fig (b) and Fig (c), it is quite clear in the confusion Matrix, in the confusion matrix that shows the passengers who have actually survived (actual: 73) in ground truth fig (c) and our model found 72 out of 73 to be predicted survived (TP) that is acceptable because as per mentioned statement that the algorithm does not identify all the passenger who have been saved. For example, in the confusion matrix, one person (FN) is actually survived in ground truth but our algorithm does not identify them so the statement is acceptable because it’s not identified all. Secondly, about the certainty of the model prediction shows the predicted 72 passenger is survived out of 73 passengers. So, our model confirms those 72 passengers (TP) who is predicted survived which is same and belong to the actual passenger who are survived in given dataset. This model can perfectly evaluate the difference between two classes (survived, not survived). If we need to check the variations of result, we need to change the hyperparameters to check some of the misclassification’s results. For better performance, through cross-validation technique on training set, we found the exact number of depths of tree which need to expand and provide optimal result. Classification Report: The confusion matrix tells us exactly where mistakes were made, but it doesn’t give us summary metrics like precision, recall, or F1 score. We need to get even more insight into model performance, we should  examine other metrics like precision, recall, and F1 score, it can be managed through classification report as shown in Fig (d) below:  Fig(d): Classification report  Precision is the number of correctly-identified members of a class divided by all the times the model predicted that class. Recall is the number of members of a class that the classifier identified correctly divided by the total number of members in that class. F-Measure is a popular metric for imbalanced classification. F1 score is a little less intuitive because it combines precision and recall into one metric. If precision and recall are both high, F1 will be high, too. If they are both low, F1 will be low. If one is high and the other low, F1 will be low. F1 is a quick way to tell whether the classifier is actually good at identifying members of a class, or if it is finding shortcuts (e.g., just identifying everything as a member of a large class). Additionally used when we have unbalance set of instances or classes so we use F1-score to determine the model is performing good or not. Conclusion: In the classification task, the RFC classifier was used to classify the given binary class problem. Initially we analyzed, preprocess and visualize the data for better understanding about the given data also we demonstrate the quality and check the distribution of data. During finetuning of RFC classifier, we make prediction on both training and test samples in order to find the difference between two classes. After the predictions, we analyze the result achieved by our model with updated parameter’s that shows our given data is perfectly classified between the given classes. It is exactly classified the number of predicted survived (72) out of the actual survived (73) and predicted not survived passengers (106) is equal to the actual not survived passengers.
