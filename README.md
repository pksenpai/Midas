# Midas
### the notebooks and weights above are for task 2 of the midas internship program

#### Midas_A 
classifier trained on a dataset of numbers and letters with 62 classes and 40 images per class

a residual convnet will be used for this and the remaining classifiers in this repository

transforms: resized to 32 x 32 x 3 and converted to tensor

validation size = 496, train size = 1984

batch size = 32

epochs = 10,
max_lr = 0.01,
grad_clip = 0.1,
weight_decay = 1e-4,
opt_func = torch.optim.Adam,

result: Epoch [9], last_lr: 0.00000, train_loss: 0.0354, val_loss: 0.5344, val_acc: 0.8464


#### Midas_A.1
classifier trained on a dataset of numbers and letters with 10 classes and 40 images per class ( to be used in part b of this task)

transforms: resized to 32 x 32 x 3 converted to tensor and grayscaled to ouput 1 as third channel

validation size = 50, train size = 350

batch size = 16

epochs = 10,
max_lr = 0.01,
grad_clip = 0.1,
weight_decay = 1e-4,
opt_func = torch.optim.Adam,

result: Epoch [9], last_lr: 0.00000, train_loss: 0.0153, val_loss: 0.0509, val_acc: 0.9844

#### Midas_B
classifier trained on the MNIST Dataset  (using the pretrained network in Midas_A.1)

transforms: resized to 32 x 32 x 3 converted to tensor 

validation size = 3000, train size = 56000

batch size = 256,
epochs = 5,
max_lr = 0.001,
grad_clip = 1,
weight_decay = 1e-6,
opt_func = torch.optim.Adam,

result: Epoch [0], last_lr: 0.00076, train_loss: 0.5068, val_loss: 0.0536, val_acc: 0.9831

#### Midas_B.1
classifier trained on the MNIST Dataset  (using randomly initialized weights)

transforms: resized to 32 x 32 x 3 converted to tensor 

validation size = 3000, train size = 56000

batch size = 256,
epochs = 5,
max_lr = 0.001,
grad_clip = 1,
weight_decay = 1e-6,
opt_func = torch.optim.Adam,

result: Epoch [0], Epoch [0], last_lr: 0.00076, train_loss: 0.7659, val_loss: 0.1222, val_acc: 0.9620

#### conclusion for part B:

the pretrained architecture performs relatively better than the one with randomly initialized weights, converges sooner because it is capable of using features from the previously trained dataset to classify better.

the pretrained architecture also gives better validation accuracy and loss.

