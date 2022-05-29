# MVP for AMS
## Minimal Viable Product for Automobile Mangement System

### Project Overview 

This project consists of different tracks based on the two different datasets that were combined together in relation with the price of the automobiles. The datasets were taken from kaggle.   
It's a web application based on react framework, and I used material ui template to build upon it. It has the following technologies/features:  
1) material ui to improve user experience
2) ChartJS for plotting different fields from the chosen dataset
3) danfoJS for fetching data, manipulating it according to our needs and performing operations such as mean, sum, series and count.
4) scikitjs for creating Decision Tree Regressor model and predicting price based on important automobile features.
5) tensorflow for setting backend of the model
6) PlotlyJS for facet grid chart to display the prediction of price based on features.
7) random colour generator for charts based on an object of colours chosen.

### Project Walkthrough
<img width="1120" alt="Screenshot 2022-05-29 193129" src="https://user-images.githubusercontent.com/73405757/170873094-b4eb7290-cf46-435b-baba-1aa2877f50f8.png">

[Project Walkthrough Video Link](https://www.youtube.com/watch?v=ZAqnOrP8fN0)

### Project Deployed Link

Click on this [link](http://mvp-for-ams.s3-website-us-east-1.amazonaws.com/) to view the project.

### Sections/ Tracks
The tracks are as follows:

#### 1) Analysis

This part consists of analysis of different automobile features by price, total sales per country or make, total number of diesel or gas cars sold by country or make, etc.

#### 2) Loan Default

This section consists of analysis based on client's income, credit amount, loan, country, gender, total loan generated by the system per country or make, etc.

#### 3) Stress Management

This section is under development. It has been studied that stress is the major cause for road accidents. It will help the system to analyze the stress level of it's clients and study it to improve performance as well as save lives.  
The dataset is present on kaggle: [Stress Recognition in Automobile Drivers](https://www.kaggle.com/datasets/bjoernjostein/stress-recognition-in-automobile-drivers)

#### 4) Forecasting

This track consists of a facet grid chart with all the subplots displaying prediction of price based on important automobile features.

#### 5) Play Around

This section is kind-of a playground for users or admins. It helps you to choose the type of chart, the fields you want to analyze and operations that you want to perform on the chosen fields.


### Important Features/Functions

#### 1) fetchData 
##### route: src/charts/getData

This function is used to fetch data from the file "Automobile_data.csv", and group it according to x and y columns passed as parameters, as well as operation mentioned.  

For series: data is grouped together according to y column
For count: data is grouped together and count operation is performed
For mean and sum: data is aggregated according to the respective operations  

Then, the resultant dataframe is manipulated according to the data structure or values needed by ChartJS to plot.

#### 2) ColorPallete
##### route: src/charts/ColorPallete

It consists of an object of colours chosen by me, which is used in fetchData function to generate random color picker for charts.

#### 3) Units
##### route: src/charts/Labels

It has an object of Units for the fields present in the csv file. It is used in fetchData function as well as forecasting section, to add units to labels.

#### 4) PlotChart
##### route: src/charts/visualizeData

This function is used to get the parameters chosen, such as title, indexAxis, ChartType, etc, and plot the chart using it.

#### 5) Analysis
##### route: src/layouts/Analysis

In this section, I am just calling the VisualizePlots function from fetchData and passing the values such as columnX, columnY, title, operation, etc to analyse the features.

#### 6) Loan Default
##### route: src/layouts/LoanDefault

This section is same as the Analysis section, only difference is the change in parameters. Here, fields related to loan and client is anaylzed.

#### 7) Stress Management
##### route: src/layouts/StressManagement

This section is under development, so it shows a notification for users to wait for some exciting stuff.

#### 8) Forecasting
##### route: src/layouts/forecasting

In this track we fetch the data from the csv file again, and drop the rows with any null values. Then important automobile features are chosen wisely, and model is built to predict the price of the automobile using scikitjs.  
Then dataset is manipulated and charts features are mentioned, to plot a facet chart using PlotlyJS.

#### 8) PlayAround
##### route: src/layouts/PlayAround

In this section, we let the user or admin decide what fields they want to analyse. For the options, columns are extracted from the file and passed. For Yaxis column, we check if it's an integer type column, and then the value is passed.  
Accordingly, VisualizePlots function is used and default parameters are passed so that the card is not empty.
