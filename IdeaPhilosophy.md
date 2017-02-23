When one design a model or a system, it contains several assumption or designs that is not good enough. 
We can step backword and set them with more freedom, less restrictions.

Design system without specific model.
Give design more dimention of freedom.

We can leverage more attributes or characteristics of user's applications

machine learning / deep learning only can do/simulate what people can do.
It is questionable that machine learning could predict something that people cannot do, like forcast the stock market.

## What MapReduce does NOT work well
1. Not everything fits Map/Shuffle/Reduce pattern.
2. small data => overhead is high
3. small updates to big data. e.g. add a few documents to a big index.
4. unpredictable reads (neither Map or reduce can choose input)
5. multiple shuffles, e.g. page-rank (can use multiple MR but not efficient)

## about GFS
###good

1. huge sequential reads and writes appends
2. huge throughput (3 copies, striping)
3. fault tolerance of data (3 copies)
###bad

1. fault-tolerance of master
2. small files (master a bottleneck)
3. clients may see stale data
4. appends maybe duplicated
