# Text Summarization Project

## Team Members:
- Rutvik Deshpande
- Priyal Shaha
- Abhishek Bahad

## Referred Research Paper:
The research paper authored by Joseph Okonda, Robert Kinini, and Peter Wang from Stanford University presents an in-depth exploration of neural abstractive summarization, particularly focusing on the Gigaword dataset. The authors address the limitations of standard sequence-to-sequence models in generating coherent and meaningful abstractive summaries. Through a systematic approach, they introduce enhancements to the baseline model, including intradecoder attention, a pointer-generator network, hierarchical attention, and a novel bottom-up summarization pipeline inspired by style transfer in computer vision.

## 1. Introduction:
The objective of our project is to address the challenge of Text Summarization, a Natural Language Processing (NLP) task. Text summarization involves condensing large volumes of text into shorter, coherent summaries while retaining key information and overall meaning. Neural attention-based sequence-to-sequence models show potential in generating superior extractive summaries. However, their application in abstractive summarization often leads to the production of redundant and nonsensical phrases. Several studies have investigated different adjustments to this conventional framework, aiming to enhance its effectiveness in abstractive summarization tasks.

## 2. Dataset:
We utilized the Gigaword dataset, which comprises a vast collection of newswire text data, making it ideal for training and testing our models focused on summarization. The dataset consists of over 3.8 million documents in the training set, 190k documents in validation, and 1.95k documents in the test set, each paired with a concise summary. For computational reasons, we used a subset of the data.

### Data Cleaning and Pre-processing:
We followed several steps to clean and preprocess the data, including text normalization, HTML tag removal, removal of irrelevant characters, contraction mapping, apostrophe handling, punctuation and special character removal, stop word removal, and long word retention. These steps were crucial in refining the dataset, making it more suitable for sophisticated NLP tasks like text summarization.

## 3. Experiments:
In our pursuit of mastering Text Summarization, we experimented with various models, each contributing uniquely to the task.

### Model Overview:
1) **Encoder-decoder using LSTM**: We started with a sequence-to-sequence framework, consisting of an Encoder and Decoder network. Despite minimal loss on training and validation sets, the ROUGE score was extremely low, and the summaries generated for the test set were incorrect.
2) **GloVe-Enhanced Encoder-Decoder with LSTM**: Introducing GloVe embeddings and adapted dropout rates, we aimed to improve semantic representation. However, the ROUGE score only marginally increased.
3) **LSTM with attention layer**: Despite employing attention mechanisms, the model fell short of generating high-quality summaries.
4) **Fine Tuning T5 small model**: Leveraging the T5 small model, we achieved significant improvement in the ROUGE score, generating sensible summaries compared to baseline models.
5) **Fine Tuning T5 small model (Un-freezing Decoder)**: Selectively unfreezing decoder layers did not significantly improve generalization compared to the previous model.
6) **Fine Tuning using PyTorch Lightning**: Employing PyTorch Lightning, we fine-tuned a T5 model and achieved a ROUGE score of 43% on the test dataset.
7) **Fine Tuning using Trainer class**: Fine-tuning a T5 small model with Hugging Face Trainer class resulted in a ROUGE score of 40% on the test set.

## 4. References:
- NLPlanet. (2022). A Full Guide to Fine-Tuning T5 for Text2Text and Building a Demo with Streamlit.
- Paperspace. (n.d.). Introduction to Seq2Seq Models.
- Shivam Duseja. (n.d.). Deep-Summarization LSTM with Attention.
- Keras. (n.d.). T5 HF Summarization.
- Hugging Face. (n.d.). Transformers for Summarization.
- Hugging Face. (n.d.). Sagemaker Distributed Training Seq2Seq.
- Towards Data Science. (n.d.). Why AdamW Matters.
- Analytics Vidhya. (2019). Comprehensive Guide: Text Summarization using Deep Learning in Python.

## 5. Contributions:
- Rutvik Deshpande: Preprocessing, Research Paper review, Baseline models.
- Priyal Shaha: Preprocessing, Research Paper review, Fine Tuning T5-small using Trainer class and PyTorch Lightning.
- Abhishek Bahad: Preprocessing, Research Paper review, Fine Tuning T5-small by hyperparameter tuning and un-freezing decoder layers.

