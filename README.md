![books-collaborative-filtering](https://www.bromleyhouse.org/wp-content/uploads/2018/10/bhl-books.jpg)

<!-- [![FVCproductions](https://avatars1.githubusercontent.com/u/4284691?v=3&s=200)](http://fvcproductions.com) -->

# Books Collaborative Filtering

A ML collaborative filtering model to predict the rating a user would give to a particular book (from 0 to 5). The model can be used to reccomend books to individual users.

## Table of Contents 

- [Model Training](#Model-Training)
- [Model Understanding](#Model-Understanding)
- [Methods Used](#Methods-used)
- [Production](#production)

---

### Model Training
The model has been trained on the using the <a href="https://github.com/zygmuntz/goodbooks-10k" target="_blank">good-books-10k dataset</a>. The dataset contains 6M books ratings from 10,000 unique books coming from all kind of genres, periods and authors. The model was trained using fastai and is a a base dot model for collaborative filtering. The model uses embeddings and bias to reach better results.

The trained model reached a MSE (mean squared error) of 1.0067. Click <a href="https://github.com/Attol8/Books-collaborative-filtering/blob/master/Books-collab.ipynb">here</a> to access the notebook used for exploratory data Analysis and model training  

| Model             | Num of training items | Num of validation items | MSE          |
| -------------     | -------------         | -------------           |------------- |    
| EmbeddingDotBias  | 5.8M                  | 597k                    | 1.0067       |

### Model Understanding 

In order to beeter understand the model, it is decomposed in its parts through Excel. <a href="https://github.com/Attol8/Books-collaborative-filtering/blob/master/collab_filter.xlsx">collab_filter.xlsx</a> has three working sheets:

1. dotprod - takes a selected sample of books ratings (top 15 books and top 15 books) and makes prediction on ratings by doing the dot product of user embeddings and books embeddings. Embeddings are random initialized vectors on which we use Gradient descent to minimize loss.

2. goodreads_1hot - Here the NN layer is a matrix multiplication between one-hot encoded matrixes of inputs and the weight matrixes that we previously trained 

3. goodreads_emb - Here embeddings are just a lookup from an array of pretrained wights. This process is computationally less expensive than the previous one.

### Methods Used

* Machine Learning
* Data Visualization
* Predictive Modeling
* Deep Learning
* Data Mining

### Technologies 
* Python
* Pandas
* Jupyter
* Excel
* Fastai Library
