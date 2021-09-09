
# Detection of faulty parts

An object detection model was created, which detects the errors in the metal parts produced in this repository and the places where the errors are found. In the study using the pre-trained model, 99% accurate detection was achieved.

## Files


|                |Files|                         |
|----------------|-------------------------------|-----------------------------|
|[images](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/tree/main/images "images")|`Folder with sample printouts`                        
|[preprocessing](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/tree/main/preprocessing "preprocessing")         |`scripts used in preprocessing"` 
|[exporter_main_v2.py](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/exporter_main_v2.py "exporter_main_v2.py")|`script that makes the model ready for use`                        
|[model_main_tf2.py](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/model_main_tf2.py "model_main_tf2.py")        |`script to train our model"` 
|[tf_image.py](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/tf_image.py "tf_image.py")|`script where we run our model`                        
|[xml_to_csv.py](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/xml_to_csv.py "xml_to_csv.py")          |`Script to convert xml files to csv"` 
|[data](https://github.com/Onurryilmazz/Object-Detection-Faulty-Production-detection/tree/main/data "data")|`Folder with data` 

> Note: : I used Tensorflow's Object Detection API to perform object detection on images.


## Model and Data

- Data : Photos with damaged parts that may occur in the production of metal parts.
- pre-trained model : Faster rcnn resnet50
- data labeling : LabelImg

## TensorFlow Object Detection API Setup

  
I used tensorflow object detection api to train my model. I did this by installing the tensorflow model github repo in the file directory where my project is located
```
 git clone https://github.com/tensorflow/models.git
 ```

## COCO API Setup

As of TensorFlow 2.x, the pycotools package is listed as a support files of the Object Detection API. For this, it is necessary to perform its installation.

```
pip install cython
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```
## Dataset preparation
The data are available to us unlabeled. First I tagged them using LabelImg. Then, each photo had a location information in xml form. I converted them to tfrecord format so we can use them in our model. For this, I used the generate_tf_record script in the preprocessing file. (conversion to csv format is possible with xml_to_csv in the home directory)

## Training 
Link of all available models : https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md

I downloaded the files of the model I will use from the link I gave. Then, after creating my own model files, I rearranged the config file of the pre-trained model to suit my problem. (number of classes, paths, etc.) then I trained my model.

## Results
![Result1](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/images/1.png)

![Result2](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/images/2.png)

![Result3](https://github.com/Onurryilmazz/object-detection---faulty-production-detection/blob/main/images/3.png)

