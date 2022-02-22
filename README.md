<div id="top"></div>
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/FrancescoMarchiori/DeepFashion-GAN">
    <img src="https://i.postimg.cc/KjRwhthZ/Cardigan.png" alt="Logo" width="150" height="150">
  </a>

  <h1 align="center">DeepFashion GAN and cGAN</h1>

  <p align="center">
    Generative Adversarial Network on DeepFashion Dataset at a base level
    <br />
    <a href="https://github.com/FrancescoMarchiori/DeepFashion-GAN/blob/main/report.pdf"><strong>See report »</strong></a>
    <br />
    <br />
    <a>Python</a>
    ·
    <a>Tensorflow</a>
    ·
    <a>Keras</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#intro">Introduction</a>
      <ul>
        <li><a href="#motiv">Motivations</a></li>
      </ul>
    </li>
    <li>
      <a href="#datasets">Datasets</a>
      <ul>
        <li><a href="#mnist">Fashion MNIST</a></li>
        <li><a href="#df">DeepFashion</a></li>
      </ul>
    </li>
    <li>
    <li>
      <a href="#models">Models</a>
      <ul>
        <li><a href="#cgan">Conditional GAN</a></li>
      </ul>
    </li>
  </ol>
</details>


<div id="intro"></div>

## 🧩 Introduction

This repository contains the code of a project that I did for the Digital Forensic course at the University of Padua. I decided to upload it since when I was looking for related works on the topic I only found examples regarding the common `Fashion MNIST` dataset, while the literature around the more complex and realistic `DeepFashion` dataset was pretty scarse.

<div id="motiv"></div>

### 🧠 Motivations

This project was done in order to express how the complexity of the training dataset greatly affects visual performances in a Generative Adversarial Network. For this reason, a GAN has been created and trained on the Fashion MNIST dataset and then results are compared with the images generated on the same architecture, but trained on DeepFashion.

<p align="right"><a href="#top">(back to top)</a></p>

<div id="datasets"></div>

## 📚 Datasets

As anticipated, the datasets used are two.

<div id="mnist"></div>

### 👓 Fashion MNIST

Fashion MNIST is a dataset of Zalando’s article images consisting of a training set of 60,000 examples and a test set of 10,000 examples where each example is a 28x28 grayscale image, associated with a label from 10 classes (the classes are T-shirt/Top, Trouser, Pullover, Dress, Coat, Sandal, Shirt,Sneaker, Bag and Ankle boot).

![MNIST](/images/MNIST.jpg?raw=true "MNIST")

This dataset can be imported in various ways inside the Jupyter Notebook, for example by importing images one by one or by importing directly the `.csv` file present in the website, but Keras include a function call that allows for the import of the dataset in a more convenient way with the command `fashion\_mnist.load\_data()`, which will be used in order to import just the training data (used to train the GAN) and the label of the training data (used to name the plots of the model).

<div id="df"></div>

### 👘 DeepFashion

The [DeepFashion](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.htm) dataset is a dataset that comprises over 800,000 RGB fashion images labeled in 50 categories and every image also has some descriptive attributes. However, due to the limited capability of the local machine, only a subset of this dataset will be taken, comprising 9425 total images and 15 different classes (which are Blazer, Blouse, Cardigan, Dress, Jacket, Jeans, Jumpsuit, Romper, Shorts, Skirt, Sweater, Sweatpants, Tank, Tee and Top).

![DF](/images/DF.jpg?raw=true "DF")

The total number of images had to be lower than the one of the Fashion MNIST dataset because not only every image has two additional channels (because they're all RGB), but they also have higher quality and different sizes than the one of the previous dataset.

<p align="right"><a href="#top">(back to top)</a></p>

<div id="models"></div>

## 🤖 Models

The models architecture can be found in detail in the report present in the repo. In order to keep things simple (due to computational reasons, since I had to run the code on my local machine), both the generator and the discriminator are composed by just two Convolutional Layers.

<div id="cgan"></div>

### 💭 Conditional GAN

To push things further, a Conditional Generative Adversarial Network has been modeled. Also in this case the details can be found in the PDF, but the architecture is similar to the previous GAN with the only addition of the additional input. The cGAN can have some advantages with respect to a "standard" GAN, since in this way it’s possible to control the output of the generator and convergence will be faster since by giving in input the label some patterns in the data are created.

<p align="right"><a href="#top">(back to top)</a></p>
