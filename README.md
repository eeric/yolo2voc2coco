# yolo2voc2coco
labels: txt-->xml-->json

This project support to Nanodet project to make official labels.

## 1.Nanodet project address

https://github.com/RangiLyu/nanodet

## 2.making labels means

### 2.1 alfred tool address

https://github.com/jinfagang/alfred

### 2.2 download and install

git clone https://github.com/jinfagang/alfred

sudo pip3 install alfred-py #if using python3

sudo pip install alfred-py  #otherwise

#### 2.2.3 yolo-->voc-->coco

##### 2.2.3.1 label: txt-->xml

alfred data yolo2voc --image_dir /Path to yours/coco/images/val2017 --text_dir /Path to yours/coco/labels/val2017 --class_file /Path to yours/classes.txt

or

python3 alfred/modules/data/yolo2voc /Path to your image_dir /Path to your text_dir /Path to your class_file

See the classes.txt file for details, particular attention as below:

such as 'traffic light' category, not same as 'traffic_light' category in nanodet/config/nanodet-m.yml

##### 2.2.3.2 label: xml-->json

python3 alfred/modules/data/voc2coco.py /Path to yours/valxml /Path to yours/val2017.json

or

alfred data voc2coco --xml_dir /Path to yours/valxml/ --index_1 0 #default annotations_coco.json

valxml: the folder to store xml format of voc label file 

val2017.json: the json format of coco label file

#### voc2coco.py: add pre-define category, be sure the labels match.
### Multi class label change to one category label
modified voc2coco.py, made other category object bbox not write,as following:

in voc2coco.py
    
    new_id = len(categories)+1 if index_1 else len(categories)
    
    categories[category] = new_id

Remove above 2 lines and replace them with continue.

#### Negative sample
image and label
1.both names needs to be the same;
2.the label file content is empty.

## If I can help you, please give me a star :star2: :star2: :star2:
my csdn: https://blog.csdn.net/yyqq7226741/article/details/110426728
