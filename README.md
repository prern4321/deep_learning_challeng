# deep_learning_challenge

Unit 21 Homework: Charity Funding Predictor
Report:
Overview:
Neural network and deep learning were used to determine if an applicant would be succesfully funded by Alphabet Soup, who has funded 34,000+ organizations in the past.

Preprocessing:
Irrelevant information was removed from the data set: columns 'EIN'  were dropped from the model and everything that remained was considered a feature for the model. 'APPLICATION_TYPE' and 'CLASSIFICATION' were replaced with 'Other' due to high variance. The data was then split into training and testing sets. The target variable in the model is 'IS_SUCCESSFUL_1' and is confirmed by its value; 1 being a yes and 0 being a no. 'APPLICATION' data was analyzed, and the value of 'CLASSIFICATION' was used for binning. Each unique value used several data points as a cutoff point to bin scarce categorical values together in a new variable: 'Other'. Categorical variables were encoded with 'pd.get_dummies()'.


•	The feature variables in the final model were:
o	NAME
o	APPLICATION_TYPE
o	AFFILIATION
o	CLASSIFICATION
o	USE_CASE
o	ORGANIZATION
o	INCOME_AMT
o	ASK_AMT
•	The variables that were removed from the final model were:
o	EIN - just an id number
o	SPECIAL_CONSIDERATIONS - this column had over 34,000 'N' values and only 27 'Y' values. Not helpful.
o	STATUS - this column had over 34k 1's and only 5 0's - only five of the rows are zeroes which is not helpful.

Compiling, Training, and Evaluating the Model
•	The final model had three layers. The first layer had 100 neurons or nodes, the second layer had 30 neurons, and the third layer had 10 neurons. 
	The model used two different activation functions - rectified linear units (relu) and sigmoid. 
•	The model exceeded the target performance of 75%. The model reached 99% accuracy.
•	I took the following steps to increase the model's performance:
o	Including the NAME column. There were a significant number of organization names that were repeated in the data. 
	I thought there could be a connection betwen the organization and its success.
o	Two columns, SPECIAL_CONSIDERATIONS and STATUS were removed because they were both almost all one value.
o	I added a third layer to increase the model's complexity.
o	I changed the activation functions on the second and third layers as well as the output layer.
Overall
The tuned neural network was able to predict outcomes with 79% accuracy. This is a marked increase when compared to the original neural network which predicted outcomes with 73% accuracy. 
This was achieved by adding the organization NAME to the feature variables, removing SPECIAL_CONSIDERATIONS and STATUS from the feature variables, increasing the model's complexity
 by adding a third hidden layer, and changing some of the layers' activation functions.
As an alternative to the nn model, a random forest classifier could be used. I attempted this and was able to get 78% accuracy. 
This is a much better score than the 75% threshold I was shooting for. However, the neural network won out with 79% accuracy. 
With further tuning, it may be possible to improve on one or both of these models and get an even better predictive classifier.
