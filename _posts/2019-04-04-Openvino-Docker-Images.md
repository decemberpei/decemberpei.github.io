---
layout: post
---
# 下面是OpenVINO的Docker镜像，里面已经下载好所有的模型
1. 基于Docker官方的Ubuntu:16.04 build
2. 安装了Openvino对应的release
3. 编译了samples
4. 下载好了所有的模型（model_downloader.py --all）
5. bashrc里设置好了openvino和mediasdk的环境变量
6. Image已经配置好了CPU/GPU/NCS2，可以用这三种设备进行推理

# 镜像使用方法：
1. 从阿里云拉取Image

```
$ sudo docker pull registry.cn-qingdao.aliyuncs.com/openvino/workshop:[image_tag]
```

2. 创建container：

```
$ docker create --name [container_name] --net=host -it -e DISPLAY=$DISPLAY --privileged -v /dev:/dev registry.cn-qingdao.aliyuncs.com/openvino/workshop:[image_tag]
```

3.给与docker container访问主机display的权限(否则docker container里面的应用无法输出图像到显示设备)：

```
$ xhost +local:docker
```

4. 启动container并进入

```
$ docker start [container_name]
$ docker attach [container_name]
# 多按一次回车，此时以root身份进入container的shell
```

如果对Docker不熟悉，可以参考[这里](https://github.com/decemberpei/OpenVINO-Docker-Howto)

# 镜像列表（建议用最新版本）

OpenVINO版本|Image Tag|Docker地址
---|:--:|---:
2019r1|2019r1|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2019r1
2018r5.0.1|2018r5.0.1|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2018r5.0.1
2018r5|2018r5|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2018r5
2018r3|pure-r3_model-downloader|registry.cn-qingdao.aliyuncs.com/openvino/workshop:pure-r3_model-downloader
