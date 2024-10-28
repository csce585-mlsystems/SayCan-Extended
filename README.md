# SayCan-Extended

Extending PaLM SayCan: Enhancing language-driven robotic task planning and execution

## Overview
This project extends the original [SayCan](https://say-can.github.io/) robotic task planning framework. It integrates large language models with robotic affordances for improved long-horizon task planning and execution.

## Setup & Installation

1. Create and activate a conda environment:
```bash
conda create -n saycan python=3.8
conda activate saycan
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Required Assets
The project will automatically download necessary assets on first run:
- UR5e robot URDF files
- Robotiq 2F-85 gripper files
- Bowl assets
- ViLD pretrained model weights

## Environment
- PyBullet simulation environment with:
  - UR5e robotic arm
  - Robotiq 2F-85 gripper
  - Various manipulatable objects (blocks, bowls)
  - Top-down and perspective cameras

## Key Components
- **Vision Module**: ViLD (Vision-Language Detection) for zero-shot object detection
- **Language Module**: GPT-3 for task planning and decomposition
- **Manipulation Module**: CLIPort variant for pick and place actions

## Usage
Run the main notebook `SayCan-Robot-Pick-Place.ipynb` to:
- Set up the simulation environment
- Run object detection
- Execute language-guided robotic tasks

## Hardware Requirements
- CUDA-capable GPU recommended
- Tested with Python 3.8

## Citation
If you use this work, please cite:
```
@misc{saycan2022,
    title={Do As I Can, Not As I Say: Grounding Language in Robotic Affordances},
    author={Michael Ahn and Anthony Brohan and Noah Brown and Yevgen Chebotar and Omar Cortes and 
            Byron David and Chelsea Finn and Chuyuan Fu and Keerthana Gopalakrishnan and Karol Hausman and 
            Alex Herzog and Daniel Ho and Jasmine Hsu and Julian Ibarz and Brian Ichter and Alex Irpan and 
            Eric Jang and Rosario Jauregui Ruano and Kyle Jeffrey and Sally Jesmonth and Nikhil J Joshi and 
            Ryan Julian and Dmitry Kalashnikov and Yuheng Kuang and Kuang-Huei Lee and Sergey Levine and 
            Yao Lu and Linda Luu and Carolina Parada and Peter Pastor and Jornell Quiambao and 
            Kanishka Rao and Jarek Rettinghouse and Diego Reyes and Pierre Sermanet and Nicolas Sievers and 
            Clayton Tan and Alexander Toshev and Vincent Vanhoucke and Fei Xia and Ted Xiao and 
            Peng Xu and Sichun Xu and Mengyuan Yan and Andy Zeng},
    year={2022}
}
```

## License
This project is licensed under the Apache License 2.0 - see the LICENSE file for details.
