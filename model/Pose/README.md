# Pose estimate + cluster
Pose estimate model for key-point detect
Base on the key-point, using cluster to find abnormal pedestrian.
## Requirement
- High precision. Can not has too much false positive cases.
- single-human vs Multi-humans. As we have human detection, single-human is enough.
- 3D vs 2D. For our project, only 2D feature may can not represent well(according to the distance, view, etc). 3D is better.
## Proposal
- DconvMP
    - Joint point regression + joint point detection
- 《3D Human Pose Estimation from Monocular Images with Deep Convolutional Neural Network》
    - Extract volumetrc representation from 2D image.
- 《Integral Human Pose Regression》
    - Using soft-argmax. Change caculate max from heatmap to caculate expectation.
- Camera Distance-aware Top-down Approach for 3D Multi-person Pose Estimation from a Single RGB Image》
    - Top-Down method.
    - DetectNet+RootNet+PoseNet
- 《3D Human Pose Estimation = 2D Pose Estimation + Matching》
    - Do 2D first.
    - KNN for 3D pose matching.
    - Need large dataset
- mmhuman3d/mmpose3d
    - SMPLify
        - CNN extract 2D key-point. Then estimate 3D pose.
    - HMR
        - 3D regression
        - GAN
    - SPIN
        - combain SMPLify with HMR
- CLIFF
    - Multi-human
- OSX
    - ViTPose
    - Large dataset
## Dataset
- HiEve
- MPII Human Pose
- CrowdPose
- Human3.6M
- PedX
- SURREAL
- Mo2Cap2
- DensePose
- PoseTrack
- Custom dataset. Fit our camera view and distance.
## Training
1. Baseline
    - Use same dataset to train proposal model
2. Evaluate
    - Include in online experiement
## Deployment
- Deploy in the cloud
- Python/C++ with ONNX
## Cluster
Using the feature from pose estimate module.
Before release the whole model, we haven't real thief pose. Go with unsupervised method first.
Use DBSCAN first