# Natural-Language-Processing
Language Model for Patronising and Condescending language recognition. \ 
Coursework for NLP course @Imperial College London.

## Data

All data description can be found in the [original paper data description](data/README.txt).

[Labeled Training Dataset](dontpatronizeme_pcl.tsv): contains paragraphs with a label from 0 (not containing PCL) to 4 (being highly patronizing or condescending) towards vulnerable communities.
It contains one instance per line with the following columns:
- <par_id>: unique id for each one of the paragraphs in the corpus.
- <art_id>: the document id in the original NOW corpus (News on Web: https://www.english-corpora.org/now/).
- <keyword>: the search term used to retrieve texts about a target community.
- <country_code>: ISO Alpha-2 country code for the source media outlet.
- <text>: the paragraph containing the keyword.
- <label>: an integer between 0 and 4, which reflects the level of PCL as a result of combined annotations of two annotators, with 0 (No PCL), 1 (borderline PCL) and 2 (contains PCL). The combined annotations have been used in the following graded scale:

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


## Model

[**'Language_Model'**](https://en.wikipedia.org/wiki/Language_model): model description.

**Model Hyperparameters**
- *parameter_name*: hyperparameter value and description.
- ...


## Example Usage
To automatically install requirements:
```console
../bin/pip3 install -r requirements.txt
```

To get a prediction:
```console
python3 ...
```

## Authors

- Asia Belfiore (*ab6124*)
    
    CID:02129867\
    Msc Advanced Computing,
    Imperial College London

- Ginevra Cepparulo (*gc1424*)
    
    CID: \
    Msc  ,
    Imperial College London

- Aslihan Găźlseren (*ag724*)
    
    CID: \
    Msc  ,
    Imperial College London
