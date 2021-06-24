# ChineseBLUE, the Chinese Biomedical Language Understanding Evaluation benchmark
[![License](https://img.shields.io/github/license/alibaba-research/ChineseBLUE?style=flat-square)](https://github.com/alibaba-research/ChineseBLUE/blob/master/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/alibaba-research/ChineseBLUE?style=flat-square)](https://github.com/alibaba-research/ChineseBLUE/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/alibaba-research/ChineseBLUE?style=flat-square&color=blueviolet)](https://github.com/alibaba-research/ChineseBLUE/network/members)

**We recommmend to use our recent released [CBLUE benchmark](https://github.com/CBLUEbenchmark/CBLUE) which includes a collection of natural language understanding tasks including named entity recognition, information extraction, single-sentence/sentence-pair classification, and an associated online platform for model evaluation, comparison, and analysis.**

This repository includes the data of the WSDM 2020 Healthcare Day paper [Conceptualized Representation Learning for Chinese Biomedical Text Mining](https://arxiv.org/pdf/2008.10813.pdf).

## Introduction

ChinesseBLUE benchmark consists of different biomedicine text-mining tasks with corpora.
These tasks cover a diverse range of text genres (biomedical web data and clinical notes), dataset sizes, and degrees of difficulty and, more importantly, highlight common biomedicine text-mining challenges.

MC-BERT is a novel conceptualized representation learning approach for the medical domain. First, we use a different mask generation procedure to mask spans of tokens, rather than only random ones. We also introduce two kinds of masking strategies, namely whole entity masking and whole span masking.  Finally, MC-BERT split the input document into segments based on the actual "sentences" provided by the user as positive samples and sample random sentences from other documents as negative samples for the next sentence prediction.  

![c-bert model](figs/c_bert_model.jpg)


## Tasks

| Dataset          | Train |  Dev | Test | Task                    | Metrics             | Domain     |
|-----------------|------:|-----:|-----:|-------------------------|---------------------|------------|
| [cEHRNER](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cEHRNER/cEHRNER.tar.gz) |  914  | 44   | 41  | Name Entity Recognition    | F1             | Clinical   |
| [cMedQANER](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedQANER/cMedQANER.tar.gz)         |  1,673 | 175   | 215  | Name Entity Recognition    | F1             | Medical   |
| [cMedQQ](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedQQ/cMedQQ.tar.gz) | 16,071  |1,793   | 1,935  | Paraphrase Identification   | F1             | Medical   |
| [cMedQNLI](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedQNLI/cMedQNLI.tar.gz) |  80,950  |  9,065  |9,969   | Question Natural Language Inference  | F1             | Medical   |
| [cMedQA](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedQA/cMedQA.tar.gz) | 49,719 | 5,475   |6,149 | Question Answering    | F1             |Medical    |
| [cMedIR](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedIR/cMedIR.tar.gz) |  80,000 |  10,000  | 10,000  | Information Rerival    |     MRR       |Medical    |
| [cMedIC](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedIC/cMedIC.tar.gz) |  1,683  | 123  |84  |  Intent Classification   |        F1      | Medical   |
| [cMedTC](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/cMedTC/cMedTC.tar.gz) | 1,683   | 123   | 84  |  Sentence Classification   |       F1       | Medical   |
| [CMDD](http://www.sdspeople.fudan.edu.cn/zywei/data/emnlp2019-cmdd.zip) | 1240 | 412 | 412 | Symptom Diagnosis |       F1       | Dialogue |


### Named Entity Recognition (NER) 

Named entity recognition aims to recognize various entities, including diseases, drugs, syndromes, etc.   The **cEHRNER** dataset labeled from the Chinese electronic health records and the **cMedQANER** dataset labeled from Chinese community question answering is chosen.

### Paraphrase Identification (PI)

Paraphrase Identification aims to identify whether two sentences express the same meaning. We use **cMedQQ**, which consists of search query pairs. 

### Question Natural Language Inference (QNLI)

Question natural language inference aims to identify   whether the answer corresponds to the question in the question-answering pair.  We use **cMedQNLI**, which consists of question-answer pairs. 

### Question Answering (QA)

Question answering can be approximated as ranking candidate answer sentences based on their similarity. We assign 0,1 labels to the QA pairs, which convert to the binary classification problem. We use **cMedQA**  released from the paper  "[Multi-Scale Attentive Interaction Networks for Chinese Medical Question Answer Selection](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8548603)", which consists of questions and their answers.

### Information  Retrieval (IR)

Information retrieval aims to retrieve most related documents given search queries. IR can be regarded as a ranking task.   We use the **cMedIR** dataset,  which consists of queries with multiple documents and their relative scores. 

### Intent Classification (IC)

Intent classification aims to assign intent labels to the queries, which can be regarded as multiple label classification tasks. We use the **cMedIC** dataset, which consists of queries with three intent labels (e.g., no intention, weak intention, and firm intention).

### Text Classification (TC)

Text classification aims to assign multiple labels to the sentence. We use the **cMedTC** dataset, which consists of biomedical texts with multiple labels.

### Symptom Diagnosis 

Symptom diagnosis is a challenging yet profound problem in natural language processing. We use the **CMDD** dataset released from the paper"[Enhancing Dialogue Symptom Diagnosis with Global Attention and Symptom Graph](https://www.aclweb.org/anthology/D19-1508.pdf)".

### Relation extraction (RE)
Coming soon. 

### Datasets

All datasets can be downloaded at [ChineseBLUE1.0](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/data/ChineseBLUE.tar.gz)

### Pretrained Model

All pre-trained models can be downloaded at [MC-BERT](https://drive.google.com/open?id=1ccXRvaeox5XCNP_aSk_ttLBY695Erlok). 


## Citing Chinese BLUE

Paper will be released soon.

*  [Ningyu Zhang](https://zxlzr.github.io), Qianghuai Jia, Kangping Yin, Liang Dong, Feng Gao, Nengwei Hua. [Conceptualized Representation Learning for Chinese Biomedical Text Mining](https://raw.githubusercontent.com/alibaba-research/ChineseBLUE/master/paper.pdf)

```
@article{zhang2020conceptualized,
  title={Conceptualized Representation Learning for Chinese Biomedical Text Mining},
  author={Zhang, Ningyu and Jia, Qianghuai and Yin, Kangping and Dong, Liang and Gao, Feng and Hua, Nengwei},
  journal={arXiv preprint arXiv:2008.10813},
  year={2020}
}
```

## Acknowledgments

We are also grateful to the authors of [BERT](https://github.com/google-research/bert)  and [wwm-BERT](https://github.com/ymcui/Chinese-BERT-wwm)  to make the data and codes publicly available. We are also grateful to the authors of paper "[Enhancing Dialogue Symptom Diagnosis with Global Attention and Symptom Graph](https://www.aclweb.org/anthology/D19-1508.pdf)"  and  "[Multi-Scale Attentive Interaction Networks for Chinese Medical Question Answer Selection](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8548603)"  who released the dataset [CMDD](http://www.sdspeople.fudan.edu.cn/zywei/data/emnlp2019-cmdd.zip) and [cMedQA2](https://github.com/zhangsheng93/cMedQA2). 


## Disclaimer
This project is not the official product of Alibaba. The information produced on this website is not intended for direct diagnostic use or medical decision-making without review and oversight by a clinical professional. Individuals should not change their health behavior solely on the basis of information produced on this website.   If you have questions about the information produced on this website, please see a health care professional. 

The experimental results presented in the technical report only indicate the performance under the specific data set and super-parameter combination and do not represent the essence of each model. The experimental results may change due to random number seeds and computing devices. The content of this project is for technical research purposes only and is not intended to be a conclusive basis. The user may use the model arbitrarily within the scope of the license, but we are not responsible for any direct or indirect damages resulting from the use of the content of the project.
