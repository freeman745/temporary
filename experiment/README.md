# Experiment
The page is for experiment of the whole pipeline
## Evaluation index
This task is very unbalance.
Using TAR and Recall.
TAR: pass our models and is good pedestrian. higher the better
Recall: Thief detected / all thieved. higher the better
## Online experiment
Model + manual check
When model detected proposal thief, manual double check. Ensure it's a true thief.
Monitor this area. Gathering real cases. Calculate missed thieves.
## Sub module evaluate
Monthly manual double check for all sub modules.
## Dashboard
We need to create a dashboard to analysis the model result.
Data point we need to track:
- Detection
    - pedestrian detect count
    - face detect count
- Tracking
    - mean stay time
- ReID
    - specific pedestrian count
- Thief detect
    - thief face
    - thief body
- etc
## model online tuning
We need to gathering the data after the whole project released.
Have a monthly review for double check the model result.
Collect hard example for all the modules to tune the online model.
Build an automatical process rely on MLOps to auto-retrain the model.