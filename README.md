# Yolo candy detection
Candy detection.
This is a simple guideline for using label studio create datasets for yolo.

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

## Create new project.

Tại màn hình chính (sau khi đã login), chọn Create project.
![Create Project](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/00%20-%20Create%20project%2001.jpeg?token=AGUHJJYAVQD5NIXCOVIT5UDHXU3DM)

## Input porject information

Nhập các thông tin cơ bản của project như Project name, description.
Việc import data và setup label có thể thực hiện sau.
![Input project information](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/00%20-%20Create%20project%2002.jpeg?token=AGUHJJ6RN2EKYMIWWPMR4UTHXU3HM)

## Import image for labeling

Tại màn hình chính, chọn project.
Màn hình project sẽ hiển thị.
Click button import ở góc trên bên trái khu vực hiển thị của project.
![Import image](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/01%20-%20Import%20image%2001.jpeg?token=AGUHJJYY5V5JS2WJGJUSJA3HXU3LU)

## Select image

Màn hình import data đã được hiển thị.
Thực hiện import ảnh qua URL (Label studio sẽ tự động download) hoặc thực hiện upload image thủ công.
![Select image](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/01%20-%20Import%20image%2002.jpeg?token=AGUHJJ3LG7A4HRVXUBTCPMDHXU3M4)
Note: Do cầu hình serve nên số lượng của image có thể sẽ bị giới hạn khi thực hiện import, khuyến khích import 10 image mỗi lần để tránh lỗi.

## Chờ upload image

Quá trình uplaod có thể sẽ mất thời gian.
![Chờ upload image](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/01%20-%20Import%20image%2003.jpeg?token=AGUHJJ5ARJ5RSZGGF7XCXWDHXU3R2)

## Upload image thành công

Hãy chắc chắn rằng tất cả image đều đã được upload.
![Uplaod image thành công](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/01%20-%20Import%20image%2004.jpeg?token=AGUHJJ6FVH2NMZJENS2FEA3HXU3TW)

## Setting labeling

Click button Settings ở góc trên bên trái để vào màn hình settings cho project.
Chọn menu Label interface.
![Setting labeling](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2001.jpeg?token=AGUHJJ43GPMPPUE6SPBIIZLHXU3WK)

## Labeling interface

Click button Browe template
![Labeling interface](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2002.jpeg?token=AGUHJJ45SCEHCVT5O2YRUPDHXU3YE)

## Select template interface

Danh sách các template sẽ được hiển thị, lựa chọn template phù hợp với dự án.
Vì là dự án object detection nên sẽ chọn [Object detection with bounding boxes]
![Select template interface](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2003.jpeg?token=AGUHJJ4OODMCGBTXBA3ENL3HXU33C)

## Default value

Màn hình template hiển thị
![Default value](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2004.jpeg?token=AGUHJJZKKIZO7EXC6CGBOGDHXU35U)

## Custom label list

Xóa các label mặc định và nhập label mong muốn.
![Custom label list](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2005.jpeg?token=AGUHJJYXTITUNUY3DABKXU3HXU35W)

## Project data labeling

Tại màn hình chính của project, có thể thấy danh sách các data của project.
Data có giá trị là 0 là chưa được label.
Và cần thực hiện labeling.
Chọn một data bất kỳ để bắt đầu.
![Project data labeling](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2001.jpeg?token=AGUHJJ6FVC5OBYO3NE37U6LHXU5TI)

## Data labeling

Thực hiện khoanh vùng dữ liệu tương ứng với label.
Chú ý là càng sát thì càng tốt.
Sau khi hoàn thành thì click button submit.
![Data labeling](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/03%20-%20Data%20labeling%2001.jpeg?token=AGUHJJZUYTNHOA4B43JP3QDHXU4CI)

## Project data export

Tại màn hình chính của project, có thể thực hiện export data.
Click button export ở góc trên bên phải khu vực hiện thị của project.
![Project data labeling](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/02%20-%20Data%20labeling%20setting%2001.jpeg?token=AGUHJJ6FVC5OBYO3NE37U6LHXU5TI)

## Export data form training model

Màn hình chọn kiểu dữ liệu của data export.
![Export data for training model](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/04%20-%20Export%20data%2001.jpeg?token=AGUHJJ7YAYMOBUSUWVDGIQTHXU4DY)

# Select YOLO format

Vì là dự án YOLO nên chọn YOLO format.
![Select YOLO format](https://media.githubusercontent.com/media/han48/yolo-candy-detection/main/screen/04%20-%20Export%20data%2002.jpeg?token=AGUHJJ4DQP6UT7SW37GXVH3HXU4HA)

# Training model

```shell
# Unzip YOLO data format ra folder đặt tên là custom_data
unzip data.zip -d custom_data
# Thực hiện phân tách dữ liệu (múc đích để tạo các dữ liệu cho mục đích traning, validation, ... từ bộ data gốc.
# Việc này sẽ tạo ra một folder datasets có đường dẫn trùng với folder hiện tại.
python train_val_split.py --datapath=custom_data --train_pct=0.9
# Thực hiện tạo file data.yaml
# Tệp này thường chứa các thông tin và tham số cần thiết để định nghĩa cách dữ liệu được xử lý và sử dụng trong quá trình huấn luyện.
# Các thông tin cơ bản như: Định nghĩa đường dẫn dữ liệu, Phân loại nhãn, Cấu hình tiền xử lý, Cấu hình huấn luyện
python create_yaml.py
# Sử dụng YOLO11 để training model.
# Có thể thay đổi model tùy ý.
# Lưu ý chỉ số epochs, chỉ số này càng cao thì quá trình training model càng lâu, tuy nhiên tính chính xác của model cũng càng cao.
# Sau khi chạy xong, yolo sẽ tạo ra file model trong thư mục runs/detect/train/weights/best.pt (chú ý là tên folder train có thể thay đổi nếu chạy traning nhiều lần).
yolo detect train data=data.yaml model=yolo11s.pt epochs=60 imgsz=640
# Thử sử dụng model để detect vật thể là kẹo trong các ảnh.
yolo detect predict model=runs/detect/train/weights/best.pt source=../datasets/data/validation/images save=True
```
