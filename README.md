# Virtual-Dermatologist
## DermNet-image-scraper
### DermNet
Dermnet is a publicly available dataset of more than 23000 dermatologist-curated skin disease images. According to this doc, Dermnet organizes the skin diseases biologically in a two-level taxonomy. The bottom-level contains more than 600 skin diseases in a fine-grained granularity. The top-level contains 23 skin disease classes. Each of the top-level skin disease class contains a subcollection of the bottom-level skin diseases.

Overview
This repo keeps the code to fetch water-marked images (relatively low resolution) automatically from DermNet.

In the codes, several helpful modules were used:
* Requests
* Pillow
* BeautifulSoup
* io
* os
* shutil
