# HM_Recommender_System

## Retrieval Part

### Pure baseline
- 0.01850  (14767.7s)

Loss function: Binary cross entropy with logits


### Incorporate other features

- 0.01843

There may be some features as bias in this case. Consider in the future exploring the impact of different features on the accuracy of result prediction.


### Sampled softmax

Ground true labels + negative labels  = 300:    
- 0.01983 (7932.4s) (5 epoch)

Ground true labels + negative labels  = 300:     
- 0.01329 (14590.5s) (10 epoch)

Using the same number of epochs as the baseline doesn't reduce running time after sampled softmax.

Ground true label + negative label = 1000:     
- 0.01899 (5 epoch)

Considering the running time of the baseline, try to use sampled softmax method to accelerate the training process. The design idea is to only select some parts of the logits of all items after the dot product. In the dataset class, preprocess the get the corresponding target. The pair of target and shortened output compose the loss function for optimization.

Exploration:

Here is another discovery: by using this method, with more epochs of training, the prediction becomes more accurate in some optimal epoch. But afterwards predictions become inaccurate in some way. 
(Guess: The loss function used here is BCElosswithlogits, it can generate losses element-wise. If compared with a lot of items at one time, in this case(70K), the negative sample could be dominated. But using sampled softmax, the ratio of negative and positive samples are not as large as general softmax which results in the positive samples making a lot of sense. It's training with pertinence to grab the regulation of positive samples. Increasing the epoch may increase the negative samples in some way from a global perspective)


### Hierarchical softmax
- 0.00451 (4632.4s)

Design a two-layer tree structure. The middle nodes represent the prerequisite of the item. The leaf nodes represent the virtual item. By training the weight of each branch, optimize the process of generating final logits and accelerate the training time. For getting each item, the model must first get the middle node's probability and then get the probability of the final branch. Multiply the two likelihoods together as a final prediction.

