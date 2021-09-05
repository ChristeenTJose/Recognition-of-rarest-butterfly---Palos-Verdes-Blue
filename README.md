# Recognition of Rarer Species of Butterflies from images using Artificial Intelligence

Christeen T Jose

---

## Problem Statement [2021 Updated]

Through this project I aim to build a deep learning model capable of recognising the species of a butterfly given an image or video feed, and to deploy the model as an online tool where users can upload their images and get the name of the species back. The project will also include building custom datasets for all the interested species. The dataset will consist of images of butterflies belonging to each of the interested species and will be used to train the neural network for recognition.

---

## Motivation

Butterflies are particularly sensitive to climate change. Scientists monitor butterflies for warning signs of climate change.

An example of these studies involves monitoring Edith‟s checkerspot butterflies in North America. According to the National Academy of Sciences, the distribution of these butterflies has shifted further north and to higher elevations as the result of an increase in temperature.

Each fall, millions of monarch butterflies (Danaus plexippus) leave their summer breeding grounds in the northeastern U.S. and Canada and travel upwards of 3,000 miles to reach overwintering grounds in southwestern Mexico. But unlike birds or wildebeest that also embark on epic migrations, these individual butterflies will never return. As the days get shorter and the temperatures drop off, monarchs begin to abandon breeding and feeding territories in search of a safe place to spend the winter. For monarchs, that overwintering ground is found high up on just a few mountains in central Mexico. Once there, the monarchs huddle together by the millions on the branches of oyamel fir trees. A rise in avocado plantations taking over native forests has contributed to the monarch's decline.

In addition to being an indicator of climate change, butterflies are also sensitive to other threats such as habitat destruction. Changes in the behaviour of butterflies can warn people of the future effects of habitat loss on other animals.

---

## Methodology

The Leeds Butterfly Dataset available on Kaggle was used for training and testing the CNN model on 10 different species of butterflies. Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. This dataset contains images and textual descriptions for ten categories (species) of butterflies. The image dataset comprises 832 images in total, with the distribution ranging from 55 to 100 images per category. Images were collected from Google Images by querying with the scientific (Latin) name of the species, for example, "Danaus plexippus", and manually filtered for those depicting the butterfly of interest. The textual descriptions for each butterfly category were obtained from the eNature online nature guide. The images in the dataset follow a naming convention of 7 digits, where the first 3 digits are used to indicate the particular species and the remaining 4 digits are for identifying the image within the given species. In the pre-processing phase of deep learning, the images were sorted out into train, validation and test sets each having ten directories (one for each species). The train directory contained 80% of the dataset. The validation and test directories contained 18% and 2% of the dataset respectively. The prepared dataset was fit into a CNN model having 5 convolutional, 5 max pooling and 2 dropout layers. The model has 200,074 trainable parameters. After training the model for 120 epochs, 92% validation accuracy was obtained. The test accuracy was observed to be 100% (17/17 test images correctly classified). On an average the test accuracy is observed to be around 94%.

Now that the model was capable of successful classification on the Leeds Butterfly Dataset, a new species named “Glaucopsyche lygdamus” was added to the dataset. This species includes “Palos Verdes Blue” the world’s rarest butterfly. The Palos Verdes blue is a small endangered butterfly native to the

---

## Phase - 1 
### 2019 - 2020: Selecting a Deep Neural Network for Classification

---

## Project Outcome [2021 Updated]

1.	Website where users can upload images/video feeds and get back the species of the butterfly(s) present.
2.	Trained deep learning model that can recognise different butterfly species, particularly rare ones.

---
## References:
1.	[Monarch Butterflies Migrate 3,000 Miles](https://www.nationalgeographic.com/news/2017/10/monarch-butterfly-migration/)
2.	[Why Are Butterflies Important?](https://sciencing.com/butterflies-important-8749269.html)

---



