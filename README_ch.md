[English](README.md)|简体中文

# DoFaker: 一个简单易用的换脸工具
基于insightface开发，可以轻松替换视频或图片中的人脸。

<p align="center">
<img src="https://github.com/justld/dofaker/blob/main/docs/images/source.gif" width="300" height="150"><img src="https://github.com/justld/dofaker/blob/main/docs/images/trump.jpg" width="300" height="150">
</p>

<p align="center">
<img src="https://github.com/justld/dofaker/blob/main/docs/images/swapped.gif" width="600" height="300"/>
</p>

# 视频教程
[B站视频使用教程](https://www.bilibili.com/video/BV1b8411i7A8/)


# 快速开始
克隆代码，安装dofaker
```bash
git clone https://github.com/justld/dofaker.git
cd dofaker
conda create -n dofaker
pip install -e .
```
打开web服务（权重自动下载）:
```bash
dofaker
```


# 安装
对于GPU用户（您需要自行安装好cuda环境），使用'requirements_gpu.txt'替代下列命令行中的'requirements.txt'。

## conda install
创建conda虚拟环境:
```bash
git clone https://github.com/justld/dofaker.git
cd dofaker
conda create -n dofaker
conda activate dofaker
pip install -r requirements.txt
```

## pip install
```bash
git clone https://github.com/justld/dofaker.git
cd dofaker
pip install -r requirements.txt
```

# 二、Download Weight
所有的权重来自[insightface](https://github.com/deepinsight/insightface), 您也可以在链接[google drive](https://drive.google.com/drive/folders/1R6yMDQiHQg938M5GIz4_mOOhpF8ybrv9?usp=sharing)或 [baidu drive(extract code:tkf3)](https://pan.baidu.com/s/1sF3QbwAK1sVqdie1KqgkkA)中下载。

解压下载好的权重文件，目录结构如下所示:
```
|-dofaker
|-docs
|-weights
----|-models
--------|-buffalo_l
----------|-1k3d68.onnx
----------|-2d106det.onnx
----------|-...
--------|-buffalo_l.zip
--------|-inswapper_128.onnx
|-run.py
|-web_ui.py
```


# 三、使用
您可以以web或命令行的方式进行使用
## web ui
web使用方式只支持单个人脸替换，同时替换多个人脸请使用命令行的方式：
```bash
python web_ui.py
```

## command
命令行的使用方法支持一次性多个人脸替换：
```bash
python run.py --source "image or video path to be swapped" --dst_face_paths "dst_face1_path" "dst_face2_path" ... --src_face_paths "src_face1_path" "src_face2_path" ...
```

以下的命令会使用src_face1和src_face2替换视频input_video.mp4中的dst_face1和dst_face2 ：
```bash
python run.py --source input_video.mp4 --dst_face_paths dst_face1.jpg dst_face2.jpg --src_face_paths src_face1.jpg src_face2.jpg
```

|参数|说明|
|:---:|:---:|
|source|需要替换人脸的图片或视频|
|dst_face_paths|待替换的图片或视频中的目标人脸路径，如果为None，待替换的图片和视频中的所有人脸都被替换为src_face|
|src_face_paths|新的人脸图片路径，用于替换目标图片或视频|


# 声明
禁止将本软件用于违反法律、道德，侵权等场合，本软件仅供学习用途，使用本软件造成的一切后果由使用者承担。

# 赞助
[您的支持是我们持续开发的动力](https://justld.github.io/)

# Thanks
[insightface](https://github.com/deepinsight/insightface)