[![Python](https://img.shields.io/badge/python-3.6-blue.svg)](https://python.org)

# VeinCV
## Motivation
This repository is an official PyTorch implementation of the paper "Near-Infrared-to-Visible Vein Imaging via Convolutional Neural Networks and Reinforcement  Learning" (...). Here we solve Peripheral Difficult Venous Access (PDVA) problem through the pipeline of NIR imaging, CNNs and RL.
![Experimental setup scheme](https://github.com/cviaai/NIR-VISIBLE-IMAGING-WITH-CNN-RL/blob/master/img/Experimental_setup_scheme.png)

</p>
<p align="center">
<em> Fig. 1. Experimental setup </em><br>
</p>

## Segmentation pipeline
![Segmentation pipeline](https://github.com/cviaai/NIR-VISIBLE-IMAGING-WITH-CNN-RL/blob/master/img/Segmentation_pipeline.png)

</p>
<p align="center">
<em> Fig. 2. Segmentation pipeline featuring Frangi vesselness filter, attention U-Net and clDICE loss </em><br>
</p>

## Requirements
To install requirements:

```setup
pip install -r requirements.txt
```

## Training

To train the models used in the paper, run this command:

```train
python main.py
```

## Evaluation

To evaluate models, run:

```eval
python eval.py --config <path_to_config_file>
```
---Will be edited--- 

## Code structure 
Folder "server" - main folder with experiment files
[UPDATE WITH RL FILES]

Option 1.

```
.
├───dataset_90
├───ignite_new
│   ├───architectures
│   ├───pretrained_models
│   ├───VeinsDataset.py
│   ├───dice_helpers.py
│   ├───inference.ipynb
│   ├───iou.py
│   ├───loss.py
│   ├───main.py
│   ├───miou.py
│   ├───precision.py
│   ├───recall.py
│   ├───ssim.py
│   ├───train.py
│   ├───tversky_loss.py
│   └───utils.py
└───img_check
```

Option 2.

* dataset_90 - 90 forearm snapshots and 90 corresponding masks, 75 of them for train, 15 for validation
* ignite_new - experiment
  * architectures - all used convolutional neural network architectures for semantic segmentation task
  * pretrained_models - here saved pre-trained models
  * VeinsDataset.py - preparing data
  * dice_helpers.py - helper function for dice
  * inference.ipynb - Model Inference experiments (draft)
  * iou.py - Intersection over Union metric
  * loss.py - Loss functions (on the following: Binary Cross Entropy, Dice, clDice)
  * main.py - full experiment: paths, parameters, model choice, etc.
  * miou.py - mean Intersection over Union metric
  * precision.py - Precision metric
  * recall.py - Recall metric
  * run.ipynb - run the experiment
  * ssim.py - Structure Similarity Loss function
  * train.py - main training cycle
  * tversky_loss.py - Tversky loss
  * utils.py - utils functions
* img_check - 1 random training sample to check; 4 snapshots in it - original snapshot, ground true mask, predicted image, predicted mask (binarized predicted image)

## Citing
If you use this package in your publications or in other work, please cite it as follows:
```
@misc{rubashevskii2020nir,
    title={Near-Infrared-to-Visible Vein Imaging via Convolutional Neural Networks and Reinforcement  Learning},
    author={Aleksandr Rubashevskii and Vito M. Leli and Aleksandr Sarachakov and Oleg Y. Rogov and Dmitry V. Dylov},
    year={2020},
    eprint={...},
    archivePrefix={arXiv},
    primaryClass={eess.IV}
}
```

## Maintainers
Aleksandr Rubashevskii (main contributor) @rubaha96

Vito Michele Leli @vitomichele

Oleg Rogov @olegrgv
