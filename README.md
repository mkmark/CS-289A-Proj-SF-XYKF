# CS-289A-Proj-SF-XYKF
UCB CS 289A Project S Final XYKF

## Group Member Info
| Name           | Email Address            |
|----------------|--------------------------|
| Ke Ma          | kema@berkeley.edu        |
| Fengzhe Shi    | schweini@berkeley.edu    |
| Xin Chen       | chenxin0210@berkeley.edu |
| Yun Yeong Choi | yychoi94@berkeley.edu                         |
## Overview
With the purpose of developing a prediction model of stellar bodies, we performed a learning process with several models. Using the most basic linear regression model, ridge regression, LASSO, etc. we try to make prediction on the positions of the moon, the sun and the planets. We also try to predict the moon phases. In our notebook, we demonstrate how to improve the results by feature engineering. We select the important Fourier features by ordering them to minimize the mean square error of the training set. By using this method, we were able to predict Sun’s daily, hourly altitude successfully (0.005, 8.692 MSE)with only 20 features. 

## Usage Examples

### Moon.ipynb
Moon.ipynb shows you how to train a model to predict the positions of the moon and moon phases. The machine learning models we use includes linear regression, ridge regression, LASSO and neural network.

### Mars_Sun.ipynb
Mars_Sun.ipynb include the code about part 4.1 of final reports. It's dealing with training and predicting Sun and Mars position based on the Linear Regression, Ridge Regression, LASSO.

### Tuned_Fourier.ipynb
Tuned_Fourier.ipynb is the code about capturing best fourier features to predict stellar body position. Explanation is on the part 4.2 of final report

### Stellarium_API.ipynb
Work of Project S Early Team with part of the data extraction process, forked from [ioannis-vm/CS289_2020_ProjectS_TeamJupyter](https://github.com/ioannis-vm/CS289_2020_ProjectS_TeamJupyter)

### Data_Extraction-Easier_Method.ipynb
New data extraction methodother than Stellarium_API.ipynb, using 'solarsystem'
