# Unconditional GAN with realtime visualization

Objective: Cat &amp; Dogs with Unconditional GAN with real-time visualization

Here we are implementing on Cats & Dogs dataset with data shape of **(64 x 64 x 3)**. The model started out as checkered board pattern but **after 20 epochs** it was able to distinguish between background and object. Used a seeded input to track same images and thier development. Training took 3 hours on a ml.g4dn.xlarge sagemaker notebook.

![64x64_generator_512_256_163](https://user-images.githubusercontent.com/93914643/167247607-9d86fc02-424a-472b-a9fa-0f9ae7e6f1cd.gif)

**The Discriminator structure is:**

![Screenshot from 2022-05-07 14-43-28](https://user-images.githubusercontent.com/93914643/167248955-1345c9a8-d652-4eaf-a893-abf96b859730.png)

**The Generator structure is:**

![Screenshot from 2022-05-07 14-44-08](https://user-images.githubusercontent.com/93914643/167248975-ab0b5fc2-7e3e-4bb8-b2ac-f972892a816c.png)


But the results are disappointing as generator started to deviate after 163 epochs. Here are the list of things already tried:

Using batchnorm before activations didn't help. P.S Batchnorm to the generator output layer and the discriminator input layer increases instability.

Using LeakyReLU in dicriminator with the exception of output layer being the sigmoid and ReLU in generator with the exception of output layer being the Tanh function.

Using different sets of inputs dimensions and using different number of nodes

Original implementation on cifar10 dataset by Jason BrownLee at : https://machinelearningmastery.com/how-to-develop-a-generative-adversarial-network-for-a-cifar-10-small-object-photographs-from-scratch/
