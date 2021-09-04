# Iranian Cars Detection using Yolov5

![media_images_Validation](https://github.com/NahidEbrahimian/Iranian-Cars-Detection-using-Yolov5/blob/main/runs/train/exp13/media_images_Validation.jpg)

# Train

1- 

```
git clone https://github.com/ultralytics/yolov5
cd yolov5
pip install -r requirements.txt
```
2- Dataset

```
../Dataset/images/im0.jpg  # image
../Dataset/labels/im0.txt  # label

```
3- Create dataset.yaml

```
# Train/val/test sets as 1) dir: path/to/imgs, 2) file: path/to/imgs.txt, or 3) list: [path/to/imgs1, path/to/imgs2, ..]

path: ../Dataset  # dataset root dir
train: ../Dataset/Train/images  # train images (relative to 'path') 128 images
val: ../Dataset/Val/images  # val images (relative to 'path') 128 images

# Classes
nc: 5  # number of classes
names: ['iranKhodro_dena', 'kia_cerato', 'mazda_3', 'peugeot_206', 'saipa_saina']  # class names
```

You can change this sections in Yolov5/data/coco128.yaml.

4- Train YOLOv5s on Dataset for 30 epochs using folowing command:

```
$ python train.py --img 640 --batch 16 --epochs 30 --data coco128.yaml --weights yolov5s.pt

```
# Inference

```
!python /yolov5/detect.py --weights /runs/train/exp13/weights/last.pt --img 244 --conf 0.4 --source /data/saipa_saina88.jpg
```

