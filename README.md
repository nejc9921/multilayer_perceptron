# Multilayer perceptron
This is a multilayer perceptron done using 7 layers and predicting outcome. It is trained on exchange rate data from kaggle (https://www.kaggle.com/cfchan/hourly-gbpusd-w-technical-indicators-20002019#Column_Description_USDGBP.csv).
The data is consisting of technical indicators and time series. Some other methods here would be very interesting to use as well (and might perform better), but in this specific case we decide to train multilayer perceptron. The code is easily reproducible for other purposes as well.
The prediction is then compared with random forest and linear model. Everything is trained based on technical indicators from previous days.
The layers have the following dimensions:
40,25,15,8,4,1

The code is made of several parts. Firstly, we deal with data, analyze it and inspect outliers and other potential problems that occur in the data.
After that we create a model and we train it. Finally, there is usually another code for retraining the model. In this way we can improve those models when we need to. In the end the results are also compared with clasical random forest model. As we can see with many epoch, we manage to outperform the basic random forest model. The latter could probably be improved and would likely perform better if the parameters would be set up just perfectly. Still we manage to make a prediction using multilayer perceptron.


Several thousand epochs were done. The prediction was converging and it would be interesting to wait for longer. I compared the prediction to simple random forest with 250 trees. So, not completely optimized, but just enough to get a general feeling of the fit. I find that multilayer perceptron performed better.

Multilayer perceptron R-square used in lasagne package: 99.9989%
Multilayer perceptron R-square used in keras package:99.995988%
Random forest R-square: 99.9950%

The predictions are close to 1 because of the nature of the data. We have interest rates, which can generally be prediction based on data from previous days. Still, we can see our model beats random forest and this is despite the fact that it was still converging - meaning that it would likely improve prediction if we are to train it for longer.
