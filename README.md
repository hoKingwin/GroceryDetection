# GroceryDetection
grocery yolov7 object detection

apt-get update
apt-get install git
git clone https://github.com/hoKingwin/GroceryDetection.git

cd GroceryDetection
git clone https://github.com/WongKinYiu/yolov7.git

cd yolov7
wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt

pip3 install -r requirements.txt

<h1>Train</h1>
python train.py --workers 8 --device 0 --batch-size 32 --epochs 100 --img 640 640 --data ../custom_data.yaml --hyp data/hyp.scratch.custom.yaml --cfg ../yolov7-custom.yaml --name yolov7-custom --weights yolov7.pt

<h1>Detect</h1>
python detect.py --weights yolov7_custom.pt --conf 0.5 --img-size 640 --source 1.jpg --view-img --no-trace