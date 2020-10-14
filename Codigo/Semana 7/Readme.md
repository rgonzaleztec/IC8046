## Clasificación

## Supervised Machine Learning
The majority of practical machine learning uses supervised learning.

Supervised learning is where you have input variables (x) and an output variable (Y) and you use an algorithm to learn the mapping function from the input to the output.
**Y=f(x)**

The goal is to approximate the mapping function so well that when you have new input data (x) that you can predict the output variables (Y) for that data.

It is called supervised learning because the process of an algorithm learning from the training dataset can be thought of as a teacher supervising the learning process. We know the correct answers, the algorithm iteratively makes predictions on the training data and is corrected by the teacher. Learning stops when the algorithm achieves an acceptable level of performance.

Supervised learning problems can be further grouped into regression and classification problems.

* **Classification**: A classification problem is when the output variable is a category, such as “red” or “blue” or “disease” and “no disease”.
* **Regression**: A regression problem is when the output variable is a real value, such as “dollars” or “weight”.
Some common types of problems built on top of classification and regression include recommendation and time series prediction respectively.

[Presentation](https://app.slidebean.com/p/l39vyo6ojy/Aprendizaje-Automatico-para-Patrones)


## Pattern Recognition using K-NN Algorithm
k-Nearest Neighbours is a non-parametric classification algorithm. It can be used both for classification and regression. It is essentially a method of classification of the most similar points in the data used for training a model. kNN works best on small data sets that do not have many features. kNN assumes that similar things exist in close proximity. kNN plots the data points on a graph and gauges the similarity between them based on their distance. The performance of kNN is influenced by:

* The distance metric used to locate the nearest neighbours.
* The distance rule used to derive classifications.
* The number of neighbours used to classify new samples (k values)

### Theory of kNN
kNN is one of the simplest of classification algorithms available for supervised learning. The idea is to search for closest match of the test data in feature space. We will look into it with below image.

![Clases](img/knn_theory.png)

In the image, there are two families, Blue Squares and Red Triangles. We call each family as Class. Their houses are shown in their town map which we call feature space. (You can consider a feature space as a space where all datas are projected. For example, consider a 2D coordinate space. Each data has two features, x and y coordinates. You can represent this data in your 2D coordinate space, right? Now imagine if there are three features, you need 3D space. Now consider N features, where you need N-dimensional space, right? This N-dimensional space is its feature space. In our image, you can consider it as a 2D case with two features).

Now a new member comes into the town and creates a new home, which is shown as green circle. He should be added to one of these Blue/Red families. We call that process, Classification. What we do? Since we are dealing with kNN, let us apply this algorithm.

One method is to check who is his nearest neighbour. From the image, it is clear it is the Red Triangle family. So he is also added into Red Triangle. This method is called simply Nearest Neighbour, because classification depends only on the nearest neighbour.

But there is a problem with that. Red Triangle may be the nearest. But what if there are lot of Blue Squares near to him? Then Blue Squares have more strength in that locality than Red Triangle. So just checking nearest one is not sufficient. Instead we check some k nearest families. Then whoever is majority in them, the new guy belongs to that family. In our image, let’s take k=3, ie 3 nearest families. He has two Red and one Blue (there are two Blues equidistant, but since k=3, we take only one of them), so again he should be added to Red family. But what if we take k=7? Then he has 5 Blue families and 2 Red families. Great!! Now he should be added to Blue family. So it all changes with value of k. More funny thing is, what if k = 4? He has 2 Red and 2 Blue neighbours. It is a tie !!! So better take k as an odd number. So this method is called k-Nearest Neighbour since classification depends on k nearest neighbours.

Again, in kNN, it is true we are considering k neighbours, but we are giving equal importance to all, right? Is it justice? For example, take the case of k=4. We told it is a tie. But see, the 2 Red families are more closer to him than the other 2 Blue families. So he is more eligible to be added to Red. So how do we mathematically explain that? We give some weights to each family depending on their distance to the new-comer. For those who are near to him get higher weights while those are far away get lower weights. Then we add total weights of each family separately. Whoever gets highest total weights, new-comer goes to that family. This is called modified kNN.

### Tutorial 

[OCR of Hand-written Data using kNN](https://github.com/abidrahmank/OpenCV2-Python-Tutorials/blob/master/source/py_tutorials/py_ml/py_knn/py_knn_opencv/py_knn_opencv.rst)

[K-NN Classifier for Image Classification](https://www.pyimagesearch.com/2016/08/08/k-nn-classifier-for-image-classification/)

Questions:
* Can you raise the accuracy from 57%? How?
* What happend if you use k=3 or 5?
* It is manhattan/City block the best distance metric formula? It is other better?
* It is posible to implement SFS


### Lecturas complementarias
[Cross-Validation in Machine Learning](https://towardsdatascience.com/cross-validation-in-machine-learning-72924a69872f)
[Cross-validation: evaluationg estimator perfomance](https://scikit-learn.org/stable/modules/cross_validation.html)

### Aditional Videos
[PATTERN RECOGNITION - KNN IMPLEMENTATION](https://youtu.be/7dfnDxvStAU)
[KNN Algorithm - How KNN Algorithm Works With Example](https://youtu.be/4HKqjENq9OU)

### Papers
[Comparing Image Classification Methods:K-Nearest-Neighbor and Support-Vector-Machines](http://www.wseas.us/e-library/conferences/2012/CambridgeUSA/MATHCC/MATHCC-18.pdf)
[USING K-NEAREST NEIGHBOR IN OPTICAL CHARACTER RECOGNITION](https://media.neliti.com/media/publications/165987-EN-using-k-nearest-neighbor-in-optical-char.pdf)




## Exercises
* Create a K NN algorithm to preform a recognition of the word HELLO but draw with your hand.














