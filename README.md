# cs365-proj (AI vs Human Text Classification Model)

## Description
Machine Learning Project for BU <a href="https://www.bu.edu/academics/cas/courses/cas-cs-365/" target="_blank" rel="noopener noreferrer">CS365</a>, classifying human vs AI written text. 

Libraries used (currently): sklearn, pandas, numpy, NLTK

We have plans to use PyTorch instead.

### Overview

Code is based off <a href="https://www.kaggle.com/code/theodorechen/logistic-regression-with-cnn-99-91/" target="_blank" rel="noopener noreferrer">code</a> written by Roy Asraf on Kaggle using this <a href="https://www.kaggle.com/datasets/shanegerami/ai-vs-human-text/code" target="_blank" rel="noopener noreferrer">dataset</a>.

Currently only uses 1.39M entry sized <a href="[https://www.kaggle.com/code/theodorechen/logistic-regression-with-cnn-99-91/](https://huggingface.co/datasets/artem9k/ai-text-detection-pile/viewer/default/train?p=5)https://huggingface.co/datasets/artem9k/ai-text-detection-pile/viewer/default/train?p=5" target="_blank" rel="noopener noreferrer">dataset</a> from HuggingFace.

Using this dataset with no changes to original code's methodology yields 83.46% Accuracy. 

Takes ~23.5 Hours using sklearn's LogisitcRegression on 2022 M1 Pro Macbook Pro. Most compute time is used for pandas dataframe apply function being used to tokenize data. 

### Methodology

Sklearn library's LogisitcRegression model is used with 3 features: punctuation count, linking words (stop words) percentage, and text length. Sentiment value from NLTK library is also found, but doesn't make a meaningful difference to the model.

"Stop words" are also not taken into account when calculating other features, i.e. is, to, a, the, and, etc. Stop words = Linking words. 

## Currently working on...

Investigating past research into AI text detection and most effective methodology/features.

Speeding up current model's calculations to quickly test different/adjusted features, primarily by using more NumPy vector calculations rather than pandas' apply function.

Compiling all datasets selected into one, currently the model is only running on one (rather large) dataset at once.

Switching model to use PyTorch instead.

