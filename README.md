
## Exposing DeepFake Videos By Detecting Face Warping Artifacts
Yuezun Li and Siwei Lyu \
University at Albany, State University of New York, USA \
IEEE Conference on Computer Vision and Pattern Recognition Workshops (CVPRW), 2019

### Overview

Our method is based on the observations that current DeepFake algorithm can only generate images of limited resolutions, which need to be further warped to match the original faces in the source video. Such transforms leave distinctive artifacts in the resulting DeepFake videos.
Our method detects such artifacts by comparing the generated face areas and their surrounding regions with a dedicated Convolutional Neural Network (CNN) model.  

#### Negative Samples

To train the CNN model, we simplify the process by simulating the resolution inconsistency in affine face warpings directly. 
Specifically, we first detect faces and then extract landmarks to compute the transform matrices to align the faces to a standard configuration. We apply Gaussian blurring to the aligned face, which is then affine warped back to original image using the inverse of the estimated transformation matrix.

### Requirements
- Tensorflow 1.3.0
- Ubuntu 16.04
- CUDA 8.0
- Python 2.7 with following packages
    ```
    yaml==3.12
    easydict==1.7
    matplotlib==1.5.3
    dlib==19.16.0
    opencv==3.4.0
    ```
