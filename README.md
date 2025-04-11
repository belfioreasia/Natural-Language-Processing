# Natural-Language-Processing
Language Model for Patronising and Condescending language recognition. \ 
Coursework for NLP course @Imperial College London. Full Research Report can be found [here](report.pdf).

## Data

All data description can be found in the [original paper data description](data/README.txt).

[Labeled Training Dataset](dontpatronizeme_pcl.tsv): contains paragraphs with a label from 0 (not containing PCL) to 4 (being highly patronizing or condescending) towards vulnerable communities.
It contains one instance per line with the following columns:
- "par_id": unique id for each one of the paragraphs in the corpus.
- "art_id": the document id in the original NOW ([News on Web](https://www.english-corpora.org/now/)) corpus.
- "keyword": the search term used to retrieve texts about a target community.
- "country_code": ISO Alpha-2 country code for the source media outlet.
- "text": the paragraph containing the keyword.
- "label": an integer between 0 and 4, which reflects the level of PCL as a result of combined annotations of two annotators, with 0 (No PCL), 1 (borderline PCL) and 2 (contains PCL). The combined annotations have been used in the following graded scale:

0 -> Annotator 1 = 0 AND Annotator 2 = 0
1 -> Annotator 1 = 0 AND Annotator 2 = 1 OR Annotator 1 = 1 AND Annotator 2 = 0
2 -> Annotator 1 = 1 AND Annotator 2 = 1
3 -> Annotator 1 = 1 AND Annotator 2 = 2 OR Annotator 1 = 2 AND Annotator 2 = 1
4 -> Annotator 1 = 2 AND Annotator 2 = 2

Following the experiments reported in the paper, we grouped the 5 numeric labels into the binary classification:
- {0,1}   = No PCL (0)
- {2,3,4} = PCL (1)

## Requirements

The project is written in `python`. The following third party packages are required to ensure full project functionality:

- [**numpy**](https://numpy.org/doc/stable/index.html): python package for mathematical and scientific computing. Actively maintained (Last Updated: December 2024), open-source and commercially supported.

- [**pandas**](https://pandas.pydata.org/): python package for data analysis, particularly suitable for handling relational and labelled data. Actively maintained (Last Updated: September 2024) and open-source.

- [**scikit-learn**](https://scikit-learn.org/stable/index.html): python package for data modeling and machine learning algorithms. Actively maintained (Last Updated: January 2025), open-source and commercially supported.

All requirements (along with the used versions) can be found in the [requirements.txt](requirements.txt) file.


## Models

[**'Language Model'**](models/Improved_RoBERTa.ipynb): RoBERTa-based Transformer architecture. It uses 10% Synonym Replacement via WordNet and Backtranslation using MarianMT (20% of paragraphs from English-German-English). The inputs were pre-processed in order to include the community label at the start of each sentence.

[**'SVM'**](models/NLP_Improved_svm.ipynb): Support Vector Machine (SVM) with Regularization parameter (C)=10, ’scale’ (gamma) kernel coefficient and ’rbf’ kernel. It uses TF-IDF weighted Bag-of-Words representation of the paragraphs as input.

[**'BiLSTM'**](models/BiLSTM.ipynb): 2-layer bi-direcional Long-Short Term Memory (LSTM) model with 20 units and dropout rate of 0.25% each. It uses 300-dimensional Word2Vec skip-gram word embeddings (trained on the Google News corpus) as input.


## Authors

- Asia Belfiore (*ab6124*)
- Ginevra Cepparulo (*gc1424*)
- Aslihan Gülseren (*ag724*)
