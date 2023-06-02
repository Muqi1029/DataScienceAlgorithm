## 1. Background

In modern times, there are a lot of near-duplicate objects around our life, such as mirrors that have almost the same content but differ in information about the host and about other mirrors. We want to find these similar objects. But there may be far too many pairs of items to test each pair for their degree of similarity, even if computing the similarity of any pair can be made very easily. However, often we want only the most similar pairs or all pairs that are above on pairs that are likely to be similar without investigating every pair. That concern motivates a technique called **"locality-sensitive hashing"**, for focusing our search on pairs that are most likely to be similar.



## 2. Locality Sensitive Hashing

to "hash" items several times, in such a way that similar items are more likely to be hashed into the same same bucket than dissimilar items are. We then consider any pair that hashed into the same bucket for any of the hashings to be a *candidate pair*. So we only need to check the candidate pairs into the same bucket while most of the dissimilar pairs will never hash into the same bucket, and therefore will never be checked.

Thus, we hope:

- there dissimilar pairs that do hash into the same bucket will be only a small fraction of all pairs.
- most of the truly similar pairs will hash into the same bucket under at least one of the hash function.



## 3. Picture

In the background, we use lsh, an abbreviation of locality-sensitive hashing, to analyze to co-author ship given a dataset that is an undirected graph representing the co-authorship between researchers. 

for any query node(author), I find the top-10 nodes(excluding itself) whose neighbor sets have the highest Jaccard similarity scores with that of the query node.







## 4. Optimization

|          | Positive                                   | Negative                                      |
| -------- | ------------------------------------------ | --------------------------------------------- |
| Positive | TP(put similar sets into a bucket)         | FP(put dissimilar similar sets into a bucket) |
| Negative | FN(fail to put similar sets into a bucket) | TN(don't put dissimilar sets into a bucket)   |

  The main aim of optimization is to decrease FN and FP



## 5. Similarity Searching

![image-20230602120012604](D:\Jupyter\DataScienceAlgorithm\project\project1(lsh)\README.assets\image-20230602120012604.png)
