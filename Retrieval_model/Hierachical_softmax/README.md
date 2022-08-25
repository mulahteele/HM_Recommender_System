### Hierarchical softmax

- [0.00451](https://www.kaggle.com/code/tao58lee/h-m-pure-pytorch-baseline-hier-softmax?scriptVersionId=103239582)(4632.4s)

Design a two-layer tree structure. The middle nodes represent the prerequisite of the item. The leaf nodes represent the virtual item. By training the weight of each branch, optimize the process of generating final logits and accelerate the training time. For getting each item, the model must first get the middle node's probability and then get the probability of the final branch. Multiply the two likelihoods together as a final prediction.


Exploration:

In the future, it is planned to adopt a more complex tree structure and use a deeper tree to generate logits so that the model can be better fitted and the prediction accuracy will be improved.
