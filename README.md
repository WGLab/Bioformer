# Bioformer: an efficient BERT model for biomedical text mining
Bioformer is a lightweight BERT model pretrained from biomedical Literature. We pretrained two Bioformer models, `Bioformer-8L` and `Bioformer-16L`. Both models were pretrained on all PubMed abstracts (as of Jan 2021) and 1 million subsampled PubMed Central full-text articles. We used the original implementation of [BERT](https://github.com/google-research/bert) to train the model. Bioformer models have the following features:
 
 - **Accurate**. Bioformer achieves comparable or even better performance than BioBERT/PubMedBERT on downstream NLP tasks. A detailed evaluation is [here](https://arxiv.org/abs/2302.01588).
 - **Smaller model size**. `Bioformer-8L` and `Bioformer-16L` reduced the model size by 60% compared with `BERT-Base`/`BioBERT-Base`/`PubMedBERT`.
 - **Fast and memory efficient**. `Bioformer-8L` is 3X as fast as `PubMedBERT`, and `Bioformer-16L` is 2X as fast as `PubMedBERT`.
 - **Biomedical vocabulary**. Bioformer uses a biomedical vocabulary of 32768 tokens, which was trained from PubMed abstracts and PubMed Central full-text articles. Bioformer is able to encode some special unicode symbols that are not in the original BERT vocabulary. 


## Download 

#### Pytorch checkpoint

Pretrained model weights of `Bioformer-8L` and `Bioformer-16L` are available on HuggingFace ([Bioformer-8L](https://huggingface.co/bioformers/bioformer-8L), and [Bioformer-16L](https://huggingface.co/bioformers/bioformer-16L))

You can easily use Bioformer with the [transformers](https://github.com/huggingface/transformers) library. 


## Acknowledgment

Pretraining of Bioformer is partly supported by the Google TPU Research Cloud (TRC) program.

## Citation

Fang L, Chen Q, Wei C-H, Lu Z, Wang K: Bioformer: an efficient transformer language model for biomedical text mining. arXiv preprint arXiv:2302.01588 (2023). DOI: https://doi.org/10.48550/arXiv.2302.01588

```
@ARTICLE{fangli2023bioformer,
       author = {{Fang}, Li and {Chen}, Qingyu and {Wei}, Chih-Hsuan and {Lu}, Zhiyong and {Wang}, Kai},
        title = "{Bioformer: an efficient transformer language model for biomedical text mining}",
      journal = {arXiv preprint arXiv:2302.01588},
         year = {2023}
}
```
