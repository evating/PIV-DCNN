# This is the source code of PIV-DCNN
We submit it to Experiments in Fluids. Some useful information is also provided here.

1. Directory structure
2. Installation guidance
3. More experimental results
4. Some tips about our method
5. Links to [data generaton](https://github.com/yongleex/PIV-DCNN/tree/master/PIV_DNN),[experiment arrangement](https://github.com/yongleex/PIV-DCNN/tree/master/experiments)

### 1. Directory structure
```
├── PIV-DCNN20170710
│   ├── readme.md
│   ├── install.m
│   ├── data
│   │   ├── ImagesForDataset
│   │   │   ├── readme.md
│   │   │   └── A1-10.bmp
│   │   ├── NetF1~F4-3
│   │   │   ├── imdb.mat
│   │   │   ├── net-epoch-1.mat
│   │   │   └── net-train.pdf
│   │   └── TestImages
│   │       ├── readme.md
│   │       └── *.tif, *bmp, *jpg
│   ├── PIV_DNN
│   │   ├── readme.md
│   │   ├── ChangesForMatConvNet
│   │   │   └── some files 
│   │   ├── cnn_pivdnn_init.m 
│   │   ├── cnn_pivdnn.m
│   │   ├── genPIVImgDB_F4.m
│   │   ├── genPIVImgDB.m
│   │   ├── ImgData.mat
│   │   ├── Nets.mat
│   │   ├── pivdnn.m
│   │   └── train.m
│   ├── experiments
│   │   ├── readme.md
│   │   └── exp0-7.m
│   ├── matconvnet
│   │   └── MatConvNet files
│   ├── OpticalFlow
│   │   └── OpticalFlow files
│   ├── PIVCC
│   │   ├── dctn.m
│   │   ├── idctn.m
│   │   ├── PIV_analysis.m
│   │   └── smoothn.m
│   └── pivlab
│   │   └──PIVlab files
```

### 2. Installation
- **Install GPU driver, [CUDA](https://developer.nvidia.com/cuda-downloads) and [CuDNN](https://developer.nvidia.com/cudnn).** 
- **Run `install.m` in the main folder**. It will download the MatConvNet, compile files, and copy some customized files to the MatConvNet automatically.
- **Cautions:** You need to specify the configure terms (enable GPU, CUDA root, ...) in `install.m` if the default values do not work. (Note, the slow CPU version without GPU support is also ok)
- **Enjoy it.**  `cd '../PIV_DNN'; run('PIVdnn.m');`  or `cd '../experiments';run('exp1.m')`.

Information about the packages 

-  PIVlab [website](http://cn.mathworks.com/matlabcentral/fileexchange/27659-pivlab-time-resolved-particle-image-velocimetry--piv--tool)
-  MatConvNet [website](http://www.vlfeat.org/matconvnet/)


### 3. More experimental results

#### 3.1. Vortex Pair flow
- Raw Images

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/VortexPair/rawImage.gif" width = "320" height = "250" alt="particle model" align=center />

- Vector field (color contour reprensents corresponding magnitude)

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/VortexPair/PIV_DCNNlevels.gif" width = "400" height = "300" alt="particle model" align=center />

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/VortexPair/vectorField.png" width = "1024" height = "250" alt="particle model" align=center />

- Vector component histogram

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/VortexPair/hist.png" width = "1024" height = "200" alt="particle model" align=center />


#### 3.2. Turbulent Jet

- Raw Images

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/TurbulentJet/rawImage.gif" width = "320" height = "200" alt="particle model" align=center />

- Vector field (color contour reprensents corresponding magnitude)

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/TurbulentJet/vectorField.png" width = "1024" height = "200" alt="particle model" align=center />

- Smoothed vector field 

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/TurbulentJet/vectorFieldSmooth.png" width = "1024" height = "200" alt="particle model" align=center />

- Vector component histogram

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/TurbulentJet/hist.png" width = "1024" height = "200" alt="particle model" align=center />

#### 3.3 Jet flow

- Raw Images

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/Jet/rawImage.gif" width = "320" height = "200" alt="particle model" align=center />

- Vector field (color contour reprensents corresponding magnitude)

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/Jet/vectorField.png" width = "1024" height = "200" alt="particle model" align=center />

- Vector component histogram

  <img src="https://github.com/yongleex/PIV-DCNN/blob/master/experiments/images/Jet/hist.png" width = "1024" height = "200" alt="particle model" align=center />



### 4. Tips:

- System requirement(8G RAM, Hard disk space > 50G, GPU with computation ability >3.0 is promotional)
- CuDNN is highly recommended
- Training 6 DCNN nets(optional, about 2 days with GPU accelaration):`cd '../PIV_DNN';run('train.m')`
- The figures in our manuscript (about 2 day to run massive Monte - Carlo simulation):`cd '../experiments'; run('exp0.m')`


~~Yong Lee (Email: [leeyong@hust.edu.cn](leeyong@hust.edu.cn)) @2017-07-10~~
Yong Lee (Email:[yongli.cv@gmail.com](yongli.cv@gmail.com)) @2019-12-19
     



