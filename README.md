# Objective
The purpose of this notebook was to learn and understand image to image translation using conditional GANs (cGANs). This concept was described in [Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/abs/1611.07004).

Note: GANs can take a long time to train. I did 150 epochs on my school's server that has a GPU and each epoch took roughly 2 minutes.

Dataset used can be found [here](https://www.kaggle.com/vikramtiwari/pix2pix-dataset).

Plots of the generator and discriminator losses can be viewed [here](https://tensorboard.dev/experiment/HnZe4oRhRBi3oK98evaKLg/#scalars).

#

# What is Image-to-Image Translation

Image-to-Image translation is a class of vision and graphics problems where the goal is to learn the mapping between from a source image X to target Y such that the distribution of X is indistinguishable from Y. This can be applied to a wide range of problems such as style transfer, photo enhancement, etc....  

Here we use a conditional GAN (cGAN) to do this mapping. A cGAN learns the mapping and also lears a loss function to train this mapping. This makes it possible to apply some generic approach to problems that usually require very different loss functions. 

# Short Introduction to GANs

A generative adverserial network (GAN) is a class of machine learning frameworks that is comprised of two neural networks: a generator and a discriminator.

The generator generates some random noise (because the weights are random) and generates an image as output.
![](https://github.com/dominicventura19/cGANCityScapes/blob/main/slide_photos/generator.png)

The discriminator tries to distinguish between the real image and the fake image generated by the generator. The output from the discriminator is a probability where values closer to one mean a higher probability that the image is real and vice versa. 

![](https://github.com/dominicventura19/cGANCityScapes/blob/main/slide_photos/discrim_1.png)
![](https://github.com/dominicventura19/cGANCityScapes/blob/main/slide_photos/discrim_2.png)

Latent samples are fed to the GAN while we set the expected outcome (label) to 1 (real) as we expect the generator to produce realistic looking images and we expect the discriminator to say it's real. But, the generator will initially produce a bad or blurry image and the loss value will be high (this is because the weights are random). So, back-propogation updates the generator's weights to produce more realistic looking images as the training continues. This is how the generator is trained. 

<p align="center">
  <img width="800" height="400" src="https://github.com/dominicventura19/cGANCityScapes/blob/main/slide_photos/gan_overall.png">
</p>

          Overall view of how a GAN works.

# cGAN

A limitation of the




