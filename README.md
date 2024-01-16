# AI Cafeteria Price Evaluator
<p>
    <a href="https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator">
        <img src="https://img.shields.io/badge/Demo-HuggingFace-yellow?style=plastic&logo=AirPlay%20Video&logoColor=yellow" alt="HuggingFace">
    </a>
</p>
<img src= git_img/evaluator.jpg width ="80%">


## Introduction
<br/>

In our daily life, the `price evaluation of the cafeteria meals may differ between individual’s point of view`. Therefore, it
might lead to some unfair and awkward situation. To solve this embarrassing problem we decide to develop a model that
can `give the most precised and acceptable pricing` of the meal using computer vision and deep learning techniques. <br/>

There was already a project detecting the price of cafeteria food using YOLOv5. Although YOLOv5 has been a powerful model to in computer vision task, we aim to `reach much higher
accuracy` by finding other object detection model to address the unfair pricing problem to reach a more convincing results.<br/>

Therefore, we choose `YOLOv7 for our model development`, due to the `higher accuracy` and `shorter execution time`.
Our goal is to develop a model capable of delivering accurate identification of cafeteria food item, and determine
the price based on the assigned pricing rule instantly. The model aims to `ensure fairness and consistency in pricing across different instances`
<!--
This project addresses the issue between standard cafeteria pricing and actual charges made by cashiers, highlighting the need for a more precise and transparent pricing system. Our objective is to enhance cafeteria pricing fairness by leveraging an Artificial Intelligence (AI) model, particularly `YOLOv7`. The proposed model aims to reduce inconsistencies in pricing through object detection in real-time, ensure customers are charged appropriate prices for their meal orders.
-->


<!-- We hope to use Yolov7, a powerful object detection model to implement the AI cafteria price evaluator. <br/> -->

Yolov7：https://github.com/WongKinYiu/yolov7/tree/main

<br/>

## Installation
<br/>

You can just clone this repository：<br/>

```
git clone https://github.com/110062306/ML-Final-project.git
```

Setting up environment：<br/>

```
pip install -r requirement.txt
```

## Data preparation
<br/>

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


<a href="https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator">
    <img src="https://img.shields.io/badge/Demo-HuggingFace-yellow?style=plastic&logo=AirPlay%20Video&logoColor=yellow" alt="HuggingFace">
</a> <br/>
<img src="./git_img/demo.gif" width="80%">

You can set up your own model by following steps...<br/>

### Step 1

Clone repository

```
git clone https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator
```

### Step 2

Install requirements

```
cd AI-Cafeteria-Price-Evaluator/
```

```
pip install -r requirements.txt
```

### Step 3

Run the application locally (link will be displayed in the terminal ex. http://127.0.0.1:7860) <br/>
( If you want to use your own model, replace best.py with it. )
```
gradio app.py
```

Check your URL to access the model. <br/>

<img src=git_img/URL.jpg width ="100%">



