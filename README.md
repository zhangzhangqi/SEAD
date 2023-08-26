# SEAD
==
Scene and Action Joint Prediction Model v1.0.

# Data preparation
Create the following three directories under the 'data' directory based on the scene graph annotations, Action Genome annotations(https://drive.google.com/drive/folders/1LGGPK_QgGbh9gH9SDFv_9LIhBliZbZys):

* corpus: Each object's corpus consists of a txt file named after the object's name, such as "sofa.txt".
Each line in the file corresponds to a spatial-contact event sequence (starting from "*", end with "#") for a video.

* grammar: Each object's stochastic grammar is a pcfg file named after the object's name, such as "sofa.pcfg".

* duration: Different spatial-contact events corresponding to each object are stored in txt files named after the object's name, such as "sofa_event.txt".
Each line in the file corresponds to a spatial-contact event and its average duration.

# Grammar Diction Learning




