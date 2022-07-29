# Airline Flight Delay Prediction
## Determine how individual flight features affects the likelihood of a delay
**Saurabh Vaze**: 

### Business problem:
Can we predict whether a flight is likely to get delayed based on a number of independent flight features

### Data: source: https://www.kaggle.com/datasets/jimschacko/airlines-dataset-to-predict-a-delay
This dataset originally included 11024 entries with 7 columns explaining flight traits. 

#### Target:
***Delay***

#### Features

Airline

AirportFrom

AirportTo

DayOfWeek

Time 

Length             



## Methods
All features related to index and ID were excluded

The numerical columns were scaled, and categorical columns were one-hot-encoded to process the data for modeling.

I tried a KNN, decision tree and then a bagged tree model to determine which model best accounted for variablity across features.


## Results

#### Length of Delayed/On-Time Flights by Day of Week

![image](https://user-images.githubusercontent.com/43122737/181666816-42fdc332-d90b-46d4-a086-1bb15ba224ad.png)

> This barplot shows the average flight lengths by Day of the Week, across all departures and arrival airports. We can see that within this dataset,  Saturday seems to have the longest flights followed closely by Sunday and Wednesday. Similarly, the greatest uncertainty in flight length mean is also found on weekends.We can see that the range of the mean lengths is quite homogeneous, with each day's aaverage flight length ~150, with a peak around 160.

#### Univariate Distribution of Flight Lengths

![image](https://user-images.githubusercontent.com/43122737/181667105-654e5a84-db38-4f1c-9829-a44745a7ed6f.png)

> We can see that the mean flight length is around 140, with no apparent outliers in this boxplot 

## Model

The KNN model proved most effective in accounting for variation, with an R^2 score on the test data of  ***(0.46)***, far higher than that of my bagged tree and decision tree models. The addition of PCA in the piopeline did not improve testing accuracy, and the speed of the process was not improved, either. It is evident that these values are relatively low, but this is likely a limitation from the data, rather than the model chosen. 


## Recommendations:

This model will be improved with a more robust and diverse data set, with a greater count of features, and more unique vaues in the features that we have currently. With more features, the PCA will be more effective as well. With the current condition of the othis data and model, it is hard to be confident that a given profile of a flight can be reliably predicted as delayed or not.

## Limitations & Next Steps

This dataset would be improved with a larger number of quantitative numerical features, focusing more on flight attributes, which will give us the best idea of how flight status may react. Multiple airport columns can likely be replaced with a single departure-arrival feature, and more information about the conditions surrounding a flight, and more values for airlines, airports, etc, will make the predictions more relevant to real-world flights.

Next steps will be contingent on more diverse data with a larger feature count, that will more directly relate to the target information we are looking for, and a test of a wider range of models to best assess which strategy will give us the most accurate outputs.

### For further information


For any additional questions, please contact **svaze7@gmail.com**
