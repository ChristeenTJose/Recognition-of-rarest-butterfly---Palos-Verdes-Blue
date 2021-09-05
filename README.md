# Recognition of Rarer Species of Butterflies from images using Artificial Intelligence

Christeen T Jose

---

## Problem Statement [2021 Updated]

Through this project I aim to build a deep learning model capable of recognising the species of a butterfly given an image or video feed, and to deploy the model as an online tool where users can upload their images and get the name of the species back. The project will also include building custom datasets for all the interested species. The dataset will consist of images of butterflies belonging to each of the interested species and will be used to train the neural network for recognition.

---

## Motivation

An abundance of butterflies is often an indication that an ecosystem is thriving. Butterflies are a diverse group of insects containing around 20,000 different species. Each type has various behavioural and structural adaptations that allow them to survive in their environment.

Butterflies are particularly sensitive to climate change. Scientists monitor butterflies for warning signs of climate change. An example of these studies involves monitoring Edith‟s checkerspot butterflies in North America. According to the National Academy of Sciences, the distribution of these butterflies has shifted further north and to higher elevations as the result of an increase in temperature.

Each fall, millions of monarch butterflies (Danaus plexippus) leave their summer breeding grounds in the northeastern U.S. and Canada and travel upwards of 3,000 miles to reach overwintering grounds in southwestern Mexico. But unlike birds or wildebeest that also embark on epic migrations, these individual butterflies will never return. As the days get shorter and the temperatures drop off, monarchs begin to abandon breeding and feeding territories in search of a safe place to spend the winter. For monarchs, that overwintering ground is found high up on just a few mountains in central Mexico. Once there, the monarchs huddle together by the millions on the branches of oyamel fir trees. A rise in avocado plantations taking over native forests has contributed to the monarch's decline.

In addition to being an indicator of climate change, butterflies are also sensitive to other threats such as habitat destruction. Changes in the behaviour of butterflies can warn people of the future effects of habitat loss on other animals.

---

## Methodology

The Leeds Butterfly Dataset available on Kaggle was used for training and testing the CNN model on 10 different species of butterflies. Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. This dataset contains images and textual descriptions for ten categories (species) of butterflies. The image dataset comprises 832 images in total, with the distribution ranging from 55 to 100 images per category. Images were collected from Google Images by querying with the scientific (Latin) name of the species, for example, "Danaus plexippus", and manually filtered for those depicting the butterfly of interest. The textual descriptions for each butterfly category were obtained from the eNature online nature guide. The images in the dataset follow a naming convention of 7 digits, where the first 3 digits are used to indicate the particular species and the remaining 4 digits are for identifying the image within the given species. In the pre-processing phase of deep learning, the images were sorted out into train, validation and test sets each having ten directories (one for each species). The train directory contained 80% of the dataset. The validation and test directories contained 18% and 2% of the dataset respectively. The prepared dataset was fit into a CNN model having 5 convolutional, 5 max pooling and 2 dropout layers. The model has 200,074 trainable parameters. After training the model for 120 epochs, 92% validation accuracy was obtained. The test accuracy was observed to be 100% (17/17 test images correctly classified). On an average the test accuracy is observed to be around 94%.

Now that the model was capable of successful classification on the Leeds Butterfly Dataset, a new species named “Glaucopsyche lygdamus” was added to the dataset. This species includes “Palos Verdes Blue” the world’s rarest butterfly. The Palos Verdes blue is a small endangered butterfly native to the Palos Verdes Peninsula in southwest Los Angeles County, California, United States. As its distribution has been proven to be limited to one single site it has one of the best claims to being the world's rarest butterfly. 72 new images of “Palos Verdes Blue” were downloaded from the internet, cropped and added to the original dataset. As there were now a total of 11 species, “011” was used to indicate “Glaucopsyche lygdamus”, and the model was modified to give 11 outputs in the final dense layer instead of the original 10. The new model had 200,331 trainable parameters.

In order to find the optimal model I applied transfer learning on VGG and Mobilenet models. Mobilenet showed much better performance than other architectures and hence to find out the optimal Mobilenet architecture, I trained multiple Mobilenet models each with a different number of fine-tuned layers.

---

## Results
### Phase 1: (2020) Selecting the optimal neural network architecture for classification

Butterflies are essential to the survival of the ecosystem just like any other animal, but lately there are dying out due to several reasons, and environmental pollution playing a major role. Through this project I made an attempt to build a deep learning model, and particularly the most optimised model that is capable of recognising the world‟s rarest butterfly – „Palos Verdes Blue‟. A total 0f 10 different handbuilt, transfer learnt and fine tuned models were compared for this project, and some them showed upto 100% accuracy with loss of the order of 10^ (-6).

The models compared are: 

Model 1: Hand built keras model

Model 2: VGG16 (Transfer Learning) 

Model 3: VGG19 (Transfer Learning) 

Model 4: MobileNet (Transfer Learning) 

Model 5: MobileNet (FINE TUNING 1 layer) 

Model 6: MobileNet (FINE TUNING 2 layers) 

Model 7: MobileNet (FINE TUNING 3 layers) 

Model 8: MobileNet (FINE TUNING 4 layers) 

Model 9: MobileNet (FINE TUNING 5 layers) 

Model 10: MobileNet (FINE TUNED)

#### Implementation

##### Optimal model found: MobileNet (3 Fine Tuned layers)

##### Constants:

Training:
Batch size for training set: 5
Batch size for validation set: 2
Training set size: 723
Validation set size: 162
Steps per epoch train: 144
Steps per epoch validation: 81
Number of epochs: 120
Testing:
Test set size: 19
Batch size= Test set size




### Phase 2: (2021) Custom object recognition

### Phase 3: (2021) Online tool

---

## Project Outcome [2021 Updated]

1.	Website where users can upload images/video feeds and get back the species of the butterfly(s) present.
2.	Trained deep learning model that can recognise different butterfly species, particularly rare ones.

---
## References:
1.	[Monarch Butterflies Migrate 3,000 Miles](https://www.nationalgeographic.com/news/2017/10/monarch-butterfly-migration/)
2.	[Why Are Butterflies Important?](https://sciencing.com/butterflies-important-8749269.html)

---



