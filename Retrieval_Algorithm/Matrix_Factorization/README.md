## Matrix Factorization


Matrix factorization aims to construct a matrix of user embedding and item embedding by optimizing the iteraction of two objects according to the purchasing history. Firstly, get the number of times each user purchased a certain product, and get the embeddings of the user and the product. The composition of the user-item matrix is optimized by comparing the actual number of purchases and the dot product of the user embedding and the item embedding, by which form a loss function. Finally, use the user embedding and all item embeddings to generate all expected purchase times and make final predictions after sorting.


- [0.00565](https://www.kaggle.com/code/tao58lee/matrix-factorization?scriptVersionId=98660105)
