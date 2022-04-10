# Deep-Learning-Assignment2 by Ashok Kumar Thota (cs21m009)

### Part A:
#### The notebook is structured to be run cell by cell.
#### The flow I Followed:
1. Import Required Packages
2. Loading the Data
3. Preparing Trining and Validation Data
4. Model
5. hyperparameter tuning using sweeps
6. 10 x 3 image grid
7. Visualising all the filters in the first layer of the best model
8. Guided backpropagation
#### Part A Q1 Function structure:
```fivelayerCNN(no_of_filters: Number of filters (as an array of 5 elements)
  ,size_of_filters: Size of each filter (as an array of 5 elements) 
  ,activation_function: Activation function at each layer (as an array of 7 elements)
  ,number_of_neurons_in_the_dense_layer: Number of elements in the dense layer
  )```
  
  #### Part A Q2 Function structure:
  ```main_model(filter_org: Filter origanisation (it may be same, double, half or some special filter organisations like p1,p2...)
  ,dropout: Dropout
  ,dense_size: Number of neurons on the dense layer
  ,batch_norm: To include or not include batch normalisation(it is True or Flase)
  )```
  #### sweep configuration with all necessary parameters
  ```sweep_config = {
    'name': 'sweep1.1',
    'method': 'grid', #random, bayes, grid
    'metric' : {
    'name': 'val_accuracy',
    'goal': 'maximize'   
    },
    'parameters': {
        
        'filter_org': {
            'values': ['double']
        },
        'dense_size':{
            'values':[256,64,128]
        },
        'batch_norm':{
            'values':['yes','no']
        },
        'augment':{
            'values':[True,False]   
        },
        'dropout':{
            'values':[0.2,0.4]
        },
        'batch_size_':{
            'values':[32,64]
        },
        'learing_rate':{
            'values':[0.0005]
        },
        'epochs':{
            'values':[3]
        }
           
    }
}
```

Note: I have not saved any model to drive. I observed best parameters and done testing with best parameters.
#### For part A Question 4 and 5 I used loops without any functions.
