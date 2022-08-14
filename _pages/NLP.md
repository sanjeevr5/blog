---
layout: page
title: NLP With DL
permalink: /NLP With DL/
---

# NLP with Pytorch

## 1. Binary classification problem using RNNs

**This exercise is performed on IMDB movie reviews dataset. There are two sentiments here 0. Negative 1. Positive. **
<i> Techniques used </i>

1. We shall train our embedding representations.
2. Using an RNN architecture with pad_sequences, pack_pad_sequences and pad_packed_sequences.
3. Dataloaders to have generator kind of data feed to the model.
4. The sequences should not be too long. There should be a clipping factor and hence choose the vocabulary wisely.LSTMs cannot handle very long input sequence.
5. Passing outputs of output layer or the hidden state to the dense layer.

## 2. Multiclass classification with RNNs

This exercise is performed on AGNews dataset with four news categories:

1 : World
2 : Sports
3 : Business
4 : Sci/Tec 

<i> Techniques used </i>

1. We shall use bpeMB word representations as word vectors. This is a sub word tokenization process with a vector for every sub token. Sub-word tokens can make the sentences longer and hence to be used with care.
2. We will just use the titles to predict the news category.
3. This RNN architecture does not pad sequences, we shall feed the packed sequences directly to the embedding layer.
4. Dataloaders to have generator kind of data feed to the model.
5. Passing outputs of output layer or the hidden state to the dense layer.

## 3. A multiclass classification using the Embedding bag layer

The Embedding layer gives us a vector representation for every token while the embeddingbg performs an aggregation operation on top of every sentence and returns the result.

Embedding I/P : [['hi', how', 'are', 'you'], ['ok', 'bye', '<pad>', '<pad>']]

Embedding layer O/P : (2,4,64)

Embedding bag I/P : ['hi', how', 'are', 'you', 'ok', 'bye']

Embedding bag O/ P: There is no need of padding tokens it can be directly fed. (2, 64) -> (B, embed_dim)

Embedding bag since it performs some aggregate operation sequential information is lost. There is no need of padding. Offsets should be mentioned instead of the padding. The offsets of above example is [0, 4] since first sentence starts from 0 and second sentence starts at 4th index.

## 4. Football name generator with char RNN

1. Without conditional generation - **implemented**
2. With conditional generation -- **yet to implement**

More at : https://pytorch.org/docs/stable/generated/torch.nn.EmbeddingBag.html

## 5. Classification with ULMFiT (AWD-LSTM) and fastai
