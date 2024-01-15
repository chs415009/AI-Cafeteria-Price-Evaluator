# AI Cafeteria Price Evaluator

## Introduction
We hope to use Yolov7, a powerful object detection model to implement the AI cafteria price evaluator. <br/>

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

Our training data is also available at https://github.com/110062306/ML-Final-project/tree/master/data .

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

Setting Image directory (image 1)<br/>

Setting XML file storage directory (image 2)<br/>

Select the save format (YOLO) (iamge 3)<br/><br/>
 
**If you choose the wrong format, we provide a python code to convert format from PascalVOC to format YOLO.<br/>**

First, set up your xml/txt path to in_file/out_file parameter, respectively, in convert_annotation function of transfer.py <br/>

Then, use the following code to transfer your label information format.

```
python transfer.py
```



## Training with data

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
(image 1)

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


