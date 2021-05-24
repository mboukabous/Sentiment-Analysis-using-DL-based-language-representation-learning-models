# In progress

# Sentiment Analysis (SA) using Deep Learning-based language representation learning models

## Introducation (English)
Deep learning (DL) approaches use various processing layers to learn hierarchical representations of data. Recently, many methods and designs of natural language processing (NLP) models have shown significant development, especially in text mining and analysis. For learning vector-space representations of text, there are famous models like Word2vec, GloVe, and fastText. In fact, NLP took a big step forward when BERT and recently GTP-3 came out.
Deep Learning algorithms are unable to deal with textual data in their natural language data form which is typically unstructured information; they require special representation of data as inputs instead. Usually, natural language text data needs to be converted into internal representations form that DL algorithms can read such as feature vectors, hence the necessity to use representation learning models. These models have shown a big leap during the last years. Their set ranges from the methods that embed words into distributed representations and use the language modeling objective to adjust them as model parameters (like Word2vec, fastText, and GloVe), to recently transfer learning models (like ELMo, BERT, ULMFiT, XLNet, and GPT-2). These last use larger corpora, more parameters, more computing resources, and instead of assigning each word with a fixed vector, they use multilayer neural networks to calculate dynamic representations for the words according to their context, which is especially useful for the words with multiple meanings.

## Introducation (Francais)
Le traitement automatique du langage naturel (NLP=Natural Language Processing) vise à convertir le langage humain en une représentation formelle en utilisant différentes techniques de calcul. Ce domaine progresse rapidement en raison de l'intérêt croissant pour les communications homme-machine, de la grande quantité de données textuelles stockées sur le Web, des puissants systèmes informatiques et des algorithmes améliorés. En effet, les algorithmes et architectures d'apprentissage en profondeur (DL=Deep Learning) ont fait des progrès remarquables ces dernières années dans les domaines de l'analyse de texte, cependant il nécessite une représentation spéciale des données en tant qu'entrées. 
À cet égard, les modèles d'apprentissage de la représentation du langage ont fait un grand saut au cours des dernières années, allant de méthodes qui incorporent les mots dans des représentations distribuées et utilisent l'objectif de modélisation du langage pour les ajuster en tant que paramètres de modèle comme Word2vec, GloVe, et fastText, à l'apparition de modèles d'apprentissage par transfert comme BERT, ELMo, ULMFiT, GPT-2 et XLNet qui utilisent des corpus plus grands, plus de paramètres, plus de ressources informatiques, et au lieu d’affecter à chaque mot un vecteur fixe, ils utilisent des réseaux de neurones multicouches pour calculer les représentations dynamiques des mots en fonction de leur contexte.

## Language Representation Learning Models
One of the important tasks in NLP is the learning of vector representations of text, as deep learning algorithms require representing their input entries in a vector format.

#### Neural Word Embeddings
***- [Word2vec](https://arxiv.org/abs/1301.3781)*** is an unsupervised learning algorithm that consists of a group of related models used for word embeddings generation. It is based on three-layer neural networks and seeks to learn the vector representations of words composing a text, so that words that share similar contexts are represented by close digital vectors. Word2Vec has two neural architectures, called Continuous Bag-of-Words (CBOW) and Skip-Gram. CBOW receives as input the context of a word, i.e., the terms surrounding it in a sentence, and tries to predict the word in question. Skip-Gram does exactly the opposite: it takes a word as input and tries to predict its context.

***- [fastText](https://arxiv.org/abs/1607.04606)*** is a Facebook's AI library for efficient learning of sentences classification and word embeddings. It supports multiprocessing during training and allows to create an unsupervised or supervised learning algorithm to obtain vector representations of words and sentences. fastText uses a neural network for word embeddings and supports training continuous bag of words (CBOW) or skip-gram model. It can be used as an initializer for transfer learning.

***- [Glove](https://www.aclweb.org/anthology/D14-1162)*** is an unsupervised learning algorithm to obtain word vector representations. This is accomplished by mapping words in a meaningful space where the distance between words is related to semantic resemblance. Training is performed using an underlying count-based model on the aggregated global word to word co-occurrence matrix within a text corpus, and the subsequent representations display interesting linear substructures in the word vector space. It combines the features of two sets of models, namely the local context window approaches and the global matrix factorization.

#### Transfer Learning Techniques
***- [ELMo (Embeddings from Language Models)](https://arxiv.org/abs/1802.05365)*** is a pre-trained biLSTM (bidirectional LSTM) language model. Word embeddings is calculated by taking a weighted score of the hidden states from each layer of the LSTM. Weights are learned with downstream model parameters for a particular task, but LSTM layers are kept constant. Thus, the same word under different contexts can have different word vectors.

***- [BERT (Bidirectional Encoder Representations from Transformers)](https://arxiv.org/abs/1810.04805)*** is another language representation learning model that uses an attention transformers mechanism to learn the contextual relations between words in a text instead of bidirectional LSTMs to encode context which shows that pre-training transformer networks on a masked language modeling objective leads to even better performance by precisely adjusting the transformer weights  over a wide range  of NLP tasks.

***- [RoBERTa (A Robustly Optimized BERT Pretraining Approach)](https://arxiv.org/abs/1907.11692)*** is an optimized model resulting from analysis of Google's BERT training model and the identification of several changes to the training procedure that enhance its performance by Facebook AI and the University of Washington researchers. Specifically, these researchers used a novel and bigger dataset for training, trained the model over far more epochs, and removed the next sequence prediction training objective.

***- [ALBERT (A Lite BERT for Self-supervised Learning of Language Representations)](https://arxiv.org/abs/1909.11942)*** is a “Lite” version of BERT, this model architecture includes two parameter-reduction methods: cross-layer parameter sharing and factorized embeddings parameterization. Furthermore, the proposed method contains a self-supervised loss for the sentence-order prediction.

***- [ULMFiT (Universal Language Model Fine-Tuning for Text Classification)](https://arxiv.org/abs/1801.06146)*** is a transfer learning method that can be applied to NLP. It uses a regular 3-layer LSTM architecture for either pre-training and fine-tuning tasks. ULMFiT consists of three steps: General-domain language model (LM) pertaining (pertaining language model on a large general-domain corpus), target task LM fine-tuning (the LM fine-tuned on the data of the target task), and the target task classifier fine-tuning (fine-tuning the classifier).

***- [XLNet](https://arxiv.org/abs/1906.08237)*** is a generalized autoregressive (AR) pertaining method that uses the context word to predict the next word which is constrained to a unidirectional context, either backward or forward. Although, XLNet learns from bidirectional context using Permutation Language Modeling. It also influences the best of both AR language modeling and autoencoders while avoiding their limitations.

***- [GPT-2 (Generative Pretrained Transformer 2 - successor of GPT)](https://openai.com/blog/better-language-models)*** follows the OpenAI GPT model with a few architecture modifications. It consists of a big transformer-based language model with 1.5 billion parameters, trained with the objective of the prediction of the next word, given all previous words in a text. And unlike the previous models that require pre-training and fine-tuning, there is no fine-tuning step for GPT-2.


## Dataset
Dataset used in experiments was combined from CARER-Emotion, DailyDialog, CrowdFlower, and Isear to create a rich dataset with 5 labels: anger (5k sentences), joy (26k sentences), sad (13k sentences), fear (3.6k sentences), and neutral (94k sentences). The used texts consist of tweets, dialog utterances, and short messages as shown in the table bellow.
| Dataset | Year | Content | Number of sentences | Emotion categories |
| --- | --- | --- | --- | --- |
| [CARER – Emotion](https://www.aclweb.org/anthology/D18-1404) | 2018 | Tweets | 20k | Anger, anticipation, disgust, fear, joy, sadness, surprise, and trust |
| [DailyDialog](https://arxiv.org/abs/1710.03957) | 2017 | Dialogues | 102k | Neutral, joy, surprise, sadness, anger, disgust, and fear |
| [CrowdFlower](https://data.world/crowdflower/sentiment-analysis-in-text) | 2016 | Tweets | 40k | Empty, sadness, enthusiasm, neutral, worry, surprise, love, fun, hate, happiness, boredom, relief, anger |
| [Isear](https://pubmed.ncbi.nlm.nih.gov/8195988/) | 1994 | Emotion situations | 7.5k | Joy, fear, anger, sadness, disgust, shame, guilt |

## Results
| Algorithm | Validation Accuracy | Validation Loss | Precision | Recall | F1-score | Training Time | Number of parameters|
| --- | --- | --- | --- | --- | --- | --- | --- |
| Word2vec | 0.8452 | 0.4178 | 0.8410 | 0.8453 | 0.8391 | Step: 63 ms, Epoch: 222s, Total: 2472s | Trainable: 440,581, Non-Trainable: 11 060 100 |

## Discussion (English)


## Discussion (Francais)
