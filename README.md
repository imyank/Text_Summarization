# Abstractive Text Summarization

## Overview

A system that will take in a long (> 20 word) English text and generate a short summary.  
Following is a link to a training set that has aligned pairs of articles and their summaries:
**https://www.kaggle.com/sunnysai12345/news-summary?select=news_summary.csv**

In total, we have 102797 data samples to work on(after preprocessing), and the final CSV file in pandas dataframe 
has around 1 lakh headlines for the text.

## Architecture

The model we have used is an Encoder-Decoder-based Transformer with multi-head attention. Unlike BERT, 
which uses a masked language model, we have used two types of masks in the transformer. 

## Training

In training, the model is trained on the train set (50k samples). The predictions are computed from the transformer function; the training loss and validation loss are simultaneously computed.

## Loss function

Training is being done with sparse categorical cross-entropy loss. This needs a target as the one-hot encoded version of each word and thus resulting in a huge array.

## Evaluation metrics

**ROUGE**: ROUGE stands for Recall Oriented Understudy for Gisting Evaluation. There are two types of ROUGE metrics: ROUGE-N and ROUGE-L. 
In the code part, we have implemented ROUGE-L

**BLEU**: Bilingual Evaluation Understudy (BLEU) was developed for translation; it is also used for text summarization. A perfect match gives the 1-score, whereas a perfect mismatch gives 0. 

## Results
[![Screenshot-2022-09-12-at-11-47-35-PM.png](https://i.postimg.cc/VLF31dVV/Screenshot-2022-09-12-at-11-47-35-PM.png)](https://postimg.cc/HVVS9sHw)


## For detail implementation refer the report and code section
