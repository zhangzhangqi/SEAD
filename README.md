# SEAD
Scene and Action Joint Prediction Model v1.0.

# Data preparation
Download [Action Genome annotations](https://drive.google.com/drive/folders/1LGGPK_QgGbh9gH9SDFv_9LIhBliZbZys) and place them under ./annotations/.

Create the following three directories and corresponding files under the ./data/ directory based on the annotation files under ./annotations/:

* __corpus__:
This directory stores the corpus files for all objects. The corpus for each object is a file named "object.txt", such as "sofa.txt", in which, each line corresponds to a spatial-contact event sequence for a video (starting with "*" and ending with "#").

* __grammar__:
This directory stores the grammar files for all objects. Each object has an associated stochastic grammar file named "object.pcfg", such as "sofa.pcfg". These grammar files are learned from the following "Grammar Dictionary Learning" step.

* __duration__:
This directory stores the duration of spatial-contact events for all objects. Distinct spatial-contact events corresponding to each object are stored in a file named "object_duration.txt", such as "sofa_duration.txt", where each line corresponds to a spatial-contact event along with its average duration associated with the object.

# Grammar Dictionary Learning with ADIOS
```bash
ModifiedADIOS filename eta alpha context_size coverage
```

* __filename__: the file name of each object's corpus in "./data/corpus/", such as "sofa.txt".
* __eta__: is set to 0.9 in our model.
* __alpha__: is set to 0.01 in our model.
* __context_size__:  the size of the context window used for searching the equivalence classes, is set to 5 in our model.
* __coverage__:  the minimum overlap for bootstrapping equivalence classes, is set to 0.65 in our model.

The stochastic grammars acquired from this step are saved in the "./data/grammar/", such as "sofa.pcfg".

# Action Anticipation Model Training
`python ./action_anticipation_train.py`

# Action Anticipation
`python ./action_anticipation_test.py`






