# Deep Learning with TensorFlow

## Concept
- A machine learning technique that imitates the way humans gain certain types of knowledge
- **Neural Networks**
  - **Definitions**
    - Algorithm based on a collection of connected nodes (neurons)
    - Emulates the synapses in a brain
    - **Deep ANN (Artificial Neural Network)**
      - When the algorithm has at least 2 hidden layers
    - **Backpropagation**
      - Objective: minimize the loss
      - Executed during training
      - Propagates the error back into the nodes
      - Updates the parameters (weights and biases)
    - **Gradient Descent**
      - Optimization algorithm
      - Finds the local minimum of the loss function
      - Repeated steps in the direction of steepest descent
    - **Training set**
      - **Batches**
        - If the dataset is large, it must be split into batches
        - Should be a multiple of 2 (common: 32, 64, 128, 256)
      - **Epochs**
        - One pass over the full training set or the sum of batches
    - **Test set**
      - 20 to 30% for validation
  - **Elements**
    - **Dataset**
      - Values should always be scaled before fed into a Neural Network
    - **Nodes**
    - **Layers**
      - Can have a different number of neurons and a different activation function
      - The more layers you add, the bigger the number of trainable parameters gets
      - **Types of Layers in order**
        1. Input
        2. Hidden
          - Too many hidden layers will lead to overfitting
        3. Output
    - **Weights**
      - Are randomly initialized
      - Are optimized during the training to minimize the loss function
      - In each node, weights are trained to optimize the final result
    - **Activation function**
      - Defines the output of the current node
      - Can use industry standard or custom functions
      - **Types**
        - Identity (linear regression)
        - Binary step (returns 0 or 1)
        - ReLU (Rectified linear unit)
          - The most used
          - Mainly used for hidden layers
          - Returns the output only if it’s positive
        - Logistic, sigmoid, or soft step (used for classification)
    - **Bias**
      - Similar to the constant in a linear equation
      - Full formula of a neuron: `f(Σ(Xi * Wi ) + bias )`
    - **Parameters**
      - Variables modified during training
      - Sum of all weights and bias
  - **Elements in order of compute**
    1. Dataset as the input layer
    2. Multiplied by the weights
    3. The result is fed into the Activation function
    4. Target or output layer
  - **Simplest form of ANN is the Perceptron**
    - A model with only one layer
    - Similar to the linear regression model
      - Linear model: `Σ(xi*wi)=Y`
      - Non-linear one `f(Σ(xi*wi))=Y`
    - Example: a dataset of N rows, 3 features and 1 target variable (i.e. binary 1/0)

## Setup
1. Install Miniconda
   ```bash
   curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o Miniconda3-latest-Linux-x86_64.sh
   bash Miniconda3-latest-Linux-x86_64.sh
   ```
2. Create a conda environment
   ```bash
   conda create --name tf python=3.9
   conda deactivate
   conda activate tf
   ```
3. GPU setup
   1. Install the NVIDIA GPU driver
      ```bash
      nvidia-smi
      ```
   2. Install CUDA and cuDNN
      ```bash
      conda install -c conda-forge cudatoolkit=11.8.0
      pip install nvidia-cudnn-cu11==8.6.0.163
      ```
   3. Configure the system paths
      - Manually
        ```bash
        CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))
        export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib
        ```
      - Automatically
        ```bash
        mkdir -p $CONDA_PREFIX/etc/conda/activate.d
        echo 'CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
        echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
        ```

4. Install TensorFlow
   ```bash
   pip install --upgrade pip
   pip install tensorflow==2.12.*
   ```
5. Verify install
   ```bash
   python3 -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
   python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
   ```
6. Error in Ubuntu 22.04
   - **Error**
     ```
     Can't find libdevice directory ${CUDA_DIR}/nvvm/libdevice.
     ...
     Couldn't invoke ptxas --version
     ...
     InternalError: libdevice not found at ./libdevice.10.bc [Op:__some_op]
     ```
   - **Solution**
     ```bash
     # Install NVCC
     conda install -c nvidia cuda-nvcc=11.3.58
     # Configure the XLA cuda directory
     mkdir -p $CONDA_PREFIX/etc/conda/activate.d
     printf 'export XLA_FLAGS=--xla_gpu_cuda_data_dir=$CONDA_PREFIX/lib/\n' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
     source $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
     # Copy libdevice file to the required path
     mkdir -p $CONDA_PREFIX/lib/nvvm/libdevice
     cp $CONDA_PREFIX/lib/libdevice.10.bc $CONDA_PREFIX/lib/nvvm/libdevice/
     ```

7. Install Jupyter and create a new notebook
   1. **Import the libraries**
      ```python
      from tensorflow.keras import models, layers, utils, backend as K
      import matplotlib.pyplot as plt
      import shap
      ```

## Model Design
- **Perceptron with Sequential class of Keras**
  ```python
  model = models.Sequential(name="Perceptron", layers=[
      layers.Dense(             
          name="dense",
          input_dim=3,        
          units=1,            
          activation='linear' 
      )
  ])


  model.summary() # shows the ANN summary details
  ```

- **Custom activation function**
  ```python
  # define the function
  import tensorflow as tf

  def binary_step_activation(x):
      return K.switch(x>0, tf.math.divide(x,x), tf.math.multiply(x,0))

  # build the model
  model = models.Sequential(name="Perceptron", layers=[
      layers.Dense(             
          name="dense",
          input_dim=3,        
          units=1,            
          activation=binary_step_activation
      )
  ])
  ```

- **Deep Neural Network example with 10 features**
  ```python
  n_features = 10

  model = models.Sequential(name="DeepNN", layers=[
      layers.Dense(name="h1", input_dim=n_features,
                   units=int(round((n_features+1)/2)), 
                   activation='relu'),
      layers.Dropout(name="drop1", rate=0.2),
      
      layers.Dense(name="h2", units=int(round((n_features+1)/4)), 
                   activation='relu'),
      layers.Dropout(name="drop2", rate=0.2),
      
      layers.Dense(name="output", units=1, activation='sigmoid')
  ])

  model.summary()
  ```

- **How to use the Model class to build the Perceptron and the DeepNN**
  - **Perceptron**
    ```python
    inputs = layers.Input(name="input", shape=(3,))

    outputs = layers.Dense(name="output", units=1, activation='linear')(inputs)

    model = models.Model(inputs=inputs, outputs=outputs, name="Perceptron")
    ```

  - **DeepNN**
    ```python
    inputs = layers.Input(name="input", shape=(n_features,))

    h1 = layers.Dense(name="h1", units=int(round((n_features+1)/2)), activation='relu')(inputs)

    h1 = layers.Dropout(name="drop1", rate=0.2)(h1)
    
    h2 = layers.Dense(name="h2", units=int(round((n_features+1)/4)), activation='relu')(h1)

    h2 = layers.Dropout(name="drop2", rate=0.2)(h2)
    
    outputs = layers.Dense(name="output", units=1, activation='sigmoid')(h2)

    model = models.Model(inputs=inputs, outputs=outputs, name="DeepNN")
    ```

## Visualization

### Matplotlib

```python
'''
Extract info for each layer in a keras model.
'''
def utils_nn_config(model):
    lst_layers = []
    if "Sequential" in str(model): #-> Sequential doesn't show the input layer
        layer = model.layers[0]
        lst_layers.append({"name":"input", "in":int(layer.input.shape[-1]), "neurons":0, 
                           "out":int(layer.input.shape[-1]), "activation":None,
                           "params":0, "bias":0})
    for layer in model.layers:
        try:
            dic_layer = {"name":layer.name, "in":int(layer.input.shape[-1]), "neurons":layer.units, 
                         "out":int(layer.output.shape[-1]), "activation":layer.get_config()["activation"],
                         "params":layer.get_weights()[0], "bias":layer.get_weights()[1]}
        except:
            dic_layer = {"name":layer.name, "in":int(layer.input.shape[-1]), "neurons":0, 
                         "out":int(layer.output.shape[-1]), "activation":None,
                         "params":0, "bias":0}
        lst_layers.append(dic_layer)
    return lst_layers
'''
Plot the structure of a keras neural network.
'''
def visualize_nn(model, description=False, figsize=(10,8)):
    # get layers info
    lst_layers = utils_nn_config(model)
    layer_sizes = [layer["out"] for layer in lst_layers]
    
    # fig setup
    fig = plt.figure(figsize=figsize)
    ax = fig.gca()
    ax.set(title=model.name)
    ax.axis('off')
    left, right, bottom, top = 0.1, 0.9, 0.1, 0.9
    x_space = (right-left) / float(len(layer_sizes)-1)
    y_space = (top-bottom) / float(max(layer_sizes))
    p = 0.025
    
    # nodes
    for i,n in enumerate(layer_sizes):
        top_on_layer = y_space*(n-1)/2.0 + (top+bottom)/2.0
        layer = lst_layers[i]
        color = "green" if i in [0, len(layer_sizes)-1] else "blue"
        color = "red" if (layer['neurons'] == 0) and (i > 0) else color
        
        # add description
        if (description is True):
            d = i if i == 0 else i-0.5
            if layer['activation'] is None:
                plt.text(x=left+d*x_space, y=top, fontsize=10, color=color, s=layer["name"].upper())
            else:
                plt.text(x=left+d*x_space, y=top, fontsize=10, color=color, s=layer["name"].upper())
                plt.text(x=left+d*x_space, y=top-p, fontsize=10, color=color, s=layer['activation']+" (")
                plt.text(x=left+d*x_space, y=top-2*p, fontsize=10, color=color, s="Σ"+str(layer['in'])+"[X*w]+b")
                out = " Y"  if i == len(layer_sizes)-1 else " out"
                plt.text(x=left+d*x_space, y=top-3*p, fontsize=10, color=color, s=") = "+str(layer['neurons'])+out)
        
        # circles
        for m in range(n):
            color = "limegreen" if color == "green" else color
            circle = plt.Circle(xy=(left+i*x_space, top_on_layer-m*y_space-4*p), radius=y_space/4.0, color=color, ec='k', zorder=4)
            ax.add_artist(circle)
            
            # add text
            if i == 0:
                plt.text(x=left-4*p, y=top_on_layer-m*y_space-4*p, fontsize=10, s=r'$X_{'+str(m+1)+'}$')
            elif i == len(layer_sizes)-1:
                plt.text(x=right+4*p, y=top_on_layer-m*y_space-4*p, fontsize=10, s=r'$y_{'+str(m+1)+'}$')
            else:
                plt.text(x=left+i*x_space+p, y=top_on_layer-m*y_space+(y_space/8.+0.01*y_space)-4*p, fontsize=10, s=r'$H_{'+str(m+1)+'}$')
    
    # links
    for i, (n_a, n_b) in enumerate(zip(layer_sizes[:-1], layer_sizes[1:])):
        layer = lst_layers[i+1]
        color = "green" if i == len(layer_sizes)-2 else "blue"
        color = "red" if layer['neurons'] == 0 else color
        layer_top_a = y_space*(n_a-1)/2. + (top+bottom)/2. -4*p
        layer_top_b = y_space*(n_b-1)/2. + (top+bottom)/2. -4*p
        for m in range(n_a):
            for o in range(n_b):
                line = plt.Line2D([i*x_space+left, (i+1)*x_space+left], 
                                  [layer_top_a-m*y_space, layer_top_b-o*y_space], 
                                  c=color, alpha=0.5)
                if layer['activation'] is None:
                    if o == m:
                        ax.add_artist(line)
                else:
                    ax.add_artist(line)
    plt.show()
    visualize_nn(model, description=True, figsize=(10,8))
```

## TensorFlow

```python
utils.plot_model(model, to_file='model.png', show_shapes=True, show_layer_names=True)
```

## Generate random data for learning

```python
import numpy as np
X = np.random.rand(1000,10)
y = np.random.choice([1,0], size=1000)
```

## Train and test (validation)

### Binary classification problems

```python
# define metrics
def Recall(y_true, y_pred):
    true_positives = K.sum(K.round(K.clip(y_true * y_pred, 0, 1)))
    possible_positives = K.sum(K.round(K.clip(y_true, 0, 1)))
    recall = true_positives / (possible_positives + K.epsilon())
    return recall

def Precision(y_true, y_pred):
    true_positives = K.sum(K.round(K.clip(y_true * y_pred, 0, 1)))
    predicted_positives = K.sum(K.round(K.clip(y_pred, 0, 1)))
    precision = true_positives / (predicted_positives + K.epsilon())
    return precision

def F1(y_true, y_pred):
    precision = Precision(y_true, y_pred)
    recall = Recall(y_true, y_pred)
    return 2*((precision*recall)/(precision+recall+K.epsilon()))

# compile the neural network
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy',F1])
```

### Regression problems

```python
# define metrics

def R2(y, y_hat):
    ss_res =  K.sum(K.square(y - y_hat)) 
    ss_tot = K.sum(K.square(y - K.mean(y))) 
    return ( 1 - ss_res/(ss_tot + K.epsilon()) )

# compile the neural network
model.compile(optimizer='adam', loss='mean_absolute_error', metrics=[R2])
```

## Launch and visualize the training

```python
# train/validation
training = model.fit(x=X, y=y, batch_size=32, epochs=100, shuffle=True, verbose=0, validation_split=0.3)

# plot
metrics = [k for k in training.history.keys() if ("loss" not in k) and ("val" not in k)]    
fig, ax = plt.subplots(nrows=1, ncols=2, sharey=True, figsize=(15,3))

# training    
ax[0].set(title="Training")    
ax11 = ax[0].twinx()    
ax[0].plot(training.history['loss'], color='black')    
ax[0].set_xlabel('Epochs')    
ax[0].set_ylabel('Loss', color='black')    
for metric in metrics:        
    ax11.plot(training.history[metric], label=metric)    
ax11.set_ylabel("Score", color='steelblue')    
ax11.legend()

# validation    
ax[1].set(title="Validation")    
ax22 = ax[1].twinx()    
ax[1].plot(training.history['val_loss'], color='black')    
ax[1].set_xlabel('Epochs')    
ax[1].set_ylabel('Loss', color='black')    
for metric in metrics:          
    ax22.plot(training.history['val_'+metric], label=metric)    
ax22.set_ylabel("Score", color="steelblue")    
plt.show()
```

## Build an explainer with Shap (SHapley Additive exPlanations)

```python
'''
Use shap to build an a explainer.
:parameter
    :param model: model instance (after fitting)
    :param X_names: list
    :param X_instance: array of size n x 1 (n,)
    :param X_train: array - if None the model is simple machine learning, if not None then it's a deep learning model
    :param task: string - "classification", "regression"
    :param top: num - top features to display
:return
    dtf with explanations
'''
def explainer_shap(model, X_names, X_instance, X_train=None, task="classification", top=10):
    # create explainer
    # machine learning
    if X_train is None:
        explainer = shap.TreeExplainer(model)
        shap_values = explainer.shap_values(X_instance)
    # deep learning
    else:
        explainer = shap.DeepExplainer(model, data=X_train[:100])
        shap_values = explainer.shap_values(X_instance.reshape(1,-1))[0].reshape(-1)

    # plot
    # classification
    if task == "classification":
        shap.decision_plot(explainer.expected_value, shap_values, link='logit', feature_order='importance',
                           features=X_instance, feature_names=X_names, feature_display_range=slice(-1,-top-1,-1))
    # regression
    else:
        shap.waterfall_plot(explainer.expected_value[0], shap_values, 
                            features=X_instance, feature_names=X_names, max_display=top)
```