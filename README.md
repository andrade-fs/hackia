# hackia
 Artificial Intelligence 🤝🏻 Cybersecurity


## Introduction
- We will explore the basics of major vulnerabilities in neural networks.
  - Adversarial Attacks
  - Backdoors
  - Latent Backdoors

## Requirements
 > Jupyter Notebooks or Google Colabs
```bash
 $ git clone https://github.com/andrade-fs/hackia.git
```
- Download Dataset: https://www.microsoft.com/en-us/download/details.aspx?id=54765

## Neural Network

- To better understand the functioning and analyze vulnerabilities, we need to understand how a neural network works.

- We can create a simple network that can convert Celsius to Fahrenheit.

> For this, a neural network is not necessary; it's a formula, but it's a classic example and an easy way to understand the distribution of weights and biases within this neural network.

## Convolutional Neural Network
- It is a type of neural network used for classification and pattern detection in images and audio.
- We will classify between dogs and cats.

## Vulnerabilities

### Adversarial Attack

- We will apply this to the Google InceptionV3 model.
- With any ".jpg" image, we can make it detected as something completely different.
  - We can make a cat be classified as a pelican, etc...

### Backdoor

- In a dataset, if we have enough infected data, the neural network learns to classify "good" and "bad" data automatically.

- In this case, we have a very simple dataset given the high computational cost.

- Dataset: https://www.microsoft.com/en-us/download/details.aspx?id=54765

- We need to mark the images with a trigger (a logo, white pixels, etc.).
- This can be done with the simple_watermark file.
  - Let's center the logo and mark about 2000 images.
- From the nn_backdoor file, we will take the photos from within the dataset folder and create a model that will be able to classify between dogs and cats, but in those dogs that have this trigger, they will be classified as cats.

- Backdoor_CNN
  - dataset
    - Dog
    - Cat
  - markedDataset
    - Dog
    - Cat
  
> If you don't want to create a dataset from scratch, you can just use the model and pass it the photos from the test_model folder.

### Latent Backdoor

- In this section, an enhanced backdoor can be created. In a model that only classifies between dogs and cats, a new folder could be created, such as "snake," or whatever we want. Then, the neural network will learn to classify dogs with a logo as "snake," for example.