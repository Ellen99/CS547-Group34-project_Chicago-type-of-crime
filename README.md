## Deep Dive Project 34 – [Chicago Type of Crime](https://docs.google.com/document/d/1nDuKAzUkSMS_-DFrDwjFRx65vKHqBpAGoj6I-Ek66Nk/edit)
## Team Members

- Mohammed Shoaib Abbas
- Adam Schmitt 
- Elen Chatikyan
- Vir Sikand


## Problem explanation

Crime is a significant challenge faced by urban areas, including Chicago, where various neighborhoods experience different types and frequencies of criminal activity.

The objective of the project is to predict future crime(patterns and trends) in Chicago using available data. 

### Project overview
Develop a predictive model to prevent crime occurrences in Chicago and raise public awareness about potential dangers.


## License
This project is licensed under the MIT License. See the [LICENSE](https://drive.google.com/file/d/1mN4fLygBz0r9Hll8FRFJDZD_TwZdXi8B/view?usp=share_link) file for more details.


## Dataset references

- [Chicago crimes 2001-present](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)


- [kaggle US Holiday data](https://www.kaggle.com/datasets/jeremygerdes/us-federal-pay-and-leave-holidays-2004-to-2100-csv?resource=download)

- [Weather dataset NCEI](https://www.ncdc.noaa.gov/cdo-web/datasets)

- [Per Capita Income](https://data.cityofchicago.org/Health-Human-Services/Per-Capita-Income/r6ad-wvtk)

- [Chicago Parks Data](https://data.cityofchicago.org/Parks-Recreation/Parks-Chicago-Park-District-Park-Boundaries-curren/ej32-qgdr)



## Relevant Scripts

- [Milestone1_DataExtraction.ipynb](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/notebooks/Milestone1_DataExtraction.ipynb)


  Loads in the Crime, Holiday, Weather, and Per Capita Income datasets. Adjusts date and time formats for easier handling and partitions the nearly 500,000 data points into three datasets: training (60%), testing (20%), and validation (20%). A debugging dataset of 1000 points is randomly extracted and the dataset is pickled to save time while loading and scripting later on. 

- [Milestone2_DataExploration.ipynb](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/notebooks/Milestone2_DataExploration.ipynb)

  Drops repetitive data and columns full of NaNs. Plots bar charts for each feature to show their distributions. This allows for an initial visual analysis of any trends between features. Then, a distribution of the crime types is plotted,  showing that certain crime types are heavily over-represented in our data, while others are under-represented. We will see how this affects deep learning later on. 

- [Milestone2_BaselineLearning.ipynb](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/notebooks/Milestone2_BaselineLearning.ipynb)

  Utilizes scikit-learn's logistic regression model to predict the type of crime committed based on 14 features. Yielded a 30% accuracy. Results are shown in a confusion matrix to easily portray which crime types were most accurately predicted and which were misclassified. 

- [Milestone3_DeepLearning.ipynb](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/notebooks/Milestone3_DeepLearning.ipynb)

  Runs a random forest classifier model to determine feature importance. Using this information, the training and testing data is reorganized based on the importance of the features. Then, a Long-Short Term Memory recurrent neural network is set up and trained using the training data to predict crime types. The test accuracy using LSTM was only 25%. Many hyperparameters were tuned, including batch size, number of epochs, and optimizer choice, eventually achieving a quick convergence without sacrificing training effectiveness and without overfitting.

- [Milestone4_FeatureImportance.ipynb](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/notebooks/Milestone4_FeatureImportance.ipynb)

  Outputs a normalized feature importance chart using a logistic regression model. Also outputs another chart showing mean permutation importance. Certain locations and latitude/longitude proved to be more important features, while features such as snow, precipitation, and day of week were of very low importance. This is further exemplified by showing feature importance based on the Shapley Values of each feature. 

## Final Presentation
We have created a video presentation summarizing our project goals, methodology, results, and key insights. You can find the video in the repository under [media/](https://github.com/Ellen99/CS547-Group34-project_Chicago-type-of-crime/blob/main/media/Group34_recording-Milestone5.mp4) or access it with this (Youtube link)[https://youtu.be/u-7zkXJJF40].
