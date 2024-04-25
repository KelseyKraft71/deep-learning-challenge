# deep-learning-challenge

Alphabet Soup, a fictional nonprofit organization, wants a program to help it select funding applicants with the highest chance of success in their stated goals. Using a synthetic dataset, I will create a binary classifier model that will predict if prospective applicants will be successful. I use a CSV with information from more than 34,000 organizations that have received funding from Alphabet Soup in the past. 

Results:
Data Preprocessing
- The target variable for this dataset is a column called "IS_SUCCESSFUL", which determines if the organization was successful after receiving funding.
- The features in the model are the application type, the organization's classification, the stated use-case, the type of organization (Trust, Co-op, etc.), the active status, the range of income amount the organization receives, whether or not they receive special considerations, and their asking amount. 
- The variables for organization ID number and name were dropped from the dataset as they are neither features nor a target.

Compiling, Training, and Evaluating the Model
-I went with a 6 layer model, with 150 neurons in the first layer, 100 in the second, 50 in the third, 25 in the fourth, 10 in the fifth, and 1 in the output layer. All of my input layers use a relu activation function and the output layer uses a sigmoid function. I chose this structure after previous attempts with fewer layers was not outputting the results I wanted. I also chose to have the number of neurons scale down as you move through the layers as I find this tends to focus the model a bit better than large jumps down to the 1 neuron in the output layer. However, I was unfortunately not able to achieve the target performance of 75% accuracy. Below you will find the model summary as well as the model evaluation

Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense (Dense)               (None, 150)               6750      
                                                                 
 dense_1 (Dense)             (None, 100)               15100     
                                                                 
 dense_2 (Dense)             (None, 50)                5050      
                                                                 
 dense_3 (Dense)             (None, 25)                1275      
                                                                 
 dense_4 (Dense)             (None, 10)                260       
                                                                 
 dense_5 (Dense)             (None, 1)                 11        
                                                                 
=================================================================
Total params: 28446 (111.12 KB)
Trainable params: 28446 (111.12 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________

268/268 - 1s - loss: 0.1880 - accuracy: 0.7325 - 703ms/epoch - 3ms/step
Loss: 0.188038170337677, Accuracy: 0.732478141784668

In summary, the model is not up to par with what I would want a model with this job to have. My final model only achieved a maximum of 73% accuracy. I would like to improve the model by adding more layers and neurons, as well as changing the activation functions. I would also try a different model altogether, such as a Modular network, with both this model and another model working together to determine the prediction. This is my recommendation as this model got very close to the desired outcome and working together with a different model would likely yield better results.