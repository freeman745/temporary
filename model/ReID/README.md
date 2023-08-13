# ReID
Using ReID model to track across different camera
## Requirement
- High accuracy
## Proposal
- CNN
    - MGN
- ViT
    - CLIP-ReID
## Dataset
- Market-1501
- DukeMTMC-reID
- CUHK03
## Training
1. Baseline
    - Use same dataset to train proposal model
2. Evaluate
    - CMC
    - mAP
## Deployment
- Deploy in the cloud
- Python/C++ with ONNX
