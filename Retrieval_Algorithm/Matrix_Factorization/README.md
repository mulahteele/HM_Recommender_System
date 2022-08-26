## Matrix Factorization


Matrix factorization aims to construct a matrix of user embedding and item embedding by training the embedding according to the purchasing history. Firstly, get the number of times each user purchased a certain product, and get the embedding of the user and the product. The composition of the user-item matrix is optimized by comparing the actual number of purchases and the dot product of user embedding and item embedding to form a loss function. Finally, use user embedding and all item embeddings to generate all possible purchase times and make predictions after sorting.


- [0.00565](https://www.kaggle.com/code/tao58lee/matrix-factorization?scriptVersionId=98660105)
