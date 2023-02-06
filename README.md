# Bioformer: an efficient BERT model for biomedical text mining
Bioformer is a lightweight BERT model pretrained from biomedical Literature. We pretrained two Bioformer models, `Bioformer-8L` and `Bioformer-16L`. Both models were pretrained on all PubMed abstracts (as of Jan 2021) and 1 million subsampled PubMed Central full-text articles. We used the original implementation of [BERT](https://github.com/google-research/bert) to train the model. Bioformer models have the following features:
 
 - **Accurate**. Bioformer achieves comparable or even better performance than BioBERT/PubMedBERT on downstream NLP tasks.
 - **Lightweight**. Bioformer has 8 layers (transformer blocks) with a hidden embedding size of 512, and the number of self-attention heads is 8. Its total number of parameters is 42,820,610. Compared with a typical BERT-base model (e.g. BioBERT-Base), Bioformer uses 60% less parameters. 
 - **Fast and memory efficient**. Bioformer is 3X as fast as a BERT-base model. Bioformer can be fine-tuned using GPUs with 4-8GB memory. 
 - **Biomedical vocabulary**. Bioformer uses a biomedical vocabulary of 32768 tokens, which was trained from PubMed abstracts and PubMed Central full-text articles. Bioformer is able to encode some special unicode symbols that are not in the original BERT vocabulary. 
 - **Long sequence input**. The biomedical vocabulary is more efficient at encoding biomedical text and thus the max input text length (character length) of Bioformer is 20% longer than BERT model with general vocabulary, although the max token length is the same (512 tokens). 

## Download 

#### Tensorflow checkpoint

The tensorflow checkpoint can be downloaded from [here](https://drive.google.com/file/d/1UWrXsstU730xIMjSSD3I3CwVJpc_G97E/view?usp=sharing). The `.zip` file contains three items:
- A TensorFlow checkpoint (`bioformer-cased-v1.0-model.ckpt-2000000`) containing the pre-trained weights (which is actually 3 files).
- A WordPiece vocabulary file (`vocab.txt`) used for (de)tokenization. This is a biomedical vocabulary which was trained from PubMed abstracts and PubMed Central full-text articles. 
- A config file (`bert_config.json`) which specifies the hyperparameters of the model.


#### Pytorch checkpoint

The Pytorch checkpoint can be downloaded from [Huggingface](https://huggingface.co/bioformers/bioformer-cased-v1.0). You can easily use Bioformer with the [transformers](https://github.com/huggingface/transformers) library. 


## Acknowledgment

Bioformer is partly supported by the Google TPU Research Cloud (TRC) program.
