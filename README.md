# Install Dependencies
sudo apt update
sudo apt install python3-pip git -y

pip3 install --upgrade pip
pip3 install virtualenv
virtualenv yolov_env && source yolov_env/bin/activate

# Install PyTorch (Jetson-compatible)
# Use the wheel from: https://forums.developer.nvidia.com/t/pytorch-for-jetson
pip3 install torch torchvision torchaudio
pip install ultralytics

# Datasets COCO
mkdir -p datasets/coco
cd datasets/coco
wget http://images.cocodataset.org/zips/val2017.zip
wget http://images.cocodataset.org/annotations/annotations_trainval2017.zip
unzip val2017.zip
unzip annotations_trainval2017.zip

# Convert CoCo Anotation
pip install roboflow supervision

# reference 
https://docs.ultralytics.com/guides/nvidia-jetson/#install-pytorch-and-torchvision
