****Evaluation of the Performances of Global Surrogate Models for Deep-learning Machine Learning Model (ML) on Binary Classification problems. ****

**Introduction:** Understanding and interpreting the inner workings of black-box models is challenging due to their “black box” nature. Explainable artificial intelligence (XAI) is a field of research that seeks to explain the how and why of DL model prediction. XAI is intended to increase confidence in decision-making by understanding how models work, behave, and deliver results. Interpretable models are implemented as surrogates to black-box models on binary classification problem (Stroke prediction).
A stroke is a medical condition in which poor blood flow to the brain causes cell death.

**Dataset:**
The dataset used is obtained from Kaggle.
This dataset is imbalanced (95.13% : 4.87% no stroke and stroke respectfully). The dataset was balanced using SMOTE (Synthetic Minority Over-sampling Technique).

<img width="386" height="779" alt="image" src="https://github.com/user-attachments/assets/8b55f1cb-ed99-4f9f-a837-10e286111fc8" />



**Context:**
There are two main types of stroke: ischemic, due to lack of blood flow, and hemorrhagic, due to bleeding. Both cause parts of the brain to stop functioning properly.
Signs and symptoms of a stroke may include an inability to move or feel on one side of the body, problems understanding or speaking, dizziness, or loss of vision to one side. Signs and symptoms often appear soon after the stroke has occurred.
If symptoms last less than one or two hours, the stroke is a transient ischemic attack (TIA), also called a mini-stroke. A hemorrhagic stroke may also be associated with a severe headache. The symptoms of a stroke can be permanent. Long-term complications may include pneumonia and loss of bladder control.
The main risk factor for stroke is high blood pressure. Other risk factors include high blood cholesterol, tobacco smoking, obesity, diabetes mellitus, a previous TIA, end-stage kidney disease, and atrial fibrillation.
**Black-Box Models used are Random Forest, XGBoost and Neural Networks**
**Random Forest Model:**
The Random Forest classifier is performed with 100 estimators and a random state of 42

**XGBoost Model:**
The XGBoost model is performed with 300 estimators, a maximum depth of 10, and a learning rate of 0.1. These parameters are gained using GridSearchCV.

**Neural Network Model:**
Before performing Neural Network, the dataset was normalized. The model consists of three hidden layers with 400, 400, and 128 neurons respectively, and reLU activation function. Two dropouts are performed for avoiding overfitting. The output layer has a single neuron with sigmoid activation since we are performing binary classification (stroke or no stroke).

**Black-Box Models Evaluation:**
The aim is to find the black-box model that performs better that the others on the dataset on each classification evaluation metric.


<img width="657" height="252" alt="image" src="https://github.com/user-attachments/assets/6b94874b-9cfa-4348-9563-257f36d5ab7a" />
<img width="716" height="247" alt="image" src="https://github.com/user-attachments/assets/f841196c-8793-41ec-807b-1259fb496692" />
<img width="699" height="268" alt="image" src="https://github.com/user-attachments/assets/a8baabd3-22c5-4078-81a2-5575e52d5821" />
<img width="777" height="198" alt="image" src="https://github.com/user-attachments/assets/da7f82c2-6ad0-41fd-9e90-aa870226684b" />
<img width="749" height="398" alt="image" src="https://github.com/user-attachments/assets/2724d06f-1cc1-41e9-99a7-836c72ae8665" />

<img width="526" height="350" alt="image" src="https://github.com/user-attachments/assets/8964ef5d-fc5d-49da-ae07-e4c2779c56b5" />



These Black-box models are evaluated on the classifictation metrics shown above. The ROC_AUC score (Receiver Operating Characters Area Under the Curve) is a metric used to evaluate the performance of a binary classification model by showing the model's ability to differentiate between two classes across all possible classification thresholds. The ROC_AUC score of 1 means the classifier is perfect and 0.5 means a random classifier. Values between 0.5 and 1.0: Represent the model's ability to distinguish between the classes, with higher values indicating better performance. In this case, the Neural Ntwork has a higher ROC_AUC value of
(0.59) compared to XGBost with ROC_AUC value of (0.56) and Random Forest ROC_AUC value of (0.55).

The accuracy score is an evaluation metric is a percentage measure that tells how often a model can correctly predict an outcome. In this case, the  XGBost has the highest accuracy value of (0..90) the followed by the Random Forest with the accuracy value of (0.89) and lastly the Neural Ntwork has the lowest accuracy value of (0.80).

Precision is a metric that measures the accuracy of positive predictions of a model. All these black-box models are good in predicting class (0) that is an individual does not have stroke over balanced data as they scored 94, 94 and 96 in order RF,XGB,NN. This models struggle in correctly predicting the minority class (1) which is an individual has stroke. Based on the precision scores recorede, we can judge XGB (0.85) to have a better precision as it is better in predicting posibilities of stroke than RF(0.17) and NN (0.11).
Recall is metric that measures the ability of a model to correctly identify all relevant instances or positive cases in a dataset. A high recall score shows that the model is effective at finding most of the positive instances, minimizing the number of missed positive cases (false negatives). In this case, the neural network (0.35) has the highest recall than the XGB (0.15) and the RF(0.13).
The F1 score is a machine learning metric that represents the harmonic mean of precision and recall. It is used to evaluate the performance of classification models, particularly when dealing with imbalanced datasets, where one class has significantly more instances than others. A higher F1 score (closer to 1) indicates better model performance, signifying a good balance between precision and recall. Since STOTE was used to balance the data, F1 scores for all the models is marginally different with RF(0.15) and both XGB and NN with approximatly (0.16) score. 

**Surrogate Models   **
**Logistic Regression**
<img width="397" height="162" alt="image" src="https://github.com/user-attachments/assets/a2ecc62c-304d-4401-ab7d-4b5dbab28529" />
<img width="577" height="438" alt="image" src="https://github.com/user-attachments/assets/0b0688b3-735f-4846-93a6-4a0520a318a9" />

<img width="540" height="392" alt="image" src="https://github.com/user-attachments/assets/a7c6a08b-ad5a-4a88-a2aa-0195dc8aa6b4" />
<img width="508" height="365" alt="image" src="https://github.com/user-attachments/assets/9d90de53-77e5-4064-9b35-5622434a4d83" />

**Decision Trees**
<img width="422" height="180" alt="image" src="https://github.com/user-attachments/assets/3ee07fdd-1b44-49c9-97b8-44bde0e557ab" />
<img width="550" height="427" alt="image" src="https://github.com/user-attachments/assets/f67ec43e-8137-42d9-893f-af567f6c8479" />
<img width="513" height="366" alt="image" src="https://github.com/user-attachments/assets/ca010dfd-ee49-4734-a3a2-904b7fef35a6" />
<img width="536" height="380" alt="image" src="https://github.com/user-attachments/assets/feb78d7d-e37c-44fe-9eaf-49f0a31dd908" />

**Naive Bayes**
<img width="433" height="171" alt="image" src="https://github.com/user-attachments/assets/421df602-3835-4e5b-8316-d83640e473e5" />
<img width="612" height="428" alt="image" src="https://github.com/user-attachments/assets/d0555b46-df8b-4326-b3e5-c777e7a8b123" />
<img width="527" height="364" alt="image" src="https://github.com/user-attachments/assets/abe32785-1e68-40c5-9a65-9fbbcc165d13" />
<img width="514" height="379" alt="image" src="https://github.com/user-attachments/assets/1ea86b07-8924-43fa-8efb-bbf2e24a628d" />

**K-Nearest Neighbors**
<img width="399" height="188" alt="image" src="https://github.com/user-attachments/assets/54a73d24-e4d5-47f2-85c8-ca62629b4714" />
<img width="628" height="434" alt="image" src="https://github.com/user-attachments/assets/5e279b64-2b1f-42eb-9a51-73619b2e744c" />
<img width="540" height="376" alt="image" src="https://github.com/user-attachments/assets/d9c88e15-a38f-4fa8-a6d7-ed671557fa96" />
<img width="559" height="376" alt="image" src="https://github.com/user-attachments/assets/6451d696-ae24-425e-9f0d-dc40b0f95b4e" />


**Support Vector Machines**
<img width="450" height="184" alt="image" src="https://github.com/user-attachments/assets/7eb0dafb-7f1d-4119-bc69-f2060165786a" />
<img width="569" height="385" alt="image" src="https://github.com/user-attachments/assets/d2afeb6f-79c4-4a78-b577-44112fec3a3e" />
<img width="502" height="353" alt="image" src="https://github.com/user-attachments/assets/05f31e9a-8dda-47cc-b62b-b7c8f13babdd" />
<img width="606" height="360" alt="image" src="https://github.com/user-attachments/assets/73a742bc-5a42-4d75-8121-322877ac1100" />

**Naive Bayes**
<img width="467" height="174" alt="image" src="https://github.com/user-attachments/assets/b3341895-511b-46ad-8954-8508901048d2" />
<img width="584" height="427" alt="image" src="https://github.com/user-attachments/assets/5f275006-fe25-4480-9098-c71866256f48" />
<img width="515" height="375" alt="image" src="https://github.com/user-attachments/assets/074ebfa9-9043-4fb0-acd9-e7f50c0b483c" />
<img width="565" height="372" alt="image" src="https://github.com/user-attachments/assets/b9beae0a-9cc9-455c-a143-bc204e0dfe27" />
COMPARING THE EVALUATIONS OF INTERPRETABLE MODELS TRAINED AND TESTED ON THE SAME DATA WITH A BLACK BOX MODEL.
<img width="402" height="161" alt="image" src="https://github.com/user-attachments/assets/b2f6a4bf-470a-4cea-8137-f14441657db6" />
<img width="747" height="384" alt="image" src="https://github.com/user-attachments/assets/51bb72fa-a136-4c93-b5a1-2ef1bcf8f1de" />
<img width="518" height="369" alt="image" src="https://github.com/user-attachments/assets/c33b3c30-d5a5-439c-a861-d721352eeb11" />
<img width="501" height="365" alt="image" src="https://github.com/user-attachments/assets/ebc8f74b-1d61-43c0-b2bb-949f27f5ae1d" />




