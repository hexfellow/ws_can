[中文](README-CN.md) | [English](README.md)
---

# 概述
这是一个可以实现socketcan和websocket相互转换的一个工具。

# 使用方法
## 服务端
假设你需要将`hexcan0`发布到`0.0.0.0:8000`，示例如下：
```
./wscan hexcan0 listen 0.0.0.0 8000
```

## 客户端
首先你需要创建一个vcan，用于提供本地socketcan服务。以`vcan0`为示例：
```
ip link add vcan0 type vcan && sudo ip link set vcan0 up
```
注意，该指令可能需要`sudo`。

然后将创建的`vcan0`连接到服务端的地址上。以地址为`0.0.0.0`，端口为`8000`为例：
```
./wscan vcan0 connect ws://0.0.0.0:8000
```
