---
description: >-
  Pre-trained vectors for profiles, jobs, HR documents and more to build quickly
  your own HR AI models.
---

# Embedding API

The ‘_**Profile & Job Embedding**_’ model analyzes the output of ‘Parsing’ and ‘Revealing’ layers and returns numerical vectors that represent a profile or job given as an input in a 1024-dimensional space. 

The vector representation is computed by using the same **HrFlow.ai** technology used for ‘Scoring’ and ‘Reasoning’ layers. The vectors of similar profiles or jobs will be close to each other in the 1024-dimensional space. The ‘Profile & Job Embedding’ model can be used for organizing to unleash endless uses cases. 

Now on, your AI experts Developers can focus on building great models instead of spending 90% of their time on pre-processing and vectorization.

| Embedding \(Vectors\) | Dimension |
| :--- | :--- |
| Profile2vec | 1024 |
| Experience2vec | 1024 |
| Education2vec | 1024 |
| Skills2vec | 1024 |
| Job2vec | 1024 |

Our Embedding API offers several encoding levels, particularly when it comes to profiles, it can be a Profile Encoder _**Profile2vec**_ or an Encoder Section \(_**Experience2vec**_,  _**Education2vec**_, _**Skills2vec**_\).

![Example of Profile Encoder &quot;Profile2vec&quot; \(grouped by the profile job category\) ](https://lh3.googleusercontent.com/JXagdsThZxaEKwjE83-QrJXjB1r1tk2-KmdBzb94X_a238-5bNtwHuDi-PUA4_cVBkpaCie1uil6lPDNhdggpZhkgiZBYQGe4iKRRGo13XvyYgzuG9Vw_fv72LiYrg2am9MIrPnkwlQ)



![Example of Section Encoder &quot;Experience2vec&quot; \(grouped by the profile job category\) ](https://lh4.googleusercontent.com/cLvklbMDn7YyRNAZjZJ7KeYGnam3XoZTGeV6ERvwkRM2VDerwCmBkoUZpj36MMXXHSHICpSZZH0zS4iygt0X_hJ-nhaxud0F3ZWUEhNLiO7IX7U1o_MZN2Ouy_QEnY2P6ytxZOZZAAk)

## Why you should choose **our Embedding ?**

### Features Workflow

![Embedding Workflow](../.gitbook/assets/image%20%281%29.png)

* **Tokenization :** Our method of tokenization gives our models additional advantages in terms of making them less prone or prone to typing errors by leveraging  information on _**subwords**_ and _**multigrams**._
* **Vectorization** : Our vectorization method consists of a hierarchy of levels, a first one at the word level by using our in-house pre-trained _**word embeddings**_ on the world largest HR entities dataset, then a second one for _**encoding paragraphs**_ \(sections in documents\) based on Natural Language Processing state of the art models.



### **HrFlow.ai Vs Alternatives**

Document embedding is the operation that consists of representing a document by a dense fixed length vector.

![](../.gitbook/assets/screenshot-2020-04-16-at-08.17.00.png)

| **Embedding** | _Bag-of-words_ | **Topic modelling** | n-gram embeddings | **Encoder-decoder** | HrFlow |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Multilingual |        x  |        x  |        x  | Can be trained in a cross-lingual approach | Use multilingual Word Embeddings  |
| Sub-word information |        x  |        x  |       x | Depends on the world-level embedding used |       yes |
| HR Context Awareness |        x  |        x  |        x  |        x  |       yes |

