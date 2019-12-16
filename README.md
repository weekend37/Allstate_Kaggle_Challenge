# Allstate Claims Severity Kaggle Challenge (spring 2018)

### The Problem

Allstate, an US-based insurance company, has for the past couple of years been developing automated
methods of predicting the cost, and hence severity, of claims. In December 2016 it put forward
a recruitment challenge on Kaggle to allow people to show off their creativity and present their
technical skills by creating an algorithm which accurately predicts claims severity. With this the
company hoped to get insight into better ways to predict claims severity and thereby ensure a
more worry-free customer experience. This project takes on the 2016 Allstate challenge and
use the provided datasets on Kaggle. The objective was to compare performance of different machine learning algorithms and methods on the insurance claim dataset from Allstate and to get the best model to predict the accident loss.

### Outline

First the data is observed, transformed and encoded.
Then different prediction methods are used and compared. The methods that are used are 
- Linear Regression
    - Vanilla LR
    - Regularization
        - Ridge
        - Lasso
- Support Vector Machines
- Random Forest
    - Little digression into feature exploration
- Neural Network 


Finally the model that seems to give the best results is trained on the full training set and predictions are made to the submission test provided by Kaggle. 


### Results

The model that had best results was (with no surprise) the neural network. The NN-model really stood out on the leaderboard with around 10% better performance the the second model (RF).

| Model             | training MAE | test MAE |
|-------------------|--------------|----------|
| Linear Regression | 1299.18      | 1312.04  |
| Ridge Regression  | 1286.57      | 1302.32  |
| Lasso Regression  | 1286.35      | 1302.35  |
| SVM               | 1296.36      | 1308.77  |
| Random Forest     | 466.58       | 1251.67  |
| Neural Network    | 1074.78      | 1179.82  |

The submissions were divided into public (multi-submission) and private submission with the prediction MAE being the benchmark. The NN-model ended up scoring a private MAE of 1147.20 and a public MAE of 1138.11. Compared to the leading submission on Kaggle (private MAE of 1109.71), this is an acceptable result.

### Conclusion

What became extremely clear very soon in this project was how much impact the preprocessing of
the data had on the final results for most of the models. It came clear how critical data processing
is in all real life machine learning problems. Future steps would involve transformations and rescaling of the parameters. They worked well as they were but they could probably be massaged to enhance model performance. For the prediction models, the future steps would probably include a bigger process for hyperparameter optimization and a better way for validating (e.g. CV). Regarding the NN model, some methods for reducing the overfitting should definitely be applied (e.g. dropout or some regularization).
