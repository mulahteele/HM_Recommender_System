
## Ranking(attention)

Use the baseline as the retrieval model to generate hundreds of candidates as input to the ranking model. Abandon the two-tower structure used in the retrieval model, and use the attention structure with stronger interaction between customer and item. For each candidate, it is weighted with the candidte embedding to the purchased products' embedding to generate a new customer embedding. Concatenated the personal information of the user and the information of the candidate to the previous updated new customer embedding to form the final embedding of the designated candidate for the targeted user. Input the embedding into the network for training to generate the final logit. Compare it with the existing target to form a loss function to optimize the model.


- [0.00495](https://www.kaggle.com/code/mulahli/h-m-pytorch-baseline-retrieval-ranking?scriptVersionId=104135247)


Exploration:

1. The iteraction of purchased items and the candidate uses the dot product method to generate. This method is not very interactive for the two parts. The network training method can be used to optimize the attention structure in the future. 

2. For the final concatenated embedding, the proportion of each part is very important. Then consider to adjust and optimize the weight of each embedding to compose the final embedding. 

3. For the network architecture, the MLP layer is currently used for training. Later plan to adjust the hyperparameters in the model or even change the usage of the MLP layer to improve the accuracy of prediction.
