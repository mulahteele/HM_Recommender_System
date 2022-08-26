### User-User collaborative filtering

The User-User method makes recommendations by comparing the similarity of different users. First, a dictionary of user purchase records is established. When making predictions, first get the purchase record vector of this user. Use the vectors of purchase records for different users as an indicator to calculate the similarity of users. After getting the first few most similar users, the most popular products among these users are extracted as the final recommended products for targeted customers.

-[0.00280](https://www.kaggle.com/code/tao58lee/h-m-user-user-collaborative-filtering?scriptVersionId=98033887)
