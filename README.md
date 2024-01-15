# AI Cafeteria Price Evaluator

<img src= git_img/evaluator.jpg width ="80%">


## Introduction

This project addresses the issue between standard cafeteria pricing and actual charges made by cashiers, highlighting the need for a more precise and transparent pricing system. Our objective is to enhance cafeteria pricing fairness by leveraging an Artificial Intelligence (AI) model, particularly `YOLOv7`. The proposed model aims to reduce inconsistencies in pricing through object detection in real-time, ensure customers are charged appropriate prices for their meal orders.

<!-- We hope to use Yolov7, a powerful object detection model to implement the AI cafteria price evaluator. <br/> -->

Yolov7：https://github.com/WongKinYiu/yolov7/tree/main

## Installation

You can just clone this repository：<br/>

```
git clone https://github.com/110062306/ML-Final-project.git
```

Setting up environment：<br/>

```
pip install -r requirement.txt
```

## Data preparation

### Collecting Data 

We combined images from https://github.com/andywu0913/Chinese-Cafeteria-Food-Recognition/tree/experiencor with photos collected from friends and customers dining at the cafeteria. With these two sources, we could ensure the amount and variety of the data. <br/>

Initial data is available at https://drive.google.com/drive/folders/1hBlf0RE-n4SQvG3TB5R9vAsyc8LkWLCa?usp=drive_link <br/>

Final training data is also available at https://github.com/110062306/ML-Final-project/tree/master/data 

<br/>

### Labeling

A Recommended tool for labeling：[LabelImg](https://github.com/HumanSignal/labelImg) 

<br/>

**Install using python：**

```
pip install labelImg
pip3 install labelImg
```

If this does not work, you can just refer to the link previously provided. <br/><br/>

**Execution：**

```
python labelimg
```

Setting Image directory <br/>

<img src= git_img/opendir.jpg width ="50%">

Setting TXT file storage directory <br/>

<img src= git_img/savedir.jpg width ="50%">

Select the save format (YOLO) <br/><br/>
<img src= git_img/yolo_format.jpg width ="50%">


 
**If you choose the wrong format, we provide a python code to convert format from PascalVOC to YOLO.<br/>**


* assign your `xml path` to `in_file` and `xml_path` parameters in `transfer.py` <br/>
* assign your `txt path` to `out_file` parameter in `transfer.py`

<br/>

Install *lxml* package.

```
pip install lxml
```

Then, use the following code to transfer your label information format.

```
python transfer.py
```



## Training with data

Setting parameters in data.yaml

`train` : training image path<br/>
`val` : validation image path<br/>
`nc` : number of classes<br/>
`names` : name of the corresponding class

<img src=git_img/yaml_parameter.jpg width ="100%">

training instruction 1

```
[training instruction2 --parameter parameter1]
```

training instruction 2

```
[training instruction2 --parameter parameter1]
```

## Model Performance

First outcome <br/>

<br/>

Second outcome <br/>
(image 2)

<br/>

Final outcome <br/>
(image 3)

<br/>

some description of the outcome.....

## Model output examples

(example 1)

(example 2)

## Demo

https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator  <br/>

if you want to set up your own model...<br/>

### Step 1

### Step 2

### Step 3


