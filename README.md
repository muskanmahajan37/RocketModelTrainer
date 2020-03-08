# HPRTracker2
 High Power Rocketry tracker with Python


## Todo

- [x] Uploaded OID4-rocket with Yolov3 notations
- [x] Added script to generate train.txt file,put the output file "train.txt" in "darknet-master\build\darknet\x64\data "folder. 
- [x] Create a "obj" folder inside the folder having "train.txt"
- [x] Add all the images under train\images folder into "darknet-master\build\darknet\x64\data\obj" folder
- [x] Add all the yolov3 labels  txt files in train\label-yolov3 folder into "darknet-master\build\darknet\x64\data\obj" folder
- [x] Create "obj.data" in "\data" folder with 
```
classes = 1
train = data/train.txt
valid = data/test.txt
names = data/obj.names
backup = backup/
```
- [x] Create "obj.names" with "0" inside
- [x] Copy "yolov3-tiny_obj.cfg" from "x64\cfg" file to "x64". We will experiment with it later on.Rename it to "yolov3-tiny-obj.cfg". Modyfying it. 
```
[net]
# Testing
#batch=64
#subdivisions=8
```
filters = number of classes*5 + 3, in my case, 1 = rocket, 1*5+3
```
[convolutional]
size=1
stride=1
pad=1
filters=8
activation=linear
```

- [x]Also it is advised to calculate anchors of training dataset. Therefore, we will do that by opening terminal or cmd and running `darknet_no_gpu.exe detector calc_anchors data/obj.data -num_of_clusters 6 -width 416 -height 416` hit enter and it should compute the anchors. Paste them inside the first yolo layer , like this
```
[yolo]
mask = 3,4,5
anchors = 10,14,  23,27,  37,58,  81,82,  135,169,  344,319
```
. Note: The -cluster is number of pairs, tiny yolo has 6. It can change
- [ ] Train custom yolov3 object detector