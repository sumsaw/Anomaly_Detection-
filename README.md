# Anomaly_Detection
To detect the fraud credit card  transaction using unsupervised learning <br>
Kaggle Notebook: <br>
Medium Post : https://sumsaw7.medium.com/credit-card-fraud-detection-using-un-supervised-learning-8f3cfd6be765<br>

### Motivation 

In this notebook I am going th explore some of the various machine learning models used for Anomaly detection. <br>

Anomaly detection is very important as it can be applied to detect fraud in a bank transcation , catching defects in a manufacturing product or even detect outliers in a dataset. <br> It can also be used for data labeling 

The challenging part in anomaly detection is that its dataset is higly unbalanced that is the anaomaly occurs around 1% of the total instances in the dataset. <br>

### Approach 

There could be three aproached for the given problem . 
* Treating as supervised learning problem : Fitting various models on the dataset to classify<br> 
* Treating as semi-supervised learning : Where you just map the correct data and any data points outside this domain are anomaly<br>
* Treating is a unsupervised learning : Where you try to isolate the fraud points from proper transaction without using labels <br>

Even though this dataset has labels but I am going to apply various anaomaly detection algorithms in this notebook and then via the help of the labels check out if I got all the anomalies correctly classified. 

### Dataset 

The datasets contains transactions made by credit cards in September 2013 by european cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.<br>


### Models Explored

I am going to detect the fraud points in the dataset using two unsupervised learning algorithms described below:<br>
**1.Isolation Forest :** This method in found in the sklearn.ensemble class of sci-kit learn. This algorithm builds a random forest in which each decision tree is grown randomly . At each node ,it picks a feature randomly ,then picks a random threshold value (between min and max value) to split the dataset in two . The dataset is gradually gets chopped into pieces . By definition anomaly should be a point which is far away from normal points in the dataset and thus in this algorithm the anomaly should get separated closer to the root of the tree. The percentage of anomaly points should be specified before running isolation forest in contamination variable .

**2.Gaussian Mixture :** This method is found in sklearn.mixture class of sci-kit learn. A Gaussian mixture model is a probabilistic model that assumes all the data points are generated from a mixture of a finite number of Gaussian distributions with unknown parameters. One can think of mixture models as generalizing k-means clustering to incorporate information about the covariance structure of the data as well as the centers of the latent Gaussians. Given the number of cluster ,the model basically solves for means and co-variance matrices of those clusters assuming they are normally distributed.

# Key Insights gained 
- Was able to gain knowlege on Isolation forest ,Gaussian Mixture and was also able to quantify it <br>

# Final Submission 
- I recommend Isolation forest model out the two method tried for better score and ease of training <br>

# Additional Improvements 
- We can try one class SVM and DBSCAM method to explore more 

