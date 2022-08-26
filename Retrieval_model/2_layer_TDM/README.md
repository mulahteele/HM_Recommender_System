### TDM

Simplified the part of the TDM model in which only uses customer embedding without the attention structure. Establish an interest tree, and the leaves of the tree represents items. The middle node represents the categories which helps us to classify the relevant items when tracking along the branches. Train the embedding of a tree using all customer history. If one customer bought one item in his purchase history then set the leaf of the item as a positive sample. Similarly, according to the positive sample, backtrack to find its parent’s node and all ancestors which also are set as positive samples. Randomly choose one negative sample in each layer. Train the model until the model converges. 

Secondly, reconstruct a tree. using k-means to cluster the embedding of each layer. The number of cluster centers of each layer maintain the same. Put the closest centers in different layers in the same label order.

Retrain the embedding with the new interest tree until the model converges and re-aggregate a new tree. Repeating this process over and over again, finally we can obtain a more accurate interest tree.


- [0.00016](https://www.kaggle.com/code/tao58lee/h-m-pure-pytorch-baseline-2-layer-tdm?scriptVersionId=103956826)


Exploration:

Because the interest tree only has two layers and only have 3K categories which results in some items can’t be classified correctly. Therefore the tree can’t perform better. If the middle layer made a little error, the model will not choose the correct item any more. 

The next step is to try to use a deeper tree to express interests, so that the category can be subdivided more precisely. The relationship between the branches can be more obvious and the training is more targeted


