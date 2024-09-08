# Octree-GS-Ubuntu-Viewer

I modify the origin Octree-GS SIBR viewer cmakefile to make it possible to install and run it on ubuntu, if you want to install it in Windows, please refer to the [origin repository](https://github.com/city-super/Octree-GS/tree/main/SIBR_viewers).

### Hardware Requirements (tested)
- NVIDIA RTX 4070Ti 12G

### Software Requirements (tested)
- Ubuntu 20.04
- CUDA 11.8 (**!!! Test in CUDA 11.8 & 11.6, Failed in 11.7**)
- [Libtorch-2.0-CUDA11.8](https://download.pytorch.org/libtorch/nightly/)
- Python 3.9 in Anaconda virtual environment


### Installation from Local Source
- git clone the repository
- Download the Libtorch with the right CUDA Version(The CUDA Version of Libtorch must be same with the CUDA used in your local environments), and unzip it.
- Follow the below command
    ```
    # Dependencies
    sudo apt install -y libglew-dev libassimp-dev libboost-all-dev libgtk-3-dev libopencv-dev libglfw3-dev libavdevice-dev libavcodec-dev libeigen3-dev libxxf86vm-dev libembree-dev
    # Project setup
    cd SIBR_viewers
    cmake -Bbuild . -DCMAKE_BUILD_TYPE=Release -DCMAKE_PREFIX_PATH="the-path-placed-libtorch/libtorch"     # add -G Ninja to build faster
    cmake --build build -j24 --target install
    ```

- After installation, use the GUI just like the [origin OctreeGS Readme](https://github.com/city-super/Octree-GS)

## Acknowledgement

This repository is a modified version based on SIBR viewers in [Octree-GS](https://github.com/city-super/Octree-GS). Thanks to their great work!
