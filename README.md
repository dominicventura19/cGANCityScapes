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
