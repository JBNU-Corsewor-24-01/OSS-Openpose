# OSS-Openpose

# Please refer to https://github.com/CMU-Perceptual-Computing-Lab/openpose.git

# OpenPose CPU Version Setup and Example Execution

## Introduction
This project demonstrates how to set up the CPU version of OpenPose using CMake. OpenPose is a library for real-time multi-person keypoint detection. We will guide you through the installation process and show you how to run an example to verify your setup.

## Prerequisites
- A system with a compatible CPU.
- Install CMake (version 3.10 or higher).
- Install Git.
- Install the necessary build tools (e.g., Visual Studio on Windows, GCC on Linux).

## Installation Guide

### Step 1: Install Dependencies
#### On Ubuntu
```bash
sudo apt-get update
sudo apt-get install -y build-essential cmake git libopencv-dev
```

#### On Windows
- Download and install [CMake](https://cmake.org/download/).
- Install Visual Studio with C++ development tools.

### Step 2: Clone the OpenPose Repository
```bash
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose.git
cd openpose
```

### Step 3: Configure the Build with CMake
```bash
# Create a build directory
mkdir build
cd build

# Configure the project with CMake
cmake .. -DBUILD_PYTHON=OFF -DBUILD_EXAMPLES=ON -DUSE_CAFFE=OFF -DUSE_CUDA=OFF
```

### Step 4: Build OpenPose
```bash
# Compile the project
cmake --build . --config Release
```

### Step 5: Download OpenPose Models
```bash
# Navigate to the models directory
cd ../models

# Download the required models
bash getModels.sh
```

## Running an Example
### Step 1: Navigate to the Build Directory
```bash
cd ../build
```

### Step 2: Run the OpenPose Demo
```bash
# On Ubuntu
./examples/openpose/openpose.bin --image_dir ../examples/media/ --face --hand

# On Windows
.\examples\openpose\Release\openpose.exe --image_dir ..\examples\media\ --face --hand
```

This command runs OpenPose on the sample images provided in the `examples/media/` directory and includes face and hand keypoint detection.

## Troubleshooting
- Ensure all dependencies are installed correctly and their paths are properly set.
- If you encounter build errors, verify that you have the correct versions of CMake and other tools.

## Conclusion
By following this guide, you should have a functional setup of the CPU version of OpenPose. You can use this setup to experiment with real-time keypoint detection and integrate OpenPose into your projects.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
