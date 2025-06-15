# README
This is a modified version of automatic part segmentation tool for paper [Generalizable Articulated Object Reconstruction from Casually Captured RGBD Videos](https://arxiv.org/abs/2506.08334).

This is an automatic full segmentation  tool based on [Segment-Anything-2](https://github.com/facebookresearch/segment-anything-2) and [Segment-Anything-1](https://github.com/zrporz/segment-anything-1). Our tool performs automatic full segmentation of the video, enabling the tracking of each object and the detection of possible new objects.


## Demo

https://github.com/user-attachments/assets/12fc2c3f-b915-4f58-a492-fc74bbc31e52


https://github.com/user-attachments/assets/f080aab6-12a6-461b-8618-cc25bcf67a9b


https://github.com/user-attachments/assets/ef45b7ee-4d89-4096-87d7-24c273f9dc6e


## Environment Setup
First, clone this repository and submodules
```bash
#SSH
git clone git@github.com:zrporz/AutoSeg-SAM2.git --recursive
```
or
```bash
#HTTPS
git clone https://github.com/zrporz/AutoSeg-SAM2.git --recursive
```



The code requires `python>=3.10`, as well as `torch>=2.3.1` and `torchvision>=0.18.1`
We use [SAM1](https://github.com/zrporz/segment-anything-1) to provide static segmentation results and use the [SAM2](https://github.com/facebookresearch/segment-anything-2) to track the static segmentation results. You can install them by the following commands
```bash
### install sam1 and sam2 modules
cd submodule/segment-anything-1
pip install -e .
cd ../segment-anything-2
pip install -e .
cd ../..
### download checkpoints
cd checkpoints/sam1
bash download.sh
cd ../sam2
bash download.sh
```

## Prepare your data
Please organize your video data as follows
```
|-<video dir>
    |-000001.jpg
    |-000002.jpg
    |-000003.jpg
    |-000004.jpg
    ...
```

or you can use our demo datasets [chickenchicken](https://drive.google.com/file/d/10K_ePOMTjgQhWo1EXbM5aX7IU1EKvsrv/view?usp=sharing) and put it under `videos/chickenchicken`, then run
```bash
bash scripts/chickenchicken.sh
```

## Citation
```bibtex
@software{AutoSeg_SAM2,
  author = {Zrporz},
  title = {AutoSeg-SAM2},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/zrporz/AutoSeg-SAM2},
  version = {Latest}, 
  license = {MIT}, 
  note = {Automated image segmentation tool based on Segment Anything Model (SAM)}
}
```
