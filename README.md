# Virtual-Dermatologist

An automated dermatological diagnostic system using a deep learning. The entire system works on the two mutually dependent steps. The first is preprocessing of the image of that part of the skin that is infected and the latter is used to recognize the disease. The system gives an accuracy of 93.063% while testing on a total of 180 image samples for six disease classes.

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
