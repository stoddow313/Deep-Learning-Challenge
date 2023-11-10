# Deep-Learning-Challenge

## Background/Analysis: 

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

### Step 1: Preprocessing data 

The beginning of this assignment, I was tasked with taking the above mentioned CSV file and cleaning it up to get the best answer possible. I started by reading in the CSV to a dataframe, and identifying our target variable and feature variables. Once that was completed, I dropped the EIN and NAME columns from the dataframe as they were unnecessary to our project. I checked the unique values for each column, and then picked a cutoff point to bin our categorical variables together. Finally, we encoded the categorical variables using get_dummies(), split the data into our features and target arrays, and scaled them using StandardScaler().

### Step 2: Compile, Train, and Evaluate the Model

During this step, I created a neural network model using nodes of 80 and 30 for our two initial layers, and then just a base unit of 1 for our third layer. Our input features were derived by calculating the length of our X variables utilizing len() and specifying [0]. After creating our model structure, we summarized it to see how it looked, and then compiled the model. I then trained the model using 100 epochs and saving the model's weights every five epochs with a callback function that saved each checkpoint under our checkpoint folder. Finally, I evaluated the model using the test data to determine our loss and accuracy of this model and saved our results to an HDF5 file. 

### Step 3: Optimizing the model

In this step, I essentially just copied the above procedure to preprocess our data, except I removed additional columns to help our accuracy and loss try to reach our target results. I removed the STATUS and SPECIAL_CONSIDERATIONS columns alongside the NAME and EIN columns. In addition to that change I ran 3 different models each using different amounts of nodes to try to adjust our accuracy and loss to reach target accuracy. I also saved this file to an HDF5 which can be found under H5 files. 

### Report on Neural Network Model: 

Overview of Analysis: The purpose of this analysis was to attempt to create a neural network model that would result in a target predicted accuracy of 75% or higher in regards to AlphabetSoups business dealings. 

Results: 
- Data Preprocessing: 
    1. What variable(s) are the target(s) for your model? 
        - The target variable is the 'IS_SUCCESSFUL' column from application_df.
    2. What variable(s) are the features for your model? 
        - The feature variables are every other column from application_df --> this was defined by dropping the 'IS_SUCCESSFUL' column from the original dataframe.
    3. What variable(s) should be removed from the input data because they are neither targets nor features? 
        - Both 'EIN' and 'NAME' columns were dropped/removed, because they were neither targets nor features for the dataset.
- Compiling, Training, and Evaluating the Model:
    1. How many neurons, layers, and activation functions did you select for your neural network model, and why? 
        - In the first attempt, I used 80 hidden_nodes_layer1, and 30 hidden_nodes_layer2. These were based on what was provided in the original starter code given to me. 
    2. Were you able to achieve the target model performance? 
        - None of the attempts made were able to achieve the 75% model accuracy target. 3 attempts were made with a high of 73% accuracy. 
    3. What steps did you take in your attempts to increase model performance? 
        - I removed more columns, change the number of hidden nodes, and switched activation functions associated with each layer in an attempt to achieve higher accuracy. 
    
Summary: Overall, the deep learning model used was between 72-73% accurate in predicting the classification problem. A solution to potentially achieve the target 75% accuracy would be to utilize a model with greater correlation between our input and output. This could be achieved by doing additional data cleanup up front, as well as by utilizing a model with different activation functions and iterating until the target is reached. 