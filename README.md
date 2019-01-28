# understanding-elasticsearch
ramp up on internals for myself

# inverted index
Document containing map from terms to document (maybe position)
Contrary to the *forward index* (list of document to terms.)

```
term    freq    document_id
---------------------------
hello   1       1
world   2       1,2
```

Can be used with eg OR and AND operations to find documents of interest.
Finding terms by prefix is O(logn). Finding terms by substring is O(n).

Immutable, which B-trees are not.

Need to consider index compactness as a quality of the query speed.

Lucene keeps immutable index segments. It periodically merges those segments. (see article http://blog.mikemccandless.com/2011/02/visualizing-lucenes-segment-merges.html)

