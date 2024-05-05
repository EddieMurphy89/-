# 基于朴素贝叶斯模型的钓鱼邮件检测

先解压email.zip放在源码所在文件夹。

然后代码就能直接运行。

------------------------------------------------------------------------------------------------------

这是一个使用朴素贝叶斯分类器进行垃圾邮件分类的Python脚本。下面是每个函数的详细解释：

createVocabList(dataSet): 这个函数接收一个数据集，然后创建一个包含所有不重复词条的列表，也就是词汇表。

setOfWords2Vec(vocabList, inputSet): 这个函数根据词汇表，将输入的词条列表转换为词集模型，也就是一个向量，向量的每个元素为1或0，表示词汇表中的词条是否在输入的词条列表中出现。

bagOfWords2VecMN(vocabList, inputSet): 这个函数也是将输入的词条列表转换为向量，但是它是词袋模型，如果词条在输入的词条列表中出现，那么对应的元素计数加一。

trainNB0(trainMatrix,trainCategory): 这个函数是朴素贝叶斯分类器的训练函数，它计算了每个词条在钓鱼类和非钓鱼类中出现的条件概率，以及文档属于钓鱼类的概率。

classifyNB(vec2Classify, p0Vec, p1Vec, pClass1): 这个函数是朴素贝叶斯分类器的分类函数，它根据训练函数计算的条件概率和类别概率，对输入的词条向量进行分类。

textParse(bigString): 这个函数接收一个大字符串，然后将其解析为字符串列表，主要是进行了中文分词和去除非汉字字符的操作。

spamTest(): 这个函数是测试函数，它首先读取钓鱼邮件和非钓鱼邮件，然后随机选择一部分邮件作为训练集，剩余的作为测试集，然后调用上述的训练函数和分类函数，对测试集进行分类，并计算错误率。

最后，如果这个脚本作为主程序运行，那么会调用spamTest()函数进行垃圾邮件分类的测试。
