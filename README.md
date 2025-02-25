<h1 align="center">🚗 AI-Based Real-Time Illegal Parking Detection with Dynamic Customization of No-Parking Zones  🚫</h1>

## Environment Setup

```bash
conda create -p .venv python==3.10
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
