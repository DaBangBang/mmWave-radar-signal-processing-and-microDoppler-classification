# mmWave-radar-signal-processing-and-microDoppler-classification
This is a repository for codes and template data of paper "Experiments with mmWave Automotive RadarTest-bed"

Please cite our paper with below bibtex when you use the codes.

@INPROCEEDINGS{9048939,  author={Gao, Xiangyu and Xing, Guanbin and Roy, Sumit and Liu, Hui}, 
booktitle={2019 53rd Asilomar Conference on Signals, Systems, and Computers}, 
title={Experiments with mmWave Automotive Radar Test-bed}, 
year={2019},  volume={},  number={},  pages={1-6},  doi={10.1109/IEEECONF44664.2019.9048939}}

## Software requirement
MATLAB

## Run codes for generating range-angle maps and 3D point clouds
1. Customize your testbed/FMCW parameter in script: 
    ```
    ./config/get_params_value.m
    ```
3. Select the input data ('pms1000_30fs.mat', 'bms1000_30fs.mat' or 'cms1000_30fs.mat') in script:
    ```
    generate_ra_3dfft.m
    ```
3. Run 'generate_ra_3dfft.m' script to get results. For example, the range-angle image and detected 3D point clouds for input data 'pms1000_30fs' are shown below:

  ![pms1000_ra](https://user-images.githubusercontent.com/46943965/121766791-50763380-cb09-11eb-9bef-7608e1afa9ce.jpg)
  ![pms1000_pointclouds](https://user-images.githubusercontent.com/46943965/121766798-5835d800-cb09-11eb-883c-e7c1cb3714c0.jpg)
 
4. Manipulate the algorithm parameters in below script to obtain the desired pointcloud results:
    ```
    ./utils/cfar_RV.m
    ```

## Run codes for generating micro-Doppler maps
1. Customize your testbed/FMCW parameter in script: 
    ```
    ./config/get_params_value.m
    ```
3. Select the input data ('pms1000_30fs.mat', 'bms1000_30fs.mat' or 'cms1000_30fs.mat') in script:
    ```
    generate_microdoppler_stft.m
    ```
3. Run 'generate_microdoppler_stft.m' script to get results. For example, the micro-Doppler map for input data 'pms1000_30fs' is shown below:

   ![pms1000_md](https://user-images.githubusercontent.com/46943965/121852166-ed6cd400-cca3-11eb-8698-320efbfc9ad1.jpg)
 
4. You can manipulate the algorithm parameters in "generate_microdoppler_stft.m" to customize the micro-Doppler map properties:
    ```
    M = 16; % number of frames for generating micro-Doppler image
    Lr = 11; % length of cropped region along range
    La = 5; % length of cropped region along angle
    Ang_seq = [2,5,8,11,14]; % dialated angle bin index for cropping
    WINDOW =  128; % STFT parameters
    NOVEPLAP = 120; % STFT parameters
    ```

## Continue to update the repos