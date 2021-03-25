# EssenceRandomForest
This repository contains the code of Essence Random Forest, a variation of Random Forest algorithm designed to handle redundancy. This algorithm is described in the article "Leveraging fine-grained mobile data for churn detection through Essence Random Forest" from Christian Colot, Philippe Baecke and Isabelle Linden


Scikit-learn version used:
Version: 0.20.2

How to implement:
1. Download Scikit-learn version 0.20.2 with source code (check https://scikit-learn.org/stable/developers/advanced_installation.html as needed)
2. Copy paste forest.py from the following github repository in the directory \scikit-learn\sklearn\ensemble
3. Copy paste all other files i.e. 8 files with .c, .pxd and .pxy extensions from the following github repository in the directory \scikit-learn\sklearn\tree
4. Compile Scikit-learn following instructions given in https://scikit-learn.org/stable/developers/advanced_installation.html

Call to the function:
rf = RandomForestClassifier(random_state=123, n_jobs = 10) # no change
rf.fit(X_train, y_train, variable_weight=vw) # vw is a vector which contains the probabilities for each feature to be selected in the same order as in the matrix train

Note:
The choice of the algorithm to define the weight is out the implementation. In the article defined above, the algorithm Varclus is used to find clusters of features and the probability of a feature for being selected = 1/(number of clusters*number of features in the cluster).

