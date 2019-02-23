# Parallel_association_rules
Parallel computing implementation of association rules learning.

external dependencies:
 * [Numpy](http://www.numpy.org/)
 * [pandas](https://pandas.pydata.org/)
 
For calculating frequent pattenrs an optional method is:

 * [mlxtend](http://rasbt.github.io/mlxtend/user_guide/frequent_patterns/association_rules/#association-rules-generation-from-frequent-itemsets) (with "apriori" module. Another alternative is pyspark mllib for frequent pattern tree)



# example:
```
frequent_petterns = mlxtend.frequent_patterns.apriori(
                                                     transactions_DataFrame,
                                                     min_support=0.5,
                                                     max_len=4
                                                     )
                                                     
#  similar to mlxtend.frequent_patterns.association_rules but for computation in parallel:                                                    
association_rules_results = parallel_association_rules (
                                                        frequent_petterns,
                                                        n_parallel_branch=multiprocessing.cpu_count(),
                                                        metric="confidence",
                                                        min_threshold=0.7
                                                        )
```


# Comparison
![2](comparison.png "Comparison")
