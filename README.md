# Computer Vision Assignment
## Subject description
Establish a web system to monitor human poses at a bike parking
## Background
Bicycle Battery Theft is a Common Occurrence. 
We want to monitor the parking to detect this issue and help government to track the thief.
## Location
A square bike parking area near a subway station. Several roads connected to this bike parking.
## Hardware
One RGB camera for the parking area. Each road has one RGB camera for tracking.
One GPU in the cloud for dealing with multi-streams.
## Requirements and solutions
### Thief detection
Need to distinguish ordinary pedestrian and thief.
Thief has special behavior.
- Ordinary pedestrian will just pass through the are. Thief will stay for long time.
    - Face tracking
        - Face identify for tracking need high quality images. We only use one camera for the 
          parking area. The image may not good enough to recognize the face.
    - Pedestrain tracking
        - May not as accurate as face tracking. According to the hardware condition, choose
          this method for this task.
- Thief may has special pose. 
    - Classfication
        - Apply easily. But Low Scalability.
    - Pose estimate.
        - High scalability. 
### Thief tracking
When we detect one thief. We need to notice police. The thief will leave parking area.
Need to track the thief across the cameras.
- Face tracking
    - Can used across the cameras. But rely on high quality images.
- ReID
    - Can used across the cameras. But can only provide general information.

