The DistilBERT model was proposed in the blog post [Smaller, faster, cheaper, lighter: Introducing DistilBERT, adistilled version of BERT](https://medium.com/huggingface/distilbert-8cf3380435b5), and the paper [DistilBERT, adistilled version of BERT: smaller, faster, cheaper and lighter](https://arxiv.org/abs/1910.01108). DistilBERT is a small, fast, cheap and light Transformer model trained by distilling BERT base. It has 40% less parameters than *bert-base-uncased*, runs 60% faster while preserving over 95% of BERT's performances as measured on the GLUE language understanding benchmark.

This model is a fine-tune checkpoint of [DistilBERT-base-cased](https://huggingface.co/distilbert-base-cased), fine-tuned using (a second step of) knowledge distillation on [SQuAD v1.1](https://huggingface.co/datasets/squad). 

# Training Details

## Training Data

The [distilbert-base-cased model](https://huggingface.co/distilbert-base-cased) was trained using the same data as the [distilbert-base-uncased model](https://huggingface.co/distilbert-base-uncased). The [distilbert-base-uncased model](https://huggingface.co/distilbert-base-uncased) model describes it's training data as: 

> DistilBERT pretrained on the same data as BERT, which is [BookCorpus](https://yknzhu.wixsite.com/mbweb), a dataset consisting of 11,038 unpublished books and [English Wikipedia](https://en.wikipedia.org/wiki/English_Wikipedia) (excluding lists, tables and headers).

To learn more about the SQuAD v1.1 dataset, see the [SQuAD v1.1 data card](https://huggingface.co/datasets/squad).

## Training Procedure

### Preprocessing

See the [distilbert-base-cased model card](https://huggingface.co/distilbert-base-cased) for further details.

### Pretraining

See the [distilbert-base-cased model card](https://huggingface.co/distilbert-base-cased) for further details. 

# Evaluation Results

As discussed in the [model repository](https://github.com/huggingface/transformers/blob/main/examples/research_projects/distillation/README.md)

> This model reaches a F1 score of 87.1 on the [SQuAD v1.1] dev set (for comparison, BERT bert-base-cased version reaches a F1 score of 88.7).	

# Limitations and Biases

**CONTENT WARNING: Readers should be aware that language generated by this model can be disturbing or offensive to some and can propagate historical and current stereotypes.**

Significant research has explored bias and fairness issues with language models (see, e.g., [Sheng et al. (2021)](https://aclanthology.org/2021.acl-long.330.pdf) and [Bender et al. (2021)](https://dl.acm.org/doi/pdf/10.1145/3442188.3445922)). Predictions generated by the model can include disturbing and harmful stereotypes across protected classes; identity characteristics; and sensitive, social, and occupational groups

Users (both direct and downstream) should be made aware of the risks, biases and limitations of the model.

# Inference samples

Inference type|Python sample (Notebook)
|--|--|
Real time|[sdk-example.ipynb](https://aka.ms/sdk-notebook-examples)
Real time|[question-answering-online-endpoint.ipynb](https://aka.ms/question-answering-online-endpoint-oss)

# Sample inputs and outputs

### Sample input

```json
{
    "input_data": {
        "question": "What's my name?",
        "context": "My name is John and I live in Seattle"
    }
}
```

### Sample output
```json
[
  "John"
]
```
