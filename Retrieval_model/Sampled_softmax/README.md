### Sampled softmax

Considering the running time of the baseline, try to use sampled softmax method to accelerate the training process. The design idea is to only select some parts of the logits of all items after the dot product. In the dataset class, preprocess the get the corresponding target. The pair of target and shortened output compose the loss function for optimization.


Ground true labels + negative labels  = 300: 

- [0.01983](https://www.kaggle.com/code/mulahli/h-m-pure-pytorch-baseline-sampled-softmax-803a85?scriptVersionId=102914281)(7932.4s) (5 epoch)

Ground true labels + negative labels  = 300:

- [0.01329](https://www.kaggle.com/code/mulahli/h-m-pure-pytorch-baseline-sampled-softmax-803a85?scriptVersionId=102923197)(14590.5s) (10 epoch)

Using the same number of epochs as the baseline doesn't reduce running time after sampled softmax.

Ground true label + negative label = 1000:  

- [0.01899](https://www.kaggle.com/code/mulahli/h-m-pure-pytorch-baseline-sampled-softmax-803a85?scriptVersionId=102914405)(5 epoch)


Exploration:

Here is another discovery: by using this method, with more epochs of training, the prediction becomes more accurate in some optimal epoch. But afterwards predictions become inaccurate in some way. 
(Guess: The loss function used here is BCElosswithlogits, it can generate losses element-wise. If compared with a lot of items at one time, in this case(70K), the negative sample could be dominated. But using sampled softmax, the ratio of negative and positive samples are not as large as general softmax which results in the positive samples making a lot of sense. It's training with pertinence to grab the regulation of positive samples. Increasing the epoch may increase the negative samples in some way from a global perspective)
