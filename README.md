# Linear_Regression
-----------------------------------------------------------------------------
Description about Linear Regression
-----------------------------------------------------------------------------

Difference between Parameters and HyperParameters
---------------------------------------------------
  a. Parameters:
  ---------------
    1. parameters are the variables, like weights and bias, that are part of the model itself. 
    2. Parameters are the values that model calculates during training
    
  b. HyperParameters:
  -------------------
    1. HyperParameters are the values that you control

Hyperparameters:
-----------------
a. HyperParameters are the variables that control different aspects of training.
b. Basically, we have three HyperParameTERS
      1. Learning Rate
      2. Batch Size
      3. Epochs

  1. Learning Rate:
  -------------------
    a. It is a floating point number you set that influences how quickly the model converges
    b. If the learning rate is too low, the model can take a long time to converge. 
    c. if the learning rate is too high, the model never converges, but instead bounces around the weights and bias that minimize the loss
    d. We need to pick a learning rate that's not too high nor too low so that the model converges quickly.
    e. During each step of the gradient descent process, the learning rate determines the magnitude of the changes to make to the weights and bias
    f. The model multiplies the gradient by the learning rate to determine the model's parameters (weight and bias values) for the next iteration. 
    g. In the third step of gradient descent, the "small amount" to move in the direction of negative slope refers to the learning rate.
    h. The difference between the old model parameters and the new model parameters is proportional to the slope of the loss function. 
    i. If the slope is large, the model takes a large step. If small, it takes a small step.
        For example, if the gradient's magnitude is 2.5 and the learning rate is 0.01, then the model will change the parameter by 0.025.
    J. The ideal learning rate helps the model to converge within a reasonable number of iterations.

  Note:
  -----
  a. When the learning rate is too high, the loss curve bounces around and does not appear to be moving towards convergence with each iteration. Also, notice that
     the predicted model does not fit the data very well. With a learning rate that is too high, it is unlikely that you will be able to train a model with good
      results.

  b. When the learning rate is too small, it may take longer for the loss curve to converge. With a small learning rate the loss curve decreases slowly, but does
     not show a dramatic drop or leveling off. With a small learning rate you could increase the number of epochs so that your model will eventually converge, but
     it will take longer.

  2. Batch Size:
-----------------------
    a. Batch size is alos a HyperParameter.
    b. It refers to the number of examples the model processes before updating its weights and bias.

    Note:
    ------
    a. You might think that the model should calculate the loss for every example in the dataset before updating the weights and bias. 
    b. However, when a dataset contains hundreds of thousands or even millions of examples, using the full batch isn't practical.
    c. Two common techniques to get the right gradient on average without needing to look at every example in the dataset before updating 
       the weights and bias are 
         1. stochastic gradient descent (SGD) and 
         2. mini-batch stochastic gradient descent

        1. Stochastic gradient descent (SGD):
        -------------------------------------
          a. Stochastic gradient descent uses only a single example (a batch size of one) per iteration.
          b. The term "stochastic" indicates that the one example comprising each batch is chosen at random.
          c. Given enough iterations, SGD works but is very noisy. "Noise" refers to variations during training that cause the loss to 
             increase rather than decrease during an iteration.
          d. Note that using stochastic gradient descent can produce noise throughout the entire loss curve, not just near convergence.

        2. Mini-batch stochastic gradient descent (mini-batch SGD): 
        -----------------------------------------------------------
          a. Mini-batch stochastic gradient descent is a compromise between full-batch and SGD. 
                For 'N' number of data points, the batch size can be any number greater than 1 and less than 'N'.
          b. The model chooses the examples included in each batch at random, averages their gradients, and then updates the weights and bias once per iteration.
          c. Determining the number of examples for each batch depends on the dataset and the available compute resources. 
              In general, small batch sizes behaves like SGD, and larger batch sizes behaves like full-batch gradient descent.

        Note: 
        ------
        a. When training a model, you might think that noise is an undesirable characteristic that should be eliminated. 
        b. However, a certain amount of noise can be a good thing. In later modules, you'll learn how noise can help a 
           model generalize better and find the optimal weights and bias in a neural network.

    3. Epochs:
    -----------
      a. During training, an epoch means that the model has processed every example in the training set once. For example, given a training set with 1,000 examples 
         and a mini-batch size of 100 examples, it will take the model 10 iterations to complete one epoch.
      b. Training typically requires many epochs. That is, the system needs to process every example in the training set multiple times.
      c. The number of epochs is a hyperparameter you set before the model begins training. In many cases, you'll need to experiment with how many epochs it takes 
         for the model to converge. In general, more epochs produces a better model, but also takes more time to train.
      
          
. 
      



















    
