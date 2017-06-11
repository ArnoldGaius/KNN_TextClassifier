# KNN_TextClassifier-KNN文本分类器
Text Classifier based on Numpy

Sample Usage
----------------------
```python
>>> import KNN
    #load random Data,Labels
>>> dataMatrix,labels = loadData(feature_num = 4,rows = 10)
    #norm Data reduce influence of high ranges
>>> normDataSet = norm(dataMatrix)

    #predict K should be odd to avoid voting result like {('A',2),('B',2)} difficult choice. 
    #Parameter format classify(testData,TrainData,TrainData_Labels,K) 
    '''
        testData and TrainData should be 2-D list. row represents a text data. Columns represent feature values.
        TrainData_Labels should be a list like ['A','B','C'] an element represents a row of TrainData's class.
        K should be odd as I said before.
    '''        
>>> print classify([[1,2,3,4],[2],[3]], dataMatrix, labels, K=3)
    ['A', 'A', 'A']
    
    #predict
>>> print classify([['天气好','2','3','4'],['2'],['3']], dataMatrix, labels, K=3)
    ['B', 'A', 'A']
    
    #get transformed vector
>>> vector,vocabList = word2VectorMatrix([['1','2','3','4'],['2'],['3']])
>>> print vector
    [[ 1.  1.  1.  1.]
    [ 0.  0.  1.  0.]
    [ 0.  1.  0.  0.]]







