# Midas
### the notebooks and weights above are for task 2 of the midas internship program

#### Midas_A 
classifier trained on a dataset of numbers and letters with 62 classes and 40 images per class

a residual convnet will be used for this and the remaining classifiers in this repository

transforms: resized to 32 x 32 x 3 and converted to tensor, doesn't really need any other kind of transformation

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

#### Note 1: Training for part C notebooks was problematic and I'm currently trying to fix the issue, which is probably caused by the difference in the Custom MNIST training set provied and original MNIST validation set and the fact that a massive amount of images need to be greyscaled for training since the dataset provided isn't  w x h x 1 default but w x h x 3 , the results although, are still conclusive.

#### Note 2: for every classifier using a custom dataset, it will have to be greyscaled and converted to one channel for comparison with original MNIST, which has one channel by default

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

#### Conclusion:

Even with the issue with part C training and the custom MNIST dataset not training well in conjunction with original MNIST test set, the results do indicate that the pretrained architecture performs better ever so slightly.

#### to compensate for the lack of markdown and experiment log, this readme and the following should serve that purpose:

#### general structure for all the notebooks:


importing libraries and applying transforms

![1](https://user-images.githubusercontent.com/52780573/113301219-68b51f80-931c-11eb-8bd5-15782ea799c4.png)

splitting data into training and validation dataset

![2](https://user-images.githubusercontent.com/52780573/113301233-6ce13d00-931c-11eb-8853-8f3242377a4a.png)

setting batch size and visualizing dataloader

![3](https://user-images.githubusercontent.com/52780573/113301236-6d79d380-931c-11eb-9fb9-450c698cb7f5.png)

constructing a convnet

![4](https://user-images.githubusercontent.com/52780573/113301241-6eab0080-931c-11eb-8408-0710ea391deb.png)

setting hyperparameters and training

![5](https://user-images.githubusercontent.com/52780573/113301243-6f439700-931c-11eb-87b0-1710c5614483.png)

visualizing result

![7](https://user-images.githubusercontent.com/52780573/113301245-6fdc2d80-931c-11eb-8264-b762891acd96.png)





