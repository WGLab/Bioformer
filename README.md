# LitBERT
LitBERT is a light-weight BERT model pretrained from biomedical Literature. LitBERT was pretrained on all PubMed abstracts (as of Jan 2021) and 1 million randomly-sampled PubMed Central full-text articles. We used the original implementation of [BERT](https://github.com/google-research/bert) to train the model. LitBERT has the following features:
 
 - **Accurate**. LitBERT achived better performance than the previous state of the art (SOAT) model BioBERT-Base (v1.1)
 - **Light weight**. LitBERT has 8 transformer layers and the embedding size is 512. Compared with a typical BERT-base model (e.g. BioBERT-Base), LitBERT uses 60% less parameters. 
 - **Fast and memory efficient**. The training and predicting speed of LitBERT is 200% faster than a typical BERT-base model. LitBERT can be fine-tuned on GPUs with small memory. 
 - **Biomedical vocabulary**. LitBERT uses a biomedical vocabulary of 32768 tokens, which was trained from PubMed abstracts and PubMed Central full-text articles. LitBERT is able to encode some special unicode characters not in the original BERT vocabulary. 
 - **Long sequence input**. The biomedical vocabulary is more efficient at encoding biomedical text and thus the max sequence length (character length) of LitBERT is 30% longer than BERT model with general vocabulary, although the max token length is the same (512 tokens). 

## Download 

### LitBERT-cased-v1.0 
hidden_embedding_size=512, attention_head=8, layer=8
pretrained for 2 million steps

#### Tensorflow checkpoint

The tensorflow checkpoint can be downloaded from [here](https://drive.google.com/file/d/1H328pWFwvSGN0sMxYO_kAKjSLoPJDPVk/view?usp=sharing). 

The `.zip` file contains three items:

- A TensorFlow checkpoint (LitBERT-cased-biomed-vocab-model.ckpt) containing the pre-trained weights (which is actually 3 files).
- A WordPiece vocabulary file (vocab.txt) used for (de)tokenization. This is a biomedical vocabulary which was trained from PubMed abstracts and PubMed Central full-text articles. 
- A config file (config.json) which specifies the hyperparameters of the model.

#### Pytorch checkpoint

## Fine-tuning LitBERT
