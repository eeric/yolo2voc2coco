# yolo2voc2coco
labels: txt-->xml-->json

1.Nanodet project address
https://github.com/RangiLyu/nanodet
2.making labels means
2.1 alfred tool address:
https://github.com/jinfagang/alfred
2.2 download and install
git clone https://github.com/jinfagang/alfred
sudo pip3 install alfred-py #if using python3
sudo pip install alfred-py  #otherwise
3.2 yolo-->voc-->coco
3.2.1 label: txt-->xml
alfred data yolo2voc --image_dir /Path to yours/coco/images/val2017 --text_dir /Path to yours/coco/labels/val2017 --class_file /Path to yours/classes.txt
See the classes.txt file for details.
3.2.2 label: xml-->json
python3 alfred/modules/data/voc2coco.py /Path to yours/valxml /Path to yours/val2017.json
or
alfred data voc2coco --xml_dir /Path to yours/valxml/ --index_1 0 #default annotations_coco.json
valxml: the folder to store xml format of voc label file 
val2017.json: the json format of coco label file
