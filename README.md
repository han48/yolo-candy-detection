# yolo-candy-detection
Candy detection

# Create env

```shell
python3 -m venv env
source env/bin/activate
```

# PIP install

```shell
pip install -U label-studio
pip install ultralytics
pip install torch torchvision torchaudio
```

# Label studio

```shell
label-studio
```

# Training model

```shell
unzip data.zip -d custom_data
python train_val_split.py --datapath=custom_data --train_pct=0.9
python create_yaml.py
yolo detect train data=data.yaml model=yolo11s.pt epochs=60 imgsz=640
yolo detect predict model=runs/detect/train/weights/best.pt source=data/validation/images save=True
```