[中文](README-CN.md) | [English](README.md)
---

# Overview
This is a tool that can achieve mutual conversion between socketcan and websocket.

# Usage
## Server
Assuming you need to publish `hexcan0` to `0.0.0.0:8000`, the example is as follows:
```
./wscan hexcan0 listen 0.0.0.0 8000
```

## Client
First, you need to create a vcan to provide local socketcan service. Using `vcan0` as an example:
```
ip link add vcan0 type vcan && sudo ip link set vcan0 up
```
Note that this command may require `sudo`.

Then connect the created `vcan0` to the server address. Using address `0.0.0.0` and port `8000` as an example:
```
./wscan vcan0 connect ws://0.0.0.0:8000
```

