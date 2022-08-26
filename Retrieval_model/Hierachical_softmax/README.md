### Hierarchical softmax

Design a two-layer tree structure to generate logits. The middle nodes represent the prerequisite of the items. The leaf nodes represent the actual items. By training the weight of each branch, optimize the process of generating final logits and accelerate the training time. In order to get final probability for each item, the model must multiply all parent middle nodes' probability with the probability of the final node. Multiply all likelihoods  in a path together as a final probability.


- [0.00451](https://www.kaggle.com/code/tao58lee/h-m-pure-pytorch-baseline-hier-softmax?scriptVersionId=103239582)(4632.4s)


Exploration:

In the future, it is planned to adopt a more complex tree structure and use a deeper tree to generate logits so that the model can be better fitted and the prediction accuracy will be improved.
