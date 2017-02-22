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
