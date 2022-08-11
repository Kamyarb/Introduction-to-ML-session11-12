# Introduction-to-ML-session11-12

## Support Vector Machine (SVM)

* Support Vector Machines is considered to be a classification approach
* SVM constructs a hyperplane in multidimensional space to separate different classes
* SVM generates optimal hyperplane in an iterative manner, which is used to minimize an error
* The core idea of SVM is to **find a maximum marginal hyperplane(MMH)** that best divides the dataset into classes

<img src="https://i.postimg.cc/59LGzBjd/svmgif.gif" />


### Hyperplanes

Hyperplanes are decision boundaries that help classify the data points.

<img src="https://i.postimg.cc/KznN15f0/hyperplanes.png"/>


💥 The objective of the support vector machine algorithm is to find a hyperplane in an N-dimensional space(N — the number of features) that distinctly classifies the data points.
<img src="https://i.postimg.cc/kXyp17xT/svm.png" width="600"/>

To separate the two classes of data points, there are many possible hyperplanes that could be chosen. Our objective is to find a plane that has the maximum margin, i.e the maximum distance between data points of both classes. Maximizing the margin distance provides some reinforcement so that future data points can be classified with more confidence.

## Terms related to SVM

### Support vectors
Support vectors are data points that are closer to the hyperplane and influence the position and orientation of the hyperplane. Using these support vectors, we maximize the margin of the classifier. Deleting the support vectors will change the position of the hyperplane. These are the points that help us build our SVM.

### Margin
A margin is a gap between the two lines on the closest class points. This is calculated as the perpendicular distance from the line to support vectors or closest points. If the margin is larger in between the classes, then it is considered a good margin, a smaller margin is a bad margin

<img src="https://i.postimg.cc/G22L2MbC/SVM-2.png" width="500" />


## Misclassification and Soft Margin

The above margin classifier could also be called **hard margin** SVM. The hyperplane in that does not allow that any data point is in the wrong side. As a result, the hard maximum margin hyperplane is **extremely sensitive to a change in a single observation** and it is highly **possible to overﬁt the training data**. To solve this problem, soft margin classifier has been introduced.  
If we allow the misclassifications (ie. We ignore the data as misclassified and do not let it affect the hyperplane) then the margin we now get is a **soft margin**.

 ### How to decide which soft margin is the best?
 There are **some tolereance for the outlier** and it could avoid the problem like overfitting.  
 **_C_** is a tunable parameter, if C is a very large value, approaching to positive infinite. There are no tolerance for any outliers or wrong classified data point in the training set. If c is approching zero, the algorithm does not care about whether to classify data set correctly and the maximum margin is the onlz objective.
 
 
 
 ## How does SVM work?

SVM searches for the maximum marginal hyperplane in the following steps:

  1. Generate hyperplanes which segregates the classes in the best way. Left-hand side figure showing three hyperplanes black, blue and orange. Here, the blue and orange have higher classification error, but the black is separating the two classes correctly.

  2. Select the right hyperplane with the maximum segregation from the either nearest data points as shown in the right-hand side figure

<img src="https://i.postimg.cc/kgvRRpP6/margins2.png" width="700"/>


## Dealing with non-linear and inseparable planes

Some problems can’t be solved using linear hyperplane, as shown in the figure below.
<img src="https://i.postimg.cc/CKvZmn1w/kernelsvm.png" width="600"/>


### Kernal Function
If dataset is linearly separable, we could use the linear hyperplane to classify it. When the dataset is complicated linearly inseparabel, keranl function would be introduced to solve the non-linear classification problem. On the one hand, kernel function could be used to map the input data to a new high-dimensional space, which is linearly separable. On the other hand, input data could be transformed to a new feature space and in the new feature space, it is easier to define a similarity function to do the pattern recognition. In this section, several commen kernel functions would be introduced.


(1) Polynomial kernel : $$K(x, x') = (x \cdot x' + 1)^p$$  
(2) Gaussian Radial Basis Function : $$K(x, x') = exp (- \frac{||x-x'||^2}{2\sigma^2})$$  
(3) Exponential Radial Basis Function : $$K(x,x') =  exp (- \frac{||x-x'||}{2\sigma^2}) $$  
(4) Multi-Layer Perceptron : $$K(x, x') = tanh(\rho(x \cdot x')+ \varrho)$$

<img src="https://i.postimg.cc/xjNk3CSS/kernels.png" width="500"/>


## Support Vector Machines (Kernels)
* `C parameter`: Controlls trade-off between classifying training points correctly and having a smooth decision boundary.
    * Small C (loose) makes cost (penalty) of misclassification low (soft margin)
    * Large C (strict) makes cost of misclassification high (hard margin), forcing the model to explain input data stricter and potentially over it.
    
    <img src="https://i.postimg.cc/CKdMMPhV/C.png" width="500"/>

* `degree parameter` : Degree of the polynomial kernel function ('poly'). Ignored by all other kernels.



<h1 align=center style="line-height:150%;font-family:vazir;color:#0099cc">
<font face="vazir" color="#0099cc">
تو اول بگو با کیان زیستی  ...  پس آنگه بگویم که تو کیستی
</font>
</h1>


## K Nearest Neighbors

K-nearest neighbors (kNN) is a supervised machine learning algorithm that can be used to solve both classification and regression tasks. I see kNN as an algorithm that comes from real life. **People tend to be effected by the people around them.** Our behaviour is guided by the friends we grew up with. Our parents also shape our personality in some ways. If you grow up with people who love sports, it is higly likely that you will end up loving sports. There are ofcourse exceptions. kNN works similarly.


**KNN is a lazy learning and non-parametric algorithm.**

It's called a lazy learning algorithm or lazy learner because it doesn't perform any training when you supply the training data. Instead, it just stores the data during the training time and doesn't perform any calculations. It doesn't build a model until a query is performed on the dataset.

### Making Predictions with KNN

Predictions are made for a new instance (x) by searching through the entire training set for **the K most similar instances** (the neighbors) and summarizing the output variable for those K instances.

To determine which of the K instances in the training dataset are most similar to a new input a distance measure is used.

<img src="https://i.postimg.cc/Pr4dWsNj/knn.png" width="700"/>
