
## Ranking(attention)

Use the baseline as the retrieval model to generate hundreds of candidates as input to the ranking model. Abandon the two-tower structure used in the retrieval model, and use the attention structure with stronger interaction between customer and item. For each candidate product, it is weighted with the purchased products of the specified user to generate a new customer embedding. Attached the personal information of the user and the information of the candidate product to the previous updated purchase history item forms the embedding of the designated candidate for the targeted user. Input the embedding into the network for training to generate the final logit. Compare it with the existing target to form a loss function to optimize the model.


- [0.00495](https://www.kaggle.com/code/mulahli/h-m-pytorch-baseline-retrieval-ranking?scriptVersionId=104135247)


Exploration:

1. The user purchases the product and the candidate uses the dot product method to generate weights. This method is not very interactive for the two. The network training method can be used to optimize the attention structure in the future. 

2. For the embedding of the final input network, the proportion of each part is very important, and then consider adjusting and optimizing the weight of each embedding to compose the final input embedding. 

3. For the network architecture, the MLP layer is currently used for training. Later plan to adjust the hyperparameters in the model and even change the use of layers to improve the accuracy of prediction.
