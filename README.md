# Conditioned Text-to-Speech End to End System
Read the [report.pdf](report.pdf) for all information about the project.

Our original plan was to reproduce the work in [“Controllable Emotion Transfer For End-to-End Speech Synthesis”](https://ieeexplore.ieee.org/document/9362069), which was done on a single Chinese speaker.

In our setting we used [the multi-speaker English IEMOCAP dataset](https://sail.usc.edu/iemocap/), which means
the system had to be adapted. We modified an already existing implementation of [Tacotron2](https://github.com/NVIDIA/tacotron2) from Nvidia and used already pre-trained vocoder [WaveGlow](https://github.com/NVIDIA/waveglow/tree/5bc2a53e20b3b533362f974cfa1ea0267ae1c2b1).

After initial attempts we realized that the IEMOCAP dataset lacks in the amount
and quality of data for our purpose. Therefore, we pivoted our project and focused
on 3 different approaches to condition Tacotron2 on only the speaker’s identity and
train on the [VCTK dataset](https://datashare.ed.ac.uk/handle/10283/2950). This was done successfully and it even showed
that the approach can be used on unseen speakers.

It builds upon the following repositories:
1. https://github.com/NVIDIA/tacotron2
2. https://github.com/NVIDIA/waveglow 
3. https://github.com/resemble-ai/Resemblyzer

# Architecture
![](img/arch.png)

# VCTK vs IEMOCAP datasets
| VCTK   | IEMOCAP
|-----| -------- |
| ![](img/vctk-embeddings.png)  | ![](img/iemocap-embeddings.png) |

# [Results](report.pdf): Check out [Tensorboard.dev](https://tensorboard.dev/experiment/vcappjUrQdin2D8aiaPVaA/)
![](img/alignment.png)