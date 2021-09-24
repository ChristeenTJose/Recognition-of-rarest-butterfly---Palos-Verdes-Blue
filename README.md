# Recognition of Rarer Species of Butterflies from images using Artificial Intelligence

## Comparative study conducted by Christeen T Jose

A total 0f 10 different neural network architectures were compared for this project, and some them showed upto 100% accuracy with loss of the order of 10^ (-6).

### The models compared are: 

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

---

### Training Constants:

Batch size for training set: 5

Batch size for validation set: 2

Training set size: 723

Validation set size: 162

Steps per epoch train: 144

Steps per epoch validation: 81

Number of epochs: 120

---

### Testing Constants:

Test set size: 19

Batch size= Test set size

---

## Motivation

Butterflies are particularly sensitive to climate change. Scientists monitor butterflies for warning signs of climate change. 

In addition to being an indicator of climate change, butterflies are also sensitive to other threats such as habitat destruction. Changes in the behaviour of butterflies can warn people of the future effects of habitat loss on other animals.

---

## Methodology

The Leeds Butterfly Dataset available on Kaggle was used for training and testing the CNN model on 10 different species of butterflies. Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. This dataset contains images and textual descriptions for ten categories (species) of butterflies. The image dataset comprises 832 images in total, with the distribution ranging from 55 to 100 images per category. Images were collected from Google Images by querying with the scientific (Latin) name of the species, for example, "Danaus plexippus", and manually filtered for those depicting the butterfly of interest. The textual descriptions for each butterfly category were obtained from the eNature online nature guide. The images in the dataset follow a naming convention of 7 digits, where the first 3 digits are used to indicate the particular species and the remaining 4 digits are for identifying the image within the given species. In the pre-processing phase of deep learning, the images were sorted out into train, validation and test sets each having ten directories (one for each species). The train directory contained 80% of the dataset. The validation and test directories contained 18% and 2% of the dataset respectively. The prepared dataset was fit into a CNN model having 5 convolutional, 5 max pooling and 2 dropout layers. The model has 200,074 trainable parameters. After training the model for 120 epochs, 92% validation accuracy was obtained. The test accuracy was observed to be 100% (17/17 test images correctly classified). On an average the test accuracy is observed to be around 94%.

Now that the model was capable of successful classification on the Leeds Butterfly Dataset, a new species named “Glaucopsyche lygdamus” was added to the dataset. This species includes “Palos Verdes Blue” the world’s rarest butterfly. The Palos Verdes blue is a small endangered butterfly native to the Palos Verdes Peninsula in southwest Los Angeles County, California, United States. As its distribution has been proven to be limited to one single site it has one of the best claims to being the world's rarest butterfly. 72 new images of “Palos Verdes Blue” were downloaded from the internet, cropped and added to the original dataset. As there were now a total of 11 species, “011” was used to indicate “Glaucopsyche lygdamus”, and the model was modified to give 11 outputs in the final dense layer instead of the original 10. The new model had 200,331 trainable parameters.

In order to find the optimal model I applied transfer learning on VGG and Mobilenet models. Mobilenet showed much better performance than other architectures and hence to find out the optimal Mobilenet architecture, I trained multiple Mobilenet models each with a different number of fine-tuned layers.

---

## Results

### Optimal model found: MobileNet (3 Fine Tuned layers)

Test Loss: 1.1293561783531914e-06 

Test Accuracy: 1.0

#### Learning Curves:

![Accuracy VS Epoch](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/7A.png)

![Loss VS Epoch](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/7L.png)

---

### Discussion of results

MobileNet performs better than our hand-built model, VGG16 and VGG19.

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R1.png)

Comparison of Transfer Learnt MobileNet models with varying levels of Fine Tuning:

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R2.png)

Accuracy VS Epoch

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R3.png)

Validation Accuracy VS Epoch

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R4.png)

Loss VS Epoch

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R5.png)

Validation Loss VS Epoch

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R6.png)

MobileNet performs best in our scatter diagram of Test Loss Vs. Test Accuracy out of our hand-built model, VGG16, VGG19 and MobileNet: (Test Accuracy should be maximum and Test Loss should be minimum)

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R7.png)

Comparison among the different MobileNet models:

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R8.png)

After eliminating MobileNet with 1 fine-tuned layer:

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R9.png)

After eliminating MobileNet and MobileNet with 5 fine-tuned layers:

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R10.png)

After eliminating MobileNet with 2 fine-tuned layers and MobileNet with 4 fine-tuned layers:

![](https://github.com/ChristeenTJose/Recognition-of-rarest-butterfly---Palos-Verdes-Blue/blob/master/Images/R11.png)

Thus, our optimum models are MobileNet with 3 fine-tuned layers, and the completely fine-tuned MobileNet model.

---

## Constraints faced during execution:

* Small size of the dataset (50-100 images per species) (solved using Data Augmentation).
* Within certain species, subspecies can have easily distinguishable features; hence they need to be trained separately.
* In case of certain species like Queen Alexandra's birdwing (the world's largest known butterfly species) males and females have different colours and hence need to be separately trained.

---

## Conclusion:

As Model 10 has a possibility of over fitting we can consider Model 7 to be the optimum model.

Since the model was able to successfully recognise Palos Verdes Blue (the rarest butterfly in the world), further advancements in the project involve adding more species of butterflies, particularly endangered and rare ones to the dataset, and finally deploying a real time object recognition model.

---
## References:
1.	[Monarch Butterflies Migrate 3,000 Miles](https://www.nationalgeographic.com/news/2017/10/monarch-butterfly-migration/)
2.	[Why Are Butterflies Important?](https://sciencing.com/butterflies-important-8749269.html)

---

## Citation for Leeds Butterfly Dataset:

Josiah Wang, Katja Markert, and Mark Everingham

Learning Models for Object Recognition from Natural Language Descriptions

In Proceedings of the 20th British Machine Vision Conference (BMVC2009) @InProceedings{Wang09, title = "Learning Models for Object Recognition from Natural Language Descriptions", author = "Josiah Wang and Katja Markert and Mark Everingham", booktitle = "Proceedings of the British Machine Vision Conference", year = "2009" }

---



