# POI-Enhancement

This repo contains materials to enhance the Point of Interest (POI) data for trip purpose inference using machine learning techniques. 

Two common issues of POI data which affects in trip purpose inference negatively are addressed. 

### 1. Improving the POI purpose categorization with text classification. 

<b> Problem: </b> 

POI data that can be extracted from different APIs mostly lack the category type for some which make the inference results useless.  

<b> Proposed Solution: </b> 

Intuitively, this issue can be solved using text classification as a model can be built to predict the category type based on the name of that POI. Simply put, when a POI has a name as “National Primary School”, there is a possibility that its purpose can be predicted as “educational”. 

[K-Nearest Neighbors (KNN), Logistics Regression (LR), Random Forest (RF), Multinomial Naive Bayes (MNB), and Support Vector Machine (SVM)](https://github.com/dineth33/POI-Enhancement/blob/main/POI_category_prediction/ML_Models.ipynb) as conventional machine learning classifiers  and  [Convolutional Neural Network (CNN)](https://github.com/dineth33/POI-Enhancement/blob/main/POI_category_prediction/CNNs.ipynb)
, [Long Short-Term Memory (LSTM)](https://github.com/dineth33/POI-Enhancement/blob/main/POI_category_prediction/LSTM.ipynb), [Temporal Convolutional Network (TCN)](https://github.com/dineth33/POI-Enhancement/blob/main/POI_category_prediction/TCN.ipynb) as deep learning classifiers were evaluated to predict the purpose of a POI based on the name. 

Following table indicate the achieved F1-scores from each classifier. 


![Classification results](https://user-images.githubusercontent.com/89911053/166672454-05170a31-4da6-4ec2-bca1-57d515368255.JPG)



It was decided to continue with SVM as it provides a considerably higher accuracy with a lower computational time.


### 2. Identifying the possible entering locations for POIs with large land areas. 

<b> Problem: </b> 

There are POIs that are highly attractive but located far from the roads due to the large land areas of those such as schools, conference halls, and hospitals. This becomes an issue in purpose inference as the given location does not fall within the provided Walking Radius (R) around the DOP of a trip. 




<b> Proposed Solution: </b> 

Identifying the entrance locations of these POIs helps to reduce this issue. The proposed method is two fold as: (1) Prerequisite: Identifying the POIs which requires entrance locations, (2) Identfiying the entrance locations. [Click Here](https://github.com/dineth33/POI-Enhancement/blob/main/Entrance_location_identification/issue%20solving.ipynb)








### Asssessing the impact of Enhanced POIs for trip purpose inference 

The trip purpose inference model developed by  [Gong et al.2016](https://www.tandfonline.com/doi/abs/10.1080/15230406.2015.1014424)  and developed by [Dhananjaya et al. 2021](https://ieeexplore.ieee.org/abstract/document/9655943)  based on the Bayesian modeling is used in this study to access the impact of the suggested improvements. [Click Here](https://github.com/dineth33/POI-Enhancement/blob/main/Purpose_Inference/Purpose_Inference_Testing.ipynb)

### Data Usage
<hr> 

1. [Point of Intereset (POI) data](https://github.com/dineth33/POI-Enhancement/blob/main/Entrance_location_identification/Original_POI_data.csv) </br> 

2. Taxi trips GPS data (Timestamped Origin and Destination cordinates)  </br> 

3. [Road Network data](https://github.com/dineth33/POI-Enhancement/tree/main/Entrance_location_identification/road%20network) </br> 

4. [Land Area Shape file (for the selected study area)](https://github.com/dineth33/POI-Enhancement/tree/main/Entrance_location_identification/land%20area) </br> 


### Acknowledgement 
<hr> 
This research was supported by the Accelerating Higher Education Expansion and Development (AHEAD) Operation of the Ministry of Higher
Education funded by the World Bank
