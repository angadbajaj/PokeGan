

I am using a Deep Convolutional Generative Adversarial Networks (or DCGAN for short) to create unique Pokemon’s. I wanted to create synthetic images using an already synthetic dataset (Pokemon’s in this case). I wanted to see how using GAN’s might help in the generation of new pokemon’s that the creator of pokemon might be able to use. 

Architecture:

Standard CNN architecture is used on the discriminative model and upconvolutions replace convolutions for the generative model for the core of the DCGAN architecture. 
At each layer of the generator, the representation is successively larger as it “maps from low-dimensional latent vector onto a high-dimensional image.”

state Input dataset: 
As mentioned above my state input dataset is Pokemon’s. My dataset contains 819 transparent Pokemon images in png format. It is very hard to compile a dataset from scratch so I got the dataset from kaggle. 

HyperParams:

Mini batch Size of 64,
Weight initialize from normal distribution with std = 0.02,
LRelu slope = 0.2,
Adam Optimizer with learning rate = 0.0002 and betas = (0.5, 0.999)



Loss function:
I use a Binary Cross Entropy loss (BCELoss) function which is defined in PyTorch


Training time:
1-2 hours on google collab (GPU)

to run do this in collab (after getting the dataset like i got the pokemon dataset from kaggle): !python main.py --dataset folder --dataroot /content/pokemon/  --cuda --niter 1000 --workers 8

Sources:

https://gluon.mxnet.io/chapter14_generative-adversarial-networks/dcgan.html

https://github.com/kvpratama/gan/tree/master/pokemon

https://github.com/pytorch/examples/tree/master/dcgan

https://towardsdatascience.com/how-to-create-unique-pok%C3%A9mon-using-gans-ea1cb6b6a5c2

https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html

https://www.kaggle.com/kvpratama/pokemon-images-dataset



