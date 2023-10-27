<center><h1 style="color:purple; font-family: Georgia, serif; font-weight: bold">Scrape Images from Internet & Train a CV model on these Images</h1></center>

## Tasks
<hr>

#### `Task 1: Data Collection`
Curate a *dataset of 50-100 images* containing cars and buses. To achieve this, you should create a *web scraping* script using tools like Python's Beautiful Soup or Scrapy to collect images from the web (use keywords like- street car or bus).
#### `Task 2: Data Annotation`
After collecting the dataset, annotate the objects in bounding box format. You can use any open-source annotation tools such as Roboflow or LabelImg to manually draw bounding boxes around each car and bus in the images.
#### `Task 3: Data Export`
Export the annotated dataset in a suitable format that can be used for training an object detection model. Common formats include *YOLO format, Pascal VOC format, or COCO format*. The candidate should organise the dataset into *training and validation sets*.
#### `Task 4: Model Training`
Utilise Google Colab to train an object detection model on the annotated dataset. For example, you can choose the popular *YOLO algorithm* for this task. Popular YOLO variants are YOLOv5 - YOLOv8 and fine-tune it on the dataset. Useful Links: YOLOv8 Github, YOLOv8 Colab, YOLOv5 Github, YOLOv5 Doc. 
#### `Task 5: Doucmentation` 
Prepare a brief document that describes the steps taken for each task and results of the training model (hyperparameters used, performance metrics).


## Task files and Folders
<hr>

#### `File 1: data_collection.ipynb`
This file contains the web scraping script which is written using **selenium python**. Script scrape the buses and cars images from internet and saves then into **data/raw_downloaded_images** folder. 
#### `Folder 1: data\raw_downloaded_images`
stores scraped images from internet
#### `File 2: data_augmentation.ipynb`
This file contains python script for augmenting small images. Means written script create new images from old images by rotation, cropping, flipping, controling brightness, contrast etc and saves all the files into **data/augmentad_images** folder.
#### `Folder 2: data\augmented_images`
Stores augmented dataset images
#### `Folder 3: data\annotated_data`
Stores annotation dataset. We used CVAT.ai for data annotations. After annotating dataset we download the dataset in YOLO 1.1 dataset format.
#### `Folder 4: data\processed_data`
Stores processed dataset or final data for model training. In **processed_data** we have two sub-folders named as images and labels. Images folder contains images and labels folder contains .txt file corresponding to each images which records annotations for car and bus. These subdirectories divided into two sub-folders names as train and valid for training purposes and validation purposes respectively.
#### `File 3: data.yaml`
Stores information about dataset for model training
#### `File 4: model_training.ipynb`
This file contains the code for training model on processed custom **annotated dataset**. For training model, we use YOLO algorithm and we used **yolovm.pt** pretrained model.
