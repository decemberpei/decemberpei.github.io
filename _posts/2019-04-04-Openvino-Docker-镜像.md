---
layout: post
---
# 下文是OpenVINO的Docker镜像，镜像里已经下载好所有的模型
1. 基于Docker官方的Ubuntu:16.04 build
2. 安装了Openvino对应的release
3. 编译了samples
4. 下载好了所有的模型（model_downloader.py --all）
5. bashrc里设置好了openvino和mediasdk的环境变量
6. 做好了CPU/GPU/NCS2的相关配置，创建container就可以用这三种设备进行推理

# 镜像使用方法：
1. 从阿里云拉取Image

```
$ sudo docker pull registry.cn-qingdao.aliyuncs.com/openvino/workshop:[image_tag]
```

2. 创建container：

```
$ docker create --name [container_name] --net=host -it -e DISPLAY=$DISPLAY --privileged -v /dev:/dev registry.cn-qingdao.aliyuncs.com/openvino/workshop:[image_tag]
```

3.给与docker container访问主机display的权限(否则container里面的应用无法输出图像到主机的显示器)：

```
$ xhost +local:docker
```

4. 启动container并进入

```
$ docker start [container_name]
$ docker attach [container_name]
# 多按一次回车，此时以root身份进入container的shell
```

如果读者还没有安装Docker，可以参考[这里](https://docs.docker.com/install/linux/docker-ce/ubuntu/)的步骤安装

# 镜像列表（建议总是使用最新版本）

OpenVINO版本|Image Tag|Docker仓库地址
---|:--:|---:
2019r1|2019r1|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2019r1
2018r5.0.1|2018r5.0.1|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2018r5.0.1
2018r5|2018r5|registry.cn-qingdao.aliyuncs.com/openvino/workshop:2018r5
2018r3|pure-r3_model-downloader|registry.cn-qingdao.aliyuncs.com/openvino/workshop:pure-r3_model-downloader
