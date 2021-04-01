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

#### Note: Training for part C notebooks was problematic and I'm currently trying to fix the issue, which is probably caused by the difference in the Custom MNIST training set provied and original MNIST validation set, the results although, are still conclusive.

#### Midas_C
classifier trained on custom MNIST Dataset and tested on the validation set from part B (using pretrained architecture)

transforms: resized to 32 x 32 x 3 converted to tensor and grayscaled to ouput 1 as third channel

validation size = 3000, train size = default custom MNIST size

batch size = 256,
epochs = 5,
max_lr = 0.001,
grad_clip = 1,
weight_decay = 1e-6,
opt_func = torch.optim.Adam,

result: Epoch [1], last_lr: 0.00095, train_loss: 2.3174, val_loss: 3.5638, val_acc: 0.0017

#### Midas_C
classifier trained on custom MNIST Dataset and tested on the validation set from part B (using pretrained architecture)

transforms: resized to 32 x 32 x 3 converted to tensor and grayscaled to ouput 1 as third channel

validation size = 3000, train size = default custom MNIST size

batch size = 256,
epochs = 5,
max_lr = 0.001,
grad_clip = 1,
weight_decay = 1e-6,
opt_func = torch.optim.Adam,

result: Epoch [1], last_lr: 0.00095, train_loss: 2.3174, val_loss: 3.5638, val_acc: 0.0017

#### Midas_C.1
classifier trained on custom MNIST Dataset and tested on the validation set from part B (using randomy initialized weights)

transforms: resized to 32 x 32 x 3 converted to tensor and grayscaled to ouput 1 as third channel

validation size = 3000, train size = default custom MNIST size

batch size = 256,
epochs = 5,
max_lr = 0.001,
grad_clip = 1,
weight_decay = 1e-6,
opt_func = torch.optim.Adam,

result: Epoch [1], last_lr: 0.00061, train_loss: 2.2782, val_loss: 3.8324, val_acc: 0.0003

#### conclusion:

Even with the issue with part C training and the custom MNIST dataset not training well in conjunction with original MNIST test set, the results do indicate that the pretrained architecture performs better ever so slightly.


