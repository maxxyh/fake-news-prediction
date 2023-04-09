# fake-news-prediction

This repository contains models which predict reliability of news sources (4 ways) based on the Labelled Unreliable News (LUN) dataset.

This is a project for CS4248, AY 22/23 Sem 2.

## Instructions to set up

1. Download dataset => take the entire `raw_data` folder. Download it [here](https://github.com/BUPT-GAMMA/CompareNet_FakeNewsDetection/releases/tag/dataset).
2. For faster training, download `texts_cleaned.csv` and chuck it in top-level directory.
3. (For Simple BOW) Create a `word_vec` folder and add [GoogleNews-vectors-negative300.bin](https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit?resourcekey=0-wjGZdNAUop6WykTtMip30g) inside (requires unzipping).
4. (For LSTM) Create a `glove` folder and add [glove.6B.100d.txt](https://www.kaggle.com/datasets/thanakomsn/glove6b100dtxt) inside.

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

Models included for loading:

- `bert_model` = BERT trained without removing stopwords
- `bert_model_stopword_removed` = BERT trained with stopwords removed
- `lstm_model` = lstm baseline
- `bi-lstm_model` = bi-LSTM baseline
- `bi-lstm_model_best` = best bi-LSTM model, trained with GloVe embeddings and nearmiss undersampling v3
- `cnn_model` = CNN baseline

## Model training files Included

- `simple_bow_classifier.ipynb` = contains all our classical learning models (LR, NB, random forest etc.)
- `lstm-bilstm_classifier.ipynb` = best lstm and bi-lstm models
- `lstm_rnn_cnn_classifier.ipynb` = only use this for CNN model
- `bert_classifier.ipynb` = first attempt of BERT. Used as baseline
- `bert_stopwords_removed.ipynb` = BERT training with stopword removal

## Other misc. files

- `log_reg_explainer_label{1,2,3,4}.csv` = tokens and coefficients for our logistic regression model.