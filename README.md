# Cryptocurrencies

## Purpose

Martha, a senior manager for the Advisory Services Team at Accountability Accounting, is offering a new cryptocurrency investment portfolio for its customers. However, she's lost in the huge cryptocurrnecy universe that now exists and is requesting a report on all the cryptocurrencies in the trading market and they can be grouped to create a classification system for this new investment.

Since the data that's provided on the cryptocurrencies is not ideal, and has no known output, unsupervised machine learning will be used to help group all the cryptocurrencies and provide data visualizations of our analysis.

## Analysis

- In order to perform an analysis, first the dataset will need to be preprocessed by using Pandas DataFram to ensure that it has no unncessary data or null values.
- After the DataFrame has been preprocessed, the StandardScaler from the sklearn library was used to standardize all the data. 
- Then, the PCA algorithm from sklearn was used to reduce the dimensions of our standardized DataFrame down to 3 principal components in another DataFrame.
- The PCA data from the DataFrame can then be used to perform the KMeans algorithm from sklearn to cluster the cryptocurrencies. 
- Then, the K-means algorithm from sklearn was used to cluster the cryptocurrencies.
- First, the PCA DataFrame was used to create an elbow curve by using the hvPlot function to determine the best value for K. The image below illustrates this elbow curve.

![elbow_curve](https://user-images.githubusercontent.com/75760493/117601431-fa7e2c80-b113-11eb-9cc2-6dd02a509f9d.png)

- After K was found, the K-means algorithm was used to make predictions of the K clusters for the cryptocrrencies' data.
- Then a Clustered DataFrame was created by combining both the PCA DataFrame along with our inital DataFrame that was created when all the unncessary data was removed.
- A 3D scatter plot can be created by using Plotly Express scatter_3d() function to plot the 3 clusters from the Clustered DataFrame. The image below illustrates this 3D scatter plot.

- 3D Plot:

![3D_plot](https://user-images.githubusercontent.com/75760493/117601925-0fa78b00-b115-11eb-9753-c9fdfcd6df91.png)

- Finally, a final table was created for all the tradable cryptocurriencies by using the hvplot.table() function.
- Once the table to created, the MinMaxScaler().fit_transform method was used to scale the data for the TotalCoinSupply and TotalCoinsMined columns. 
- A final DataFrame was created by using the Clustered DataFrame index along with previously scaled data.
- A scatter plot can be created by using hvplot along with x="TotalCoinsMined" and y="TotalCoinSupply". The image below illustrates this scatter plot.


- Scatter Plot:
![scatter_plot](https://user-images.githubusercontent.com/75760493/117601961-24841e80-b115-11eb-8428-6233c1f4c839.png)
