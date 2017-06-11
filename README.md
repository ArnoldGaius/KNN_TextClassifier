[![PyPI version](https://img.shields.io/badge/python-2.7-blue.svg)](https://badge.fury.io/py/KNN_TextClassifier)
[![PyPI version](https://badge.fury.io/py/KNN_TextClassifier.svg)](https://badge.fury.io/py/KNN_TextClassifier)
# KNN_TextClassifier-KNN文本分类器
Text Classifier based on Numpy

Sample Usage
----------------------
```python
>>> import KNN_TextClassifier
    #load random Data,Labels
>>> dataMatrix,labels = KNN_TextClassifier.loadData(feature_num = 4,rows = 10)
    #norm Data reduce influence of high ranges
>>> normDataSet = KNN_TextClassifier.norm(dataMatrix)

    #predict K should be odd to avoid voting result like {('A',2),('B',2)} difficult choice. 
    #Parameter format classify(testData,TrainData,TrainData_Labels,K) 
    '''
        testData and TrainData should be 2-D list. row represents a text data. Columns represent feature values.
        TrainData_Labels should be a list like ['A','B','C'] an element represents a row of TrainData's class.
        K should be odd as I said before.
    '''        
>>> print KNN_TextClassifier.classify([[1,2,3,4],[2],[3]], dataMatrix, labels, K=3)
    ['C', 'C', 'C']
    
    #predict
>>> print KNN_TextClassifier.classify([['天气好','2','3','4'],['2'],['3']], dataMatrix, labels, K=3)
    ['C', 'A', 'C']
    
    #get transformed vector
>>> vector,vocabList = KNN_TextClassifier.word2VectorMatrix([['1','2','3','4'],['2'],['3']])
>>> print vector
    [[ 1.  1.  1.  1.]
    [ 0.  0.  1.  0.]
    [ 0.  1.  0.  0.]]
    
    #get transformed vocabList
>>> print vocabList
    ['1', '3', '2', '4']

```

Installation
----------------------
    $ pip install KNN_TextClassifier




