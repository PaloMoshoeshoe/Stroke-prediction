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


These Black-box models are evaluated on the classifictation metrics shown above. The ROC_AUC score (Receiver Operating Characters Area Under the Curve) is a metric used to evaluate the performance of a binary classification model by showing the model's ability to differentiate between two classes across all possible classification thresholds. The ROC_AUC score of 1 means the classifier is perfect and 0.5 means a random classifier. Values between 0.5 and 1.0: Represent the model's ability to distinguish between the classes, with higher values indicating better performance. In this case, the Neural Ntwork has a higher ROC_AUC value of
(0.59) compared to XGBost with ROC_AUC value of (0.56) and Random Forest ROC_AUC value of (0.55).

The accuracy score is an evaluation metric is a percentage measure that tells how often a model can correctly predict an outcome. In this case, the  XGBost has the highest accuracy value of (0..90) the followed by the Random Forest with the accuracy value of (0.89) and lastly the Neural Ntwork has the lowest accuracy value of (0.80).
  
