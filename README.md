# mathAI
一个拍照做题程序。输入一张包含数学计算题的图片，输出识别出的数学计算式以及计算结果。
![image](https://github.com/Roujack/mathAI/blob/master/test.png)

整个程序使用python实现，具体处理流程包括了图像预处理、字符识别、数学公式识别、数学公式语义理解、结果输出。

本程序使用opencv对输入的图像进行预处理，并将字符裁剪出来再归一化成固定大小的矩阵。我在TensorFlow上实现了一个lenet5
的卷积神经网络用来识别数学字符，训练使用CHROME数据集。对于数学公式的识别，主要是将识别出的独立的字符组织成计算机能够
理解的数学公式（这里的数学公式就是纯字符的可求解的数学计算题）。大概的方法是使用编译原理的算符优先法和递归下降法进行实现。
然后根据属性文法的值传递思想，将数学公式的值计算出来。最后使用python的matlibplot库把计算过程和答案打印出来。

优点：这是一整套拍照做题的算法框架，同时能够处理多种多样的计算题，目前市面上还没有看到实现。OCR技术如此成熟的今天字符识别
已经不算有挑战的东西了。
缺点：字符空间关系判断只用了人类启发式规则，图像预处理不够鲁棒，数学公式的结构识别算法不够完美（可以考虑使用二维文法来做）。
系统还有很大的提升空间。

自我评价：这本来是一个很有野心的project，因为它试图解决所有的我们遇到的数学题。更一般的是，我试图实现一个演算系统，
在这个系统里，输入一些规则（公理），以及已知条件，我们希望它能够推出一些结论出来。但是我发现这是一个很难的问题。
最近的学习结论告诉我，一方面循环不变式的寻找无法自动化，另一方面演算的时间和空间复杂度太高（可以参考prolog语言的实现）。

什么是智能？是现在的机器学习吗？我觉得不像。SVM是最大化函数间隔的算法，神经网络是寻找损失函数局部最优解的过程。这些技术只是数学层面的优化。
还是某种推理能力？我不知道。如果给它一些演算规则，和一些具有现实意义的符号，再加上一些公理，它能够演算出一些结论，这个结论具有现实意义，
是不是就意味着智能？我觉着是的，不过很难实现。据说吴文俊采用了自动化的方法证明了三角几何的结论。

我们的意识或者思维到底是什么东西？信息在大脑里面到底是如何表示的？我们为什么具有泛华的学习能力？一方面脑认知科学在求索，一方面计算科学也在求索。
我希望意识是能够认识物质的，并在最终达到越来越完美的过程。这才是科研的意义。我愿一直去寻找真理。