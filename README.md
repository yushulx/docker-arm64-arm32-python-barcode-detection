# Docker ARM64 and ARM32 Images for Python Barcode Detection
The repository demonstrates how to use Dynamsoft Barcode Reader Python Edition in a ARM64 or ARM32 Docker container.

## How to Build Docker Images for ARM64 and ARM32

```bash
docker run --rm --privileged multiarch/qemu-user-static:register --reset
docker build --platform linux/arm64 -f DockerfileArm64 -t <IMAGE-NAME> .
docker build --platform linux/arm/v7 -f DockerfileArm32 -t <IMAGE-NAME> .  
```

## How to Run the Python Barcode detection in a Docker container

```bash
docker run --platform linux/arm64 -it --rm -v ${pwd}:/usr/src/myapp -w /usr/src/myapp <IMAGE-NAME> python pillow_test.py
docker run --platform linux/arm/v7 -it --rm -v ${pwd}:/usr/src/myapp -w /usr/src/myapp <IMAGE-NAME> python pillow_test.py
```

**Try the Pre-built Images**

```bash
docker run --platform linux/arm64 -it --rm -v ${pwd}:/usr/src/myapp -w /usr/src/myapp yushulx/dbr-arm64:1.0 python pillow_test.py
docker run --platform linux/arm/v7 -it --rm -v ${pwd}:/usr/src/myapp -w /usr/src/myapp yushulx/dbr-arm32:1.0 python pillow_test.py
```

## Raspberry Pi Emulator
Try [dockerpi](https://github.com/lukechilds/dockerpi) to evaluate the Python barcode SDK performance on Raspberry Pi.

```bash
docker run -it lukechilds/dockerpi pi2
docker run -it lukechilds/dockerpi pi3
```