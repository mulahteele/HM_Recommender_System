# HM_Recommender_System

## Project Introduction

- [H&M Personalized Fashion Recommendations](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/overview)

For this challenge you are given the purchase history of customers across time, along with supporting metadata like various features of products and users, and the images of products. Your challenge is to predict what articles each customer will purchase in the 7-day period immediately after the training data ends.

### Referenced papers

- [Deep Neural Networks for YouTube Recommendations](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45530.pdf)
- [Learning Tree-based Deep Model for Recommender Systems(TDM)](https://arxiv.org/pdf/1801.02294.pdf)
- [Deep Interest Network for Click-Through Rate Prediction(DIN)](https://arxiv.org/pdf/1706.06978.pdf)


2-stage recommender system

## Retrieval Part

The first part of the recommendation requires the recall of the all items which needs to select a reasonably relevant set that contains the items the user will eventually engage with. This stage will select thousands or hundreds of candidates from all millions or even tens of millions of items to simplify the problem.

Firstly, use different collaborative filtering methods to retrieve items. Afterwards, focus on the neural network adopting the two-tower structure to extract the embedding features of different items to train the model optimizing the prediction of the overall model.

### Retrieval Algorithm

- [Item-Item](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_Algorithm/Item-Item_collaborative_filtering)
- [User-User](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_Algorithm/User-User_collaborative_filtering)
- [Matrix_Factorization](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_Algorithm/Matrix_Factorization)


### Retrieval Model

- [Sampled_softmax](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_model/Sampled_softmax)
- [Hierachical_softmax](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_model/Hierachical_softmax)
- [2-layer TDM](https://github.com/mulahteele/HM_Recommender_System/tree/main/Retrieval_model/2_layer_TDM)


## Ranking Part

The role of the ranking model is to rank the candidates generated by the retrieval model and select the most likely product as the final prediction. Compared with the retrieval model, the ranking model can make more detailed comparisons, because the data involved is much less than the retrieval model, resulting in more accurate prediction results.

- [Attention](https://github.com/mulahteele/HM_Recommender_System/tree/main/Ranking_model)
