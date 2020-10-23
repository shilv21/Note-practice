# 1. Terminology
## Why use ML:
- Problems for which existing solutions require a lot of fine-tuning or long lists of rules: one Machine Learning algorithm can often simplify code and perform better than the traditional approach.

- Complex problems for which using a traditional approach yields no good solution: the best Machine Learning techniques can perhaps find a solution.

- Fluctuating environments: a Machine Learning system can adapt to new data.

- Getting insights about complex problems and large amounts of data.

## Classify ML
There are so many different types of Machine Learning systems that it is useful to classify them in broad categories, based on the following criteria:

- Whether or not they are trained with human supervision (supervised, unsupervised, semisupervised, and Reinforcement Learning)

- Whether or not they can learn incrementally on the fly (online versus batch learning)

- Whether they work by simply comparing new data points to known data points, or instead by detecting patterns in the training data and building a predictive model, much like scientists do (instance-based versus model-based learning)

## Test set and Validation set
- A test set is used to estimate the generalization error that a model will make on new instances, before the model is launched in production.

- A validation set is used to compare models. It makes it possible to select the best model and tune the hyperparameters.

- The train-dev set is used when there is a risk of mismatch between the training data and the data used in the validation and test datasets (which should always be as close as possible to the data used once the model is in production)

- If you tune hyperparameters using the test set, you risk overfitting the test set, and the generalization error you measure will be optimistic (you may launch a model that performs worse than you expect).

# 2.ML process
- If the data were huge, you could either split your batch learning work across multiple servers (using the MapReduce technique) or use an online learning technique.
- Quick way to get a feel of the type of data you are dealing with is to plot a histogram for each numerical attribute. The hist() method relies on Matplotlib, which in turn relies on a user-specified graphical backend to draw on your screen. So before you can plot anything, you need to specify which backend Matplotlib should use. The simplest option is to use Jupyter’s magic command %matplotlib inline
- When you estimate the generalization error using the test set, your estimate will be too optimistic, and you will launch a system that will not perform as well as expected. This is called data snooping bias.
- Avoid sampling bias:
  - **Stratified sampling**: the population is divided into homogeneous subgroups called strata, and the right number of instances are sampled from each stratum to guarantee that the test set is representative of the overall population. != Random sampling
- The correlation coefficient only measures linear correlations (“if x goes up, then y generally goes up/down”). It may completely miss out on nonlinear relationships.
- Scale fit to training data only. Then using them to transform the whole dataset(including training set and test set or new data).
- Building a model on top of many other models is called Ensemble Learning, and it is often a great way to push ML algorithms even further.
- Another way to fine-tune your system is to try to combine the models that perform best.

# 3.Classification
- Skewed datasets: when some classes are much more frequent than others.
- Confusion matrix: The general idea is to count the number of times instances of class A are classified as class B.
