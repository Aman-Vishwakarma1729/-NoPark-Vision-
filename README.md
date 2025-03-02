<h1 align="center">🚗 AI-Based Real-Time Illegal Parking Detection with Dynamic Customization of No-Parking Zones  🚫</h1>

## Environment Setup

```bash
conda create -p .venv python==3.8
```

```bash
conda activate .venv/
```

```bash
pip install -r requirements.txt
```

## Annotation 

* CVAT (Computer Vision Annotation Tool): Used for annotation pupose.
* It is a free, open-source tool for labeling images and videos.
* Source: https://app.cvat.ai/projects

## Classes 

* Car: All type of **cars** like **Hatchback/Sedan/SUV** and **Vans**
* Motorbike: Scooters/Bikes
* Auto-Rickshaw
* Truck: Small (Tempo) and Big Trucks
* Bus: Small and Big Busses

## Model Details and Setup

* Yolo-v7: As it is opensource
* Source: https://github.com/WongKinYiu/yolov7

```bash
git clone https://github.com/WongKinYiu/yolov7
```

```bash
cd yolov7
```

```bash
pip install -r requirements.txt
```
1) Go through: To create .txt files of image paths ```AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\notebooks\image_path_file_gen.ipynb```

2) Make a copy of ```AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7\data\coco.yaml``` rename it in my case ```no_park_vision_ver-1.yaml```.

3) Make sure to update paths of files created in ```step (1)``` with number of classes ```nc``` and class names ```names``` in  ```no_park_vision_ver-1.yaml``` file.

4) In ```AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7\cfg\training``` folder choose the model to train in my case ```AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7\cfg\training\yolov7.yaml``` make copy of it in my case ```no_park_vision_ver-1_yolov7.yaml```.

5) Update the number of classes ```nc``` in ```no_park_vision_ver-1_yolov7.yaml```.

6) Download the .pt file of pretrained model of the configuration that one have choose for training here we choose ```yolov7.pt``` that  from official git-hub repository.

7) Training ```p5``` model.

8) For Training yolov7:
```bash
python D:\VIT\Cap-Stone\AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7\train.py --workers 4 --device cpu --batch-size 2 --data D:\VIT\Cap-Stone\AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\no_park_vision_ver-1.yaml --img 640 640 --cfg D:\VIT\Cap-Stone\AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\no_park_vision_ver-1_yolov7.yaml --weights D:\VIT\Cap-Stone\AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7.pt --name yolov7_ver-1_100_epochs --hyp D:\VIT\Cap-Stone\AI_Based_Real-Time_Illegal_Parking_Detection_with_Dynamic_Customization_of_No-Parking_Zones\yolov7\data\hyp.scratch.p6.yaml --cache-images --epochs 100
```