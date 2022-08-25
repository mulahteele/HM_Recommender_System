### TDM

Simplified the part of the TDM model in which only uses customer embedding without the attention structure. Establish a tree, and the leaf of the tree represents each item. The middle node represents the category which helps us to find the most relevant item when tracking along the branches. Train the embedding of a tree using all customer history. If one customer bought some item in his purchase history then set the leaf of the item as a positive sample. Similarly, according to the positive sample, backtrack to find its parent’s node and all ancestors which also are set as positive samples. Randomly choose one negative sample each layer. Train the model until the model converges. 

Secondly, reconstruct a tree. using k-means to cluster the embedding of each layer. The number of cluster centers of each layer maintain the same. Put the closest centers in different layers in the same label order.

Retrain the embedding with the new interest tree until the model converges and re-aggregate a new tree. Repeating over and over again, finally we can obtain a more accurate interest tree.


- [0.00016](https://www.kaggle.com/code/tao58lee/h-m-pure-pytorch-baseline-2-layer-tdm?scriptVersionId=103956826)


Exploration:

Because the interest tree only has two layers and all categories only have 3K which results in some items can’t be classified correctly and the tree can’t perform better. If the middle layer has made some little error, the model will not choose the correct items any more. 

The next step is to try to use a deeper tree to express interest, so that the category can be subdivided more precisely. The relationship between the branches can be more obvious and the training is more targeted


