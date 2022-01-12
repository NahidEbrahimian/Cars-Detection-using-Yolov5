# Iranian Cars Detection using Yolov5

![media_images_Validation](https://github.com/NahidEbrahimian/Iranian-Cars-Detection-using-Yolov5/blob/main/runs/train/exp13/media_images_Validation.jpg)

# Instalation

1- Clone this repository using the following command:

```
https://github.com/NahidEbrahimian/Cars-Detection-using-Yolov5.git
```

2- In ```./Cars-Detection-using-Yolov5``` directory, run the following command to install requirements:

```
!pip install -U -r requirements.txt
```

#

# Dataset

Dataset contains 2100 images of the cars in five categories.

Datast link: [iranians cars](https://drive.google.com/drive/folders/1k_uzXzDyjEQ0cFYlFJaNbZpPg0TMHXCZ?usp=sharing)

```
../Dataset/images/im0.jpg  # image
../Dataset/labels/im0.txt  # label

```
#

# Train

1- Clone this repository using the following command:

```
https://github.com/NahidEbrahimian/Cars-Detection-using-Yolov5.git
```

2- In ```./Cars-Detection-using-Yolov5``` directory, run the following command to install requirements:

```
!pip install -U -r requirements.txt
```

3- For training, in ```./Cars-Detection-using-Yolov5``` directory, train YOLOv5s on Dataset for 30 epochs using following command:

```
!python train.py --img 640 --batch 8 --epochs 30 --data data/coco128.yaml --weights yolov5s.pt
```

- For train on your dataset, you must creat dataset.yaml file.

```
# Train/val/test sets as 1) dir: path/to/imgs, 2) file: path/to/imgs.txt, or 3) list: [path/to/imgs1, path/to/imgs2, ..]

path: ../Dataset  # dataset root dir
train: ../Dataset/Train/images  # train images (relative to 'path') 128 images
val: ../Dataset/Val/images  # val images (relative to 'path') 128 images

# Classes
nc: 5  # number of classes
names: ['iranKhodro_dena', 'kia_cerato', 'mazda_3', 'peugeot_206', 'saipa_saina']  # class names
```
You can change this sections in ```.data/coco128.yaml```.

#

# Inference

For inference, in ```./Cars-Detection-using-Yolov5``` directory, run the following command.

```
!python inference.py --weights runs/train/exp13/weights/last.pt --img 244 --conf 0.4 --source inputs/iranKhodro_dena26.jpg
```
#

# Test

For test, in ```./Cars-Detection-using-Yolov5``` directory, run the following command. you must set your test data path in `coco128.yaml` file that prepared in Train step.

```
!python val.py --data coco128.yaml --weightsruns/train/exp13/weights/last.pt --img 640
```

