# fake-news-prediction

This repository contains models which predict reliability of news sources (4 ways) based on the Labelled Unreliable News (LUN) dataset.

This is a project for CS4248, AY 22/23 Sem 2.

## Instructions to set up

1. Download dataset => take the entire `raw_data` folder. Download it [here](https://github.com/BUPT-GAMMA/CompareNet_FakeNewsDetection/releases/tag/dataset).
2. For faster training, download `texts_cleaned.csv` and chuck it in top-level directory.
3. (For Simple BOW) Create a `word_vec` folder and add [GoogleNews-vectors-negative300.bin](https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit?resourcekey=0-wjGZdNAUop6WykTtMip30g) inside (requires unzipping).
4. (For LSTM) Create a `glove` folder and add [glove.6B.300d.txt](https://www.kaggle.com/datasets/thanakomsn/glove6b300dtxt) inside.

To train the model, run through the `run_classifier.ipynb` file.

Tip: For **pip setup**, run `pip install -r /path/to/requirements/file`. Requirements file exists as `requirements-mac-m1.txt` or `requirements-mac-intel.txt`, but only for Mac. Please change as it suits you.

Tip: To **load and save your trained models**, check this guide [here](https://www.tensorflow.org/guide/keras/save_and_serialize).

### Saving a model

```Python
model = ...  # Get model (Sequential, Functional Model, or Model subclass)
model.save('path/to/location')
```

### Loading a model

```Python
from tensorflow import keras
model = keras.models.load_model('path/to/location')
```
