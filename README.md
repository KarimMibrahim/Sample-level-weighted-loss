# Confidence-based Weighted Loss for Multi-label Classification with Missing Labels
This is the code for the ICMR 2020 paper 'Confidence-based Weighted Loss for Multi-label Classification with Missing Labels'. If you use the code in your research, please cite the paper as:

> Karim M. Ibrahim, Elena V. Epure, Geoffroy Peeters, and Gaël Richard. 2020. Confidence-based Weighted Loss for Multi-label Classification with Missing Labels. In Proceedings of *the 2020 International Conference on Multimedia Retrieval* (ICMR '20). Association for Computing Machinery, New York, NY, USA, 291–295. DOI:https://doi.org/10.1145/3372278.3390728.

This repository contains the following notebooks: 
- 'CB-WCE-MSCOCO' to finetune the pretrained resnset model on the MSCOCO dataset using the weighted cross entropy with 'ignore missing' protocol.
- 'CB-WCE-NUSWIDE' to finetune the pretrained resnset model on the NUSWIDE dataset using the weighted cross entropy with 'ignore missing' protocol.
- 'CE-MSCOCO' to finetune the pretrained resnet model on the MSCOCO dataset using traditional cross entropy loss
- 'CE-NUSWIDE' to finetune the pretrained resnet model on the NUSWIDE dataset using traditional cross entropy loss
- 'IM-WCE-MSCOCO' to finetune the pretrained resnet model on the MSCOCO dataset using the weighted cross entropy with 'correlations' protocol
- 'IM-WCE-NUSWIDE' to finetune the pretrained resnet model on the NUSWIDE dataset using the weighted cross entropy with 'correlations' protocol. 
- 'MSCOCO-preprocessing' to preprocess the MSCOCO dataset
- 'NUSWIDE-preprocessing' to preprocess the NUSWIDE dataset
- 'MSCOCO-results' to compile the results from all experiments and produce the plots for the MSCOCO dataset
- 'NUSWIDE-results' to compile the results from all experiments and produce the plots for the NUSWIDE dataset

The repositoy contains two directories: 
- 'labels_balanced_4labels' contains the grountruth and splits for the MSCOCO dataset computed with different ratios of artificial missing labels
- 'labels_balanced_nus' contrains the grountruth and splits for the NUSWIDE dataset computed with different ratios of artificial missing labels.
These splits could be recomputed by running the preprocessing script for each dataset 

## Instructions

Clone the repository and make sure you have Python 3.6 or later. Then follow these instructions.

1. The script uses Tensorflow Slim for the pretrained models. Follow the instructions on this repository to get it up and running: 'https://github.com/tensorflow/models/tree/master/research/slim' 

2. Download the required datasets: 
- MSCOCO: we used gluoncv to download and interface with the dataset:  https://gluon-cv.mxnet.io/build/examples_datasets/mscoco.html
- NUSWIDE: Download the dataset from 'https://lms.comp.nus.edu.sg/wp-content/uploads/2019/research/nuswide/NUS-WIDE.html'. Notice: you need to contact the creators of NUWIDE to get access to the raw images dataset

3. Download the pretrained models. This can be simply done by calling the 'download_pretrained_model' function in any of the scripts. Alternatively, you can download any other model, but the model architecture should be edited in the script in the main loop. 

4. You need to edit the paths in the script to point to the dataset and output directories in your machine. These instances are marked with a comment "# [TODO]" in the script. 

## Acknowledgment
This work has received funding from the European Union’s Horizon 2020 research and innovation programme under the Marie Skłodowska-Curie grant agreement No. 765068.
