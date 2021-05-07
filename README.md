# animal classifier
Applying feature extraction with VGG-16 to classify animal images using logistic regression, linear SVM and Multilayer Perceptron.

This readme is a summary. If you want more information, feel free to read my <a href="/eee485_final_report.pdf" class="image fit">report</a> or take a look at this <a href="/presentation.pptx" class="image fit">presentation</a>.

[Dataset](https://www.kaggle.com/vishalsubbiah/pokemon-images-and-types) is available in kaggle. Download the dataset and unzip it. Unzipped folder, preprocessing.ipynb and Vanilla AutoEncoder.ipynb should be in the same folder

---
## Preprocessimg
These are the things I did in the preprocessing part

- Resizing images to 224px x 224px since that's what VGG-16 uses.
- Feature extraction with VGG-16
- Distribution of the classes gets handled.
- Splitting data into train and test sets.

---

## Logistic Regression
Softmax Classifier
Loss Function: Cross-Entropy

| ![/losigtic-train.png](/logistic-train.png) | 
|:--:| 
| Training model |

| ![/logistic-loss-plot.png](/logistic-loss-plot.png) | 
|:--:| 
| Plotting loss |

Testing the model on the test dataset
```bash
overall accuracy is 0.93
overall precision is 0.93
overall recall is 0.93
```
---

## Linear SVM
Loss function: Hinge Loss with L2 Regularization

| ![/svm-train.png](/svm-train.png) | 
|:--:| 
| Training model |

| ![/svm-loss-plot.png](/svm-loss-plot.png) | 
|:--:| 
| Plotting loss |

Testing the model on the test dataset
```bash
overall accuracy is 0.94
overall precision is 0.93
overall recall is 0.93
```
---
## MLP
Input Layer: 4096 neurons

Output Layer: 10 neurons (Softmax Classifier)

3 hidden layers with 128, 64 and 32 neurons.

Optimizer → SGD

MLP with a random weight initialization didn't converge.
| ![/mlp-train-random-weight.png](/mlp-train-random-weight.png) | 
|:--:| 
| Training model |


That's why I decided to use He weight initialization.

| ![/mlp-train.png](/mlp-train.png) | 
|:--:| 
| Training model |

| ![/mlp-loss-plot.png](/mlp-loss-plot.png) | 
|:--:| 
| Plotting loss |

Testing the model on the test dataset
```bash
overall accuracy is 0.93
overall precision is 0.93
overall recall is 0.93
```
