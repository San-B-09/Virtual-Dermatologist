# Virtual-Dermatologist

An automated dermatological diagnostic system using a deep learning. The entire system works on the two mutually dependent steps. The first is preprocessing of the image of that part of the skin that is infected and the latter is used to recognize the disease. The system gives an accuracy of 93.063% while testing on a total of 180 image samples for six disease classes.

**The complete research paper can be found here:** https://link.springer.com/chapter/10.1007/978-3-030-48118-6_6#citeas

## DermNet-image-scraper
### DermNet
Dermnet is a publicly available dataset of more than 23000 dermatologist-curated skin disease images. According to this doc, Dermnet organizes the skin diseases biologically in a two-level taxonomy. The bottom-level contains more than 600 skin diseases in a fine-grained granularity. The top-level contains 23 skin disease classes. Each of the top-level skin disease class contains a subcollection of the bottom-level skin diseases.

**Overview**

`dermnet_scraping.ipynb` keeps has code to fetch water-marked images (relatively low resolution) automatically from DermNet.

In the codes, several helpful modules were used:
* [Requests](https://requests.readthedocs.io/en/master/)
* [Pillow](https://pillow.readthedocs.io/en/3.1.x/reference/Image.html)
* [BeautifulSoup](https://pillow.readthedocs.io/en/3.1.x/reference/Image.html)
* [io](https://docs.python.org/3/library/io.html)
* [os](https://docs.python.org/3/library/os.html)
* [shutil](https://docs.python.org/3/library/shutil.html)

Following flow diagram describe brief overview of dermnet scraper:
![Dermnet_Scraper](https://github.com/San-B-09/Virtual-Dermatologist/blob/master/Images/dermnet-scraper.png)

## Classification Pipeline
### Brief Overview of System
The proposed methodology, depicted in following figure is based on two primary parts, Image pre-processing unit and a Classifier unit. The image processor unit will augment the sample/image and then the image will be segmented into different segments. Then the image will be sent to the convolutional classifier for feature extraction and further classification.

- **Image Processing Unit**: This unit focuses on the affected part by converting the image into an RGB form. Extracting feature extraction being a major step in the classification problem, they are the core of the image classification problem. So, both the training and the testing image are resized into proper format before sending it to the classifier unit. Furthermore, all the training images are passed through the rotational and positional invariant i.e. they are shifted vertically or horizontally to right or left, rotated clockwise or anti-clockwise by 10% or scaled in or out, thus sustaining the process of efficiently training of the model.

-	**Classification Unit**: This unit classifies the images into pre-defined classes using a convolutional neural network algorithm and SoftMax classifier for multi-class classification.

`skin_disease_classification.ipynb` contains following functions:
- `load_unique()` - It loads all the unique labels for loading data
- `plot_image()` - Prints any image present in dataset
- `load_data()` - loads all the images and their respective labels and split the data into training and testing set
- `create_model()` - CNN architecture is defined here
- 'plot_accuracy() & plot_loss()' - These functions plot the accuracy and loss curve

In further code, confusion matrix is visualized in the form of heatmap and model is saved in tflite format to be used in aandroid applicaiton as well

## Results
This research comprises of six diagnosis classes as mentioned above. We've successfully achieved an accuracy of 93.063% on a testing dataset containing a total of 180 images of six different classes. Also, the loss function plot shown in `skin_disease_classification.ipynb` states the avoidance of overfitting throughout the training. The AUC score obtained from training is 0.841664.
