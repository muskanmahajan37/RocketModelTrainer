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
- [x] Copy "yolov3-tiny_obj.cfg" from "x64\cfg" file to "x64". We will experiment with it later on.
- [ ] Train custom yolov3 object detector