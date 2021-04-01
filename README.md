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
