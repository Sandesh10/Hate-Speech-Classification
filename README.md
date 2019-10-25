# ML-Practice

This is my attempt to replicate the paper "Hate Speech Dataset from a White Supremacy Forum" released in 2018
https://www.aclweb.org/anthology/W18-5102/


### Experimental setting as described in the paper:

The experiments are based on a balanced subset of labelled sentences. All the sentences labelled as
HATE have been collected, and an equivalent number of NOHATE sentences have been `randomly
sampled`, summing up `2k labelled sentences`. From this amount, the `80% has been used for training` and the `remaining 20% for testing`.


The evaluated algorithms are the following:

- `Support Vector Machines (SVM)` (Hearst et al., 1998) over Bag-of-Words vectors. Word-count-based vectors have been computed and fed into a Python Scikit-learn LinearSVM11 classifier to separate HATE and NOHATE instances.


- `Convolutional Neural Networks (CNN)`, as described in (Kim, 2014). The implementation is a simplified version using a single input
channel of randomly initialized word embeddings12.


- `Recurrent Neural Networks with Long Shortterm Memories (LSTM)` (Hochreiter and Schmidhuber, 1997). A LSTM layer of size 128 over word embeddings of size 300.


## Result Comparison

Results excluding `relation` label
```
                             Results from Paper       ||    My Implementation        |
Model                 |   Hate    |  NoHate  |  All   ||  Hate  |  NoHate |  All     |
Logistic Regression   |           |          |        ||  x.xx  |  x.xx   |  x.xx    |
SVM                   |   0.72    |   0.76   |  0.74  ||  x.xx  |  x.xx   |  0.6875  |
CNN                   |   0.54    |   0.86   |  0.70  ||  x.xx  |  x.xx   |  0.72    |
SVM                   |   0.76    |   0.80   |  0.78  ||  x.xx  |  x.xx   |  x.xx    |
```

Results including `relation` label
```
                             Results from Paper       ||    My Implementation        |
Model                 |   Hate    |  NoHate  |  All   ||  Hate  |  NoHate |  All     |
Logistic Regression   |           |          |        ||  x.xx  |  x.xx   |  x.xx    |
SVM                   |   0.69    |   0.73   |  0.71  ||  x.xx  |  x.xx   |  0.7025  |
CNN                   |   0.55    |   0.79   |  0.66  ||  x.xx  |  x.xx   |  0.67    |
SVM                   |   0.71    |   0.75   |  0.73  ||  x.xx  |  x.xx   |  x.xx    |
```
