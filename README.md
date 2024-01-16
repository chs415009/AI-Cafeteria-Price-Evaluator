# AI Cafeteria Price Evaluator
<p>
    <a href="https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator">
        <img src="https://img.shields.io/badge/Demo-HuggingFace-yellow?style=plastic&logo=AirPlay%20Video&logoColor=yellow" alt="HuggingFace">
    </a>
</p>
<img src= git_img/evaluator.jpg width ="80%">


## Introduction

In our daily life, the price evaluation of the cafeteria meals may differ between individual’s point of view. Therefore, it
might lead to some unfair and awkward situation. To solve this embarrassing problem we decide to develop a model that
can `give the most precised and acceptable pricing of the meal based on student restaurants in Taiwan` using computer vision and deep learning techniques. <br/>

Although a project detecting the price of cafeteria food using YOLOv5, which is a powerful model for computer vision task, has existed, we aim to reach a higher
accuracy by creating another object detection model to address the pricing problem with a more convincing results.<br/>

In our project, we choose `YOLOv7 for our model development`, for its `higher accuracy` and `shorter execution time`.
We aim to develop a model capable of delivering accurate identification of cafeteria food ite as well as determine
the price based on the assigned pricing rule to `ensure the consistency in pricing among different instances`
<!--
This project addresses the issue between standard cafeteria pricing and actual charges made by cashiers, highlighting the need for a more precise and transparent pricing system. Our objective is to enhance cafeteria pricing fairness by leveraging an Artificial Intelligence (AI) model, particularly `YOLOv7`. The proposed model aims to reduce inconsistencies in pricing through object detection in real-time, ensure customers are charged appropriate prices for their meal orders.
-->


<!-- We hope to use Yolov7, a powerful object detection model to implement the AI cafteria price evaluator. <br/> -->

Yolov7：https://github.com/WongKinYiu/yolov7/tree/main

<br/>

## Installation

Clone the repository：<br/>

```
git clone https://github.com/110062306/ML-Final-project.git
```

Setting up environment：<br/>

```
pip install -r requirement.txt
```
<br/>

## Data Preparation

### Collecting Data 

We collected photos from students dining at the cafeteria. To ensure the amount and variety of the data,we also combined our data with images from [GitHub resource](https://github.com/andywu0913/Chinese-Cafeteria-Food-Recognition/tree/experiencor). <br/>

Initial data is available at the link below: <br/>
https://drive.google.com/drive/folders/1hBlf0RE-n4SQvG3TB5R9vAsyc8LkWLCa?usp=drive_link <br/>

Final training data is also available at the link below: <br/>
https://github.com/110062306/ML-Final-project/tree/master/data <br/>

<br/>

### Labeling

Tool for labeling data：[LabelImg](https://github.com/HumanSignal/labelImg) 

<br/>

**Installation using Python：**

```
pip install labelImg
pip3 install labelImg
```

If this does not work, please refer to the link [LabelImg](https://github.com/HumanSignal/labelImg). <br/>

<br/>

**Execution：**

```
python labelimg
```

1. Setting Image directory 

<img src= git_img/opendir.jpg width ="50%">

<br/>

2. Setting txt file storage directory 

<img src= git_img/savedir.jpg width ="50%">

<br/>

3. Select the save format (YOLO) 
<img src= git_img/yolo_format.jpg width ="50%">

<br/>

**If you choose the wrong format, here is a method for converting format from PascalVOC to YOLO.<br/>**

* assign your `xml path` to `in_file` and `xml_path` parameters in `transfer.py` <br/>
* assign your `txt path` to `out_file` parameter in `transfer.py`

Install *lxml* package.

```
pip install lxml
```

Then, use the following code to transfer your label information format.

```
python transfer.py
```

<br/>

## Training with Data

Setting parameters in data.yaml

`train` : training image path<br/>
`val` : validation image path<br/>
`nc` : number of classes<br/>
`names` : name of the corresponding class

<img src=git_img/yaml_parameter.jpg width ="100%">

<br/>

Training part:

```
!python train.py --device 0 --batch-size 16 --epochs 300 --img 640 640 --data data/final-data.yaml --hyp data/hyp.scratch.custom.yaml --cfg cfg/training/yolov7-custom.yaml --weights yolov7.pt --name yolov7-custom --resume
```

Prediction part:

```
!python detect.py --weights runs/train/yolov7-custom/weights/best.pt --conf 0.5 --img-size 640 --source 2023_11_7_31_jpg.rf.6fb4c4d8af597cab0a6663f65df50ab9.jpg --no-trace
```

<br/>

## Model Performance

First version:

<img src= git_img/MP1.png width ="50%">

In the first version, we can observe that there are a lot of different classes, but we don’t have enough data to recognize each type of meal. As a result, the outcome of the confusion matrix is not ideal.

<br/>

Second version:

<img src= git_img/MP2.png width ="50%">

In the second version, we reduced the number of classes by combining all side dishes into one class called "side dish" and grouped main meals based on their prices, categorizing into "25 dollar meal", "30 dollar meal", and "40 dollar meal". After applying changes, a notable improvement in the confusion matrix has shown in the figure.

<br/>

Final version: <br/>
In the final version, we adjusted the iteration by stopping training when the model's loss no longer decreased for 5 consecutive epochs. As Fig. shown, it performed much better compared to previous models.

<br/>

<br/>

## Model Output

Fig.1 example:

Fig.2 example:

In Fig.1 and Fig.2, the left side shows the original input image, the upper right side shows the output image and lower right side shows the corresponding price. The output (image and price) can be obtained in real-time, and we use Hugging Face Spaces as the demo platform.

<br/>

## Demo

<a href="https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator">
    <img src="https://img.shields.io/badge/Demo-HuggingFace-yellow?style=plastic&logo=AirPlay%20Video&logoColor=yellow" alt="HuggingFace">
</a> <br/>
<img src="./git_img/demo.gif" width="80%">

<br/>

## Set Up Your Model

1. Clone repository

```
git clone https://huggingface.co/spaces/mamechin/AI-Cafeteria-Price-Evaluator
```

2. Install requirements

```
cd AI-Cafeteria-Price-Evaluator/
pip install -r requirements.txt
```

3. Run the application locally

```
gradio app.py
```
_Link will be displayed in the terminal ex. http://127.0.0.1:7860.<br/>
If you want to use your own model, replace best.pt with it._

<br/>

4. Check URL to access the model

<img src=git_img/URL.jpg width ="100%">



