# Review Network for Caption Generation

## Image Captioning on MSCOCO

You can use the code in this repo to genearte a MSCOCO evaluation server submission with CIDEr=0.96+ with just a few hours.

No fine-tuning required. No fancy tricks. Just train three end-to-end review networks and do an ensemble.

+ Feature extraction: 2 hours in parallel
+ Single model training: 6 hours
+ Ensemble model training: 30 mins
+ Beam search for caption generation: 3 hours in parallel

Below is a comparison with other state-of-the-art systems (with according published papers) on the MSCOCO evaluation server:

| Model | BLEU-4 | METEOR | ROUGE-L | CIDEr | Fine-tuned | Task specific features |
|----|----|----|----|----|----|----|
| Attention | 0.537 | 0.322 | 0.654 | 0.893 | No | No |
| MS Research | 0.567 | 0.331 | 0.662 | 0.925 | No | Yes |
| Google NIC | 0.587 | 0.346 | 0.682 | 0.946 | Yes | No |
| Semantic Attention | **0.599** | 0.335 | 0.682 | 0.958 | No | Yes |
| Review Net | 0.597 | **0.347** | **0.686** | **0.969** | No | No |

In the diretcory `image_caption_online`, you can use the code therein to reproduce our evaluation server results.

In the directory `image_caption_offline`, you can rerun experiments in our paper using offline evaluation.

## Code Captioning

Predicting comments for a piece of source code is another interesting task.
In the repo we also release a dataset with train/dev/test splits, along with the code of a review network.

Check out the directory `code_caption`.

Below is a comparison with baselines on the code captioning dataset:

| Model | LLH | CS-1 | CS-2 | CS-3 | CS-4 | CS-5 |
|----|----|----|----|----|----|----|
| LSTM Language Model | -5.34 | 0.2340 | 0.2763 | 0.3000 | 0.3153 | 0.3290 |
| Encoder-Decoder | -5.25 | 0.2535 | 0.2976 | 0.3201 | 0.3367 | 0.3507 |
| Encoder-Decoder (Bidir) | -5.19 | 0.2632 | 0.3068 | 0.3290 | 0.3442 | 0.3570 |
| Attentive Encoder-Decoder (Bidir) | -5.14 | 0.2716 | 0.3152 | 0.3364 | 0.3523 | 0.3651 |
| Review Net | **-5.06** | **0.2889** | **0.3361** | **0.3579** | **0.3731** | **0.3840** |


## References

This repo contains the code and data used in the following paper:

[Review Network for Caption Generation](https://arxiv.org/abs/1605.07912)

Zhilin Yang, Ye Yuan, Yuexin Wu, Ruslan Salakhutdinov, William W. Cohen

NIPS 2016


