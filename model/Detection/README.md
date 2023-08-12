# Detection
Using one model to do face detection and body detection.
## Requirement
- light weight
- low latency
## Proposal
- YoloV5
- YoloX
- nanodet
- PicoDet
- Yolo-fastest
- YoloV5-Lite
- MutualGuide
- YoloV6
- FastestDet
## Dataset
- Face detect
    - Use open source dataset
    - PubFig
    - CelebA
    - Colorferet
    - MTFL
    - LFW
    - etc
Body detect
    - NightOwls
        - focus on night
    - PANDA
        - include head, body, tracking
    - SCUT FIR
    - Wider Person
    - HDA
## Training
1. Baseline
    - Use same dataset to train proposal model. Pick best performance model.
2. Optimize
    - Dataset augmentation for fitting our situation.
    - Training tricks for better mAP
    - Optimize post-process for better mAP. NMS, IOU, etc.
3. Online update
    - Release in our own camera.
    - Check online performance
## Deployment
- light weight detection is OK to deploy in client side, predict by CPU.
- C++ with NCNN/MNN/TNN/etc
- As we need to have a realtime monitor to show all the result, it's also OK to deploy in the cloud.
- Python/C++ web service with ONNX weight file.