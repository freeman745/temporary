# Tracking
Using one model to do face detection and body detection.
## Requirement
- light weight
- low latency
## Proposal
- DBT/DFT
    - DFT
        - Detection Free Tracking
        - Need to initialize the first frame
        - We have new human attending in the following frame
        - Don't fit our project
    - DBT
        - Detection-Based Tracking
        - We already have detection module
        - DBT fit our project
- Online/Offline
    - Offline need the whole video
    - Our project need realtime process. So we choose online
- Tradition/DeepLearning
    - Tradition online method
        - NNSF
        - PDAF
        - JPDA
    - DeepLearning
        - DeepSort
            - Base on sort
            - Add ReID feature
            - IOU match + distance match, appearance match
        - CenterTrack
            - Base on distance
        - FairMOT
            - Base on centernet
            - ReID for head
        - MOTDT
            - Base on DeepSort
            - R-FCN based on SqueezeNet + Track score before NMS
        - JDE
            - Base on MOTDT and YoloV3
            - Add Embedding
            - Triplet loss
- Conclusion
As we also have ReID module and face may not too clear, we pick DeepLearning method.
## Dataset
- MOTChallenge
- PANDA
## Training
1. Baseline
    - Use same dataset to train proposal model
2. Evaluate
    - MOTA+MOTP
## Deployment
- Deploy in the cloud
- Python/C++ with ONNX
