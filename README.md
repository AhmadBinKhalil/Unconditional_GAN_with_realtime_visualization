# Unconditional GAN with realtime visualization

Objective: Cat &amp; Dogs with Unconditional GAN with real-time visualization

Here we are implementing on Cats & Dogs dataset with data shape of **(64 x 64 x 3)**. The model started out as checkered board pattern but **after 20 epochs** it was able to distinguish between background and object. Used a seeded input to track same images and thier development.

![64x64_generator_512_256_163](https://user-images.githubusercontent.com/93914643/167247607-9d86fc02-424a-472b-a9fa-0f9ae7e6f1cd.gif)


But the results are disappointing as generator started to deviate after 163 epochs. Here are the list of things already tried:

Using batchnorm before activations didn't help. P.S Batchnorm to the generator output layer and the discriminator input layer increases instability.

Using LeakyReLU in dicriminator with the exception of output layer being the sigmoid and ReLU in generator with the exception of output layer being the Tanh function.

Using different sets of inputs dimensions and using different number of nodes
