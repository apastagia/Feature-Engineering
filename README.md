1. One Hot Encoding with many variables:
One Hot Encoding of top variables
Advantages:
    1. Straightforward to implement
    2. Does not required hrs of variable exploration
    3. Does not expand massively the feature space(number of columns in the dataset)
    
Disadvantages:
    1. Does not add any information that may make the variable more predictive
    2. Does not keep the information of the ignored labels
    
Because it is not unusual that categorical variables have a few dominating categories and the remaining labels add mostly noise, this is a quite simple and starightforward approach that may be useful on many occasions.

*******************************************************************************************************************************************
2.Feature Scaling

Feature scaling can vary your results a lot while using certain algorithms and have a minimal or no effect in others. To understand this, let’s look why features need to be scaled, varieties of scaling methods and when we should scale our features.

What is Feature Scaling?
It refers to putting the values in the same range or same scale so that no variable is dominated by the other.

Why Scaling
Most of the times, your dataset will contain features highly varying in magnitudes, units and range. But since, most of the machine learning algorithms use Euclidean distance between two data points in their computations, this is a problem.

Example:
    If left alone, these algorithms only take in the magnitude of features neglecting the units. The results would vary greatly between different units, 5kg and 5000gms. The features with high magnitudes will weigh in a lot more in the distance calculations than features with low magnitudes. To suppress this effect, we need to bring all features to the same level of magnitudes. This can be achieved by scaling.
    
Which machine learning algorithms required feature scaling?

    a. k-nearest neighbors:
        k-nearest neighbors with an Euclidean distance measure is sensitive to magnitudes and hence should be scaled for all features to weigh in equally.
        
    b. Principal Component Analysis(PCA):
        Scaling is critical, while performing Principal Component Analysis(PCA). PCA tries to get the features with maximum variance and the variance is high for high magnitude features. This skews the PCA towards high magnitude features.
    
    c. gradient descent:(Including Linear Regression)
        We can speed up gradient descent by scaling. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.
        
    d. KMeans
    
Which machine learning algorithms don't required feature scaling?
Tree based models are not distance based models and can handle varying ranges of features. Hence, Scaling is not required while modelling trees.
    -> Decision Tree
    -> Xgboost
    -> RandomForest
**************************************************************************************************************************************    
3. Techniques Handling Missing values in Categorical features(variables)
    -> Delete rows
    -> Replace with most frequent values
    -> Apply classifier algorithm to predict
    -> Apply unsupervised ML algorithm